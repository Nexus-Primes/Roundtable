# Testing a real mod with Roundtable

Roundtable's own automatic tests use made-up mods. What they cannot tell you is whether a real mod from Nexus installs, updates, reinstalls and launches on a real PC.
If you can test one on a clean Windows (a fresh user account or a virtual machine with the game installed), that result is worth a lot. This is how.

## The steps

Do them in this order, for one mod. Write down `pass`, `fail` or `n/a` (and why) for each.

| Step | What to do | A pass looks like |
|---|---|---|
| 1. Install | Install the mod from its Nexus page. With a Premium key Roundtable downloads it; with a free account it opens the page and you choose the file you downloaded | The mod is installed, has a profile, and its page shows nothing red |
| 2. Install, other account type | Remove it and install again the other way (Premium or free) | The same result as step 1 |
| 3. Update | Install an older file of the mod, then use the update button | The update is found and applied, and *Undo* is offered |
| 4. Reinstall | On the mod's page: **More > Reinstall (a fresh copy)...** with *Fully fresh* ticked | Your old copy is in *Retired > Reinstalled*; the mod is as step 1 left it |
| 5. Undo the reinstall | **More > Undo last reinstall** | The old copy is back exactly as it was |
| 6. Launch | Start the mod from Roundtable | The game reaches the title screen |
| 7. Uninstall | Remove the mod | It is moved to *Retired*; nothing is deleted |
| 8. Restore | Put it back from *Retired* | It starts again |

## What to write down

The Roundtable version (bottom right of the window), the mod and its version, the game version, the Mod Engine 3 version, your Windows version, and for each step `pass`, `fail` or `n/a`.
Add a screenshot of anything surprising, even if every step passed. Then open an issue with the [bug form](https://github.com/Nexus-Primes/Roundtable/issues/new/choose) (use it for results too),
or put the text in a pull request as `docs/verified/<mod>.md`.

Mods most wanted: Reforged, Convergence, Seamless Co-op, Elden Vins, and any single-DLL mod.

## Please don't

Test on your only copy of your saves (back them up first; Roundtable makes its own copies, but a test is a test), post your Nexus key, or share files from a mod's download.
