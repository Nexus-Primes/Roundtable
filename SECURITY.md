# Security

## Reporting a problem

If you find a way Roundtable could be tricked into running something it shouldn't, leaking your Nexus key or Discord webhook, accepting an unsigned update, or touching files it shouldn't, please **don't open a public issue**.

Use the **Security** tab of this repository and choose **Report a vulnerability** to send a private report. Include what you did, what happened, and the Roundtable version (bottom right of the window). You'll get a reply as soon as I can read it.

## What is already protected

- Updates are signed. Roundtable carries the publisher's public key and refuses a download whose signature doesn't check out.
- Your Nexus key and Discord webhook are stored encrypted with Windows' own protection, tied to your Windows account.
- Archives that try to write outside their folder are rejected.
- Mods are only downloaded from the Nexus and GitHub addresses Roundtable knows about.

## Supported versions

Only the latest release is supported. Update from inside Roundtable, or from the [releases page](https://github.com/Nexus-Primes/Roundtable/releases/latest).
