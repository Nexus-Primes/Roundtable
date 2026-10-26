# Contributing

Thank you for wanting to help. Roundtable is a small project with one maintainer, so this page says plainly what is useful and how it is reviewed.

## The most useful things

1. **Tell us what broke.** Open an issue with the [bug form](https://github.com/Nexus-Primes/Roundtable/issues/new/choose). The three things that make it fixable: the Roundtable version (bottom right of the window),
   the mod and its version, and what you expected against what happened. In Roundtable, **Report a problem...** (in the sidebar's menu) writes a short text for you to paste; it hides your Windows user name and never includes your Nexus key.
2. **Correct or add what Roundtable knows about a mod.** That knowledge lives in the signed feed: [`feed/recipes.src.json`](feed/recipes.src.json). Open a pull request that edits it, or open an issue with the details.
3. **Test a real mod on a real PC.** Roundtable's own tests use made-up mods. A result from a clean Windows with a real Nexus download is worth more than most code. See
   [docs/TESTING.md](docs/TESTING.md) for the steps and what to write down.

## How a feed change is reviewed

A pull request that edits `feed/*.src.json` is **not** published by merging it. A maintainer reads it, checks every link and every name against the real project, and only then signs and publishes it;
nobody's Roundtable accepts an edit that isn't signed. The checklist is in [docs/SIGNING.md](docs/SIGNING.md#reviewing-a-pull-request-that-edits-the-feed). Please:

- keep the text plain; nothing in an entry is ever run, but it is shown to people;
- never put a hash in a pull request. A hash is a statement that a maintainer looked at the file, so maintainers make them from downloads they checked themselves;
- say where each fact comes from (the mod's own page, its changelog, your own test).

## What this repository holds

This repository holds the public front page, the guides, the signed feed and the documentation. It does not hold the program's source, so there is no code to send a pull request against yet.
If that changes, this page will say so first.

## Ground rules for everyone

Be kind, assume good intent, and keep to the [code of conduct](CODE_OF_CONDUCT.md). Do not post anyone's Nexus key, Discord webhook, save file or private message.
Security problems are reported privately: see [SECURITY.md](SECURITY.md).
