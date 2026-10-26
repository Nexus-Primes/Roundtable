# Roadmap

What is being worked on, in what order. These are plans, not promises; the order changes when something breaks or when real testing shows a better idea. Updated with each release.

## Now

- **Stable and Beta channels.** *Settings > Online > Release channel*: Stable by default; Beta gets each version about a week earlier. (0.103)
- **One program file.** `ER Mod Manager.exe` is gone; shortcuts that used it are repointed. (0.103)
- **Restore points** (0.104): one button that remembers your mods, profiles, settings, DLL presets and saves, and a restore that shows what changes first. Automatic points before risky changes.
- **Playthroughs** (0.105): one character's mods, load order, DLL switches, Seamless password and save, switched in one step. Starting one from a collection or a friend's setup comes with collections.
- **"Why did it crash?"** (0.106): one button that reads the crash records and logs and ranks the likely causes, each with a fix; known causes can now arrive with the signed feed.
- **Pinning every tool download.** Each catalog tool's download will show "Checked" once a maintainer has looked at it and pinned its hash. Until then installs ask first.
- **Real-world testing.** Five real mods, installed, updated, reinstalled and restored on a clean Windows, with the results written down in [docs/TESTING.md](docs/TESTING.md).

## Next

- **Collections.** A shareable list of mods and settings that installs in one click.

## Later

- **What does this mod change?** A read-only view of a mod's game-data changes and which mods change the same thing. Nothing is edited.
- **Load-order help** built on that view.
- **Shareable setups with checks** (same versions, same DLLs) and a co-op ready check.
- **Run tracking** from your save (bosses, time played), and challenge runs.
- **A tool for mod authors**: project, versioning, a clean-setup test, packaging.
- **A plugin boundary** so tools can be added without changing the program.
- **A docs site**, translated strings, and a build planner.

## Left out on purpose, for now

Crowdsourced reports of which mods work together, and Steam Deck / Linux support (that one needs a check of whether Mod Engine 3 runs under Proton first). Both can be revisited.
