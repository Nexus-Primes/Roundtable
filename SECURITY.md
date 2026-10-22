# Security

## Reporting a problem

If you find a way Roundtable could be tricked into running something it shouldn't, leaking your Nexus key or Discord webhook, accepting an unsigned update, or touching files it shouldn't, please **don't open a public issue**.

Use the **Security** tab of this repository and choose **Report a vulnerability** to send a private report. Include what you did, what happened, and the Roundtable version (bottom right of the window). You'll get a reply as soon as I can read it.

## What is already protected

- Updates are signed. Roundtable carries the publisher's public key and refuses a download whose signature doesn't check out.
- Your Nexus key and Discord webhook are stored encrypted with Windows' own protection, tied to your Windows account.
- Archives that try to write outside their folder are rejected.
- Mods are only downloaded from the Nexus and GitHub addresses Roundtable knows about.
- The mod-knowledge feed (notes, starter packs, the tool list) is signed too, is refused if it is older than the one Roundtable has or fails its check, and can only ask for the fields a recipe already
  has: it can never name a download address or a program to run. Roundtable accepts a feed signed by any of a short list of keys, so a key can be replaced without breaking anyone.
- **Tools you install from the list, and the me3 installer, are checked against hashes.** When the maintainers have looked at a version they pin its SHA-256 in the signed feed, and Roundtable refuses a
  different file for that version. A version nobody has looked at yet (a brand-new upstream release) is never installed without saying so and asking first; the command line needs `--allow-unchecked`.
  What was installed, and whether it was checked, is kept with the tool.
- The me3 installer is shown with who signed it (or that it isn't signed) and whether this exact file was checked, before it is run.

## What is not protected (said plainly)

- A tool version nobody has pinned yet comes straight from GitHub or Nexus. If that account were taken over, the file would be whatever the attacker uploaded; the warning and the extra confirmation are the
  protection, and they only help someone who reads them.
- Roundtable itself is not yet code-signed by a certificate authority, so Windows SmartScreen may warn when you first run it. Updates *inside* Roundtable are checked against its own signature, which is
  what keeps a tampered update out. The procedure for signing and for replacing a key is in [docs/SIGNING.md](docs/SIGNING.md).
- Roundtable does not download the Bloodborne port; it only starts the one you installed, and its "Test connection" sends a plain request (no account, key or webhook) to the server address you set.

## Supported versions

Only the latest release is supported. Update from inside Roundtable, or from the [releases page](https://github.com/Nexus-Primes/Roundtable/releases/latest).
