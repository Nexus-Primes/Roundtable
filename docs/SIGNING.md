# How Roundtable is signed - the procedure

Roundtable installs other programs and changes your files, so what it trusts has to be written down. This is the procedure for the people who publish it. Nothing here is a secret except the
private key, which is never in the repository.

## What is signed, and by what

| What | Signed with | Checked by | Where |
|---|---|---|---|
| A release (`Roundtable-x.y.z-windows.zip`) | the **release key** (`packaging/keys/release-signing.key`) | the program, before an update is installed (`core/appupdate.py`, `RELEASE_PUBKEY`) | `<zip>.sig` beside the release |
| The mod-knowledge **feed** (`feed/recipes.json`) - recipes, starter packs, the tool catalog, hash pins | the same key today; a separate **feed key** is planned (see "Rotation") | the program, about once a day (`core/feed.py`, `PUBKEYS`) | `feed/recipes.json` + `feed/recipes.json.sig` |
| A tool or me3 installer download | not signed by us: its **SHA-256 is pinned in the feed** after a maintainer looked at it | the program, before the tool is unpacked / the installer is run (`core/pins.py`) | `hashes` in the tool's feed entry, `pins` for the me3 installer |

The signed messages are different for releases and feeds (`Roundtable feed v1\n...` against `Roundtable release v1\n...`), so a signature made for one can never pass as the other.
The program can only **verify**: signing and key generation live in `packaging/rt_signing.py`, which is not part of the program.

## Who may sign

Only a maintainer, from a machine they control, with the key offline (see "Where the key lives"). A pull request never signs anything: it edits a `*.src.json` file, a maintainer
reviews it, and only then runs `python packaging/publish_feed.py --yes`.

## Reviewing a pull request that edits the feed

Do every item; do not skip one because the author looks trustworthy.

1. **The diff is only in `feed/*.src.json`.** Any other changed file is a separate review.
2. **The JSON parses and every entry passes the program's own checks:** `python packaging/publish_feed.py` (dry run) lists malformed entries; the manager would silently drop them.
3. **Nothing new can fetch from somewhere new.** A tool entry names a GitHub `owner/repo` and/or Nexus mod numbers - open each and confirm it is the real project of the tool it claims to be (right
   author, right name, plausible history). Reject an entry whose repository was created recently or whose name is one letter off a popular one.
4. **Hashes are yours, not the author's.** Never copy a `sha256` from a pull request. Run `python packaging/pin_hashes.py tool KEY` (GitHub tools) or `... --file F --version V` for a file you
   downloaded yourself and checked: the release page, the author's own published hash if there is one, a scan, and the file's contents. A pin is a statement that **you** looked at it.
5. **`min_app` is right** for what the entry needs. A feed that needs a newer manager is stored but unused until the manager updates.
6. **Recipe text is plain text.** Nothing in a recipe is ever run, but it is shown to people: no links disguised as instructions, nothing alarming or misleading.
7. After publishing, run `python packaging/check_feed.py` (below) and look at the live feed once.

## Where the key lives

- `packaging/keys/release-signing.key` on the maintainer's machine. The publishing scripts only ever upload the files they name (`publish_feed.py`, `release.py`, `publish_readme.py`), never the `keys` folder - and the key must **never** go into a repository, CI secrets, a chat, or a cloud drive.
- An offline backup, made with `python packaging/backup_key.py <folder>` onto a drive that is then put away. Without the key, nobody's manager will accept another release or feed - losing it means shipping a
  new program build with a new public key by hand, which every user has to install themselves. Back it up.
- If CI ever needs to publish a feed, give CI a **feed key only** (never the release key), as a secret scoped to a protected environment that needs a manual approval to run.

## Rotation (moving the feed to a key of its own, or replacing a key)

The program accepts a feed signed by **any** key in `feed.PUBKEYS` (today one key). To move without breaking anyone:

1. Generate the new key: `python -c "import sys; sys.path.insert(0,'packaging'); import rt_signing as r; s,p=r.generate(); print(s.hex(), p.hex())"` - keep the seed offline, note the public key.
2. Add the public key to `feed.PUBKEYS` and ship a **release**. Wait until most people have updated (the releases page shows downloads; the updater nags within a day of start-up).
3. Start signing feeds with the new key (`packaging/keys/feed-signing.key`, `publish_feed.py` accepts a key that is in `PUBKEYS`).
4. In a later release, drop the old key from `PUBKEYS`. A feed signed with it is then refused.
5. If a key is **leaked**: ship a release that removes it from `PUBKEYS` immediately, publish a feed signed with a new key already listed, and say so in SECURITY.md.

The release key stays offline and is only used for `release.py`.

## Checking what is published

```
python packaging/check_feed.py --dir feed        # a checkout of the repo
python packaging/check_feed.py                   # the live feed on GitHub
```

It fails when the signature doesn't verify, when the signed file doesn't match the `*.src.json` sources (an unsigned source edit, or a signed file edited by hand), when an entry is malformed, or when
a pin isn't a SHA-256. It needs no private key. **Today it runs on the maintainer's machine** (after every publish, and when reviewing a pull request against the live feed): the public repository holds only the feed and
the docs, not the program's source that the check uses to verify, so it can't run in the repository's own CI. If the source is ever published there, this workflow would run it on every pull request
(`.github/workflows/feed-check.yml`):

```yaml
name: feed-check
on:
  pull_request:
    paths: ["feed/**"]
  push:
    branches: [main]
    paths: ["feed/**"]
jobs:
  check:
    runs-on: windows-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v5
        with: { python-version: "3.12" }
      - run: python packaging/check_feed.py --dir feed
```

(A pull request that edits `recipes.src.json` fails this until a maintainer has reviewed it and published - which is the point: an unsigned source edit never looks "done".)
