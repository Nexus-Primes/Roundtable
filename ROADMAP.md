# Roadmap

What is being worked on, in what order. These are plans, not promises; the order changes when something breaks or when real testing shows a better idea. Updated with each release.

## Now

- **Stable and Beta channels.** *Settings > Online > Release channel*: Stable by default; Beta gets each version about a week earlier. (0.103)
- **One program file.** `ER Mod Manager.exe` is gone; shortcuts that used it are repointed. (0.103)
- **Pinning every tool download.** Each catalog tool's download will show "Checked" once a maintainer has looked at it and pinned its hash. Until then installs ask first.
- **Real-world testing.** Five real mods, installed, updated, reinstalled and restored on a clean Windows, with the results written down in [docs/TESTING.md](docs/TESTING.md).

## Next

- **Restore points.** One button that remembers your mods list, profiles, settings, DLL presets and saves, and one flow that puts them back, with an automatic point before risky changes.
- **Playthroughs.** One character's mods, load order, DLL presets, Seamless password and saves, switched in one step.
- **"Why did it crash?"** One button that reads the crash logs and gives a ranked list of likely causes, each with a fix.
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
