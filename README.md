# Roundtable

*(formerly ER Mod Manager)*

One window to launch vanilla or any mod pack, check for updates, edit configs, and install new mods.
It sits on top of **ModEngine3 (me3)** and reads the `.me3` profiles your packs already have.

## Run it

Double-click **`Roundtable.vbs`** (no console window). Or: `.venv\Scripts\python.exe -m er_mod_manager`

Paths (me3.exe, Mods folder, game folder) are auto-detected; change them under **Settings**.

## What it does

| | |
|---|---|
| **Look & library** | Elden Ring's own logo and key art (read from your Steam library cache, never copied or bundled) on the Vanilla page and as banners; each mod gets a banner from its own picture. Sidebar: search, **All / Updates / Issues** filters, sort by name / recently played / most played, update badges. Optional window background (Settings): Elden Ring artwork, your own picture, or none. |
| **Characters** | Sidebar -> **Characters**. Lists your save files and which mod uses each (`.sl2` vanilla, `.co2` Seamless, `.err` Reforged...). **Automatic backups** are taken before every launch from the manager (unchanged saves are hard-linked, so it costs little disk), plus **Back up now**, **Restore...** (it backs up what it's about to replace, and refuses while Elden Ring is running) and **Delete**. For **character appearance** it backs up your saves and opens a save editor you already have (it finds `er-save-editor.exe` etc.). The manager never edits a save itself. |
| **App updates** | When the app's own code or `CHANGELOG.md` changes on disk, an **Update ready - restart** button appears above *Install a mod*; click it to restart onto the new version. **Tools -> What's new** shows the changelog (it also opens once after each update). Every change bumps `APP_VERSION` in `core/settings.py` and adds a `CHANGELOG.md` entry. |
| **Organize DLL mods** | Tools -> **Organize DLL mods...** gives every mod its own copy of your DLL mods (settings included) in an `extra dll mods` folder listed in its own profile, and moves the global Elden Mod Loader (`dinput8.dll`, `mod_loader_config.ini`, `Game\mods`) out of the game folder into `Retired` next to your Mods folder. Mods that ship their own copy of a DLL keep it (no double-loading); Reforged gets its DLLs through its own `dll\offline` folder. **Undo DLL organization** restores every file exactly. |
| **Sessions** | The Play button shows **RUNNING** while the game is open (and blocks a second launch); playtime and last-played are tracked per mod and for vanilla. |
| **Launch** | Vanilla goes through Steam (with Easy Anti-Cheat). Packs go through `me3 launch -g eldenring -p <profile>`. Packs that ship their own launcher (e.g. Reforged's `.BAT`) list it as a target too; targets with an "Online" launcher warn about ban risk and are never the default. |
| **Health check** | Flags missing DLLs/folders, profiles with everything disabled, duplicate DLLs, and online mode. **Repair** re-points a profile at a newer version folder (e.g. `ERRv2.2.0.9` -> `ERRv2.2.2.4`) without changing your on/off switches. |
| **Fix problems** | Overview tab -> **Fix problems...** scans the mod and offers repairs you tick one by one: re-link files that moved (e.g. into a new version folder), copy in a missing shared DLL (ErdTools, erdyes...) from another mod / `Additional Mods` / the game's `mods` folder, remove stale entries, disable the older of two identical DLLs. It also reads each enabled DLL's import table to find real missing dependencies (e.g. the Visual C++ runtime) and points you at the fix. Nothing is overwritten; each fix is backed up and **Undo last fix** reverses it. |
| **Profile check** | A mod's profiles are compared with each other: if one skips DLLs the others load (an optional profile missing your extras), or a co-op profile has no `ersc.dll`, it's flagged on the Overview tab and **Fix problems** can add them (backed up, undoable). |
| **Last launch report** | After each session, or via **Check last launch**, the manager reads ModEngine3's log and the mods' own log files from that launch and explains what went wrong: unsupported game version, DLL loaded too late, hook not found, failed to load, crash. |
| **Game updates** | The manager remembers your `eldenring.exe` version; when it changes it tells you, offers to check mods for updates, and marks mods whose logs show they don't support the new version. |
| **Seamless Co-op versions** | Tools -> **Seamless Co-op versions...** lists every `ersc.dll` (mods + game folder) with its version and updates older copies from the newest one, because Seamless refuses to start when its DLL is out of date. Backed up; **Undo last sync**. |
| **Loadouts & load order** | Components tab -> **Loadouts** saves/restores named combinations of switched-on mods (the previous state is kept). Drag rows, or use the arrows, to change the DLL load order. |
| **Setup backup** | Tools -> **Back up manager setup...** zips settings, links/versions, pictures, loadouts and your `.me3` profiles (Nexus key left out by default). **Restore setup...** keeps this PC's paths and key, backs up what it replaces, and can be undone. |
| **Before you play** | PLAY first looks the profile over and interrupts only when something is likely to go wrong: a missing file, DLLs your other profiles load being skipped, an old Seamless (it closes the game at once), a mod that refused this game version last time, or a save file last used by a different mod. Fix / Update Seamless / Launch anyway. Off switch in Settings. |
| **Launch history** | Each session is recorded (when, how long, what the logs said). After a bad launch the Overview tab lists what you switched on or added since the last one that worked and can switch those off. |
| **Conflicts** | Components tab -> **Check conflicts** lists game files that more than one of a profile's asset folders replace. |
| **Share** | **Share...** on a mod page: your setup only (profiles, settings files, exact versions to match for co-op) or the whole mod folder. |
| **Go to / compact** | **Ctrl+K** jumps to any mod or tool by typing a few letters. Tools -> **Update mods one by one** opens the update for the mod you pick. Compact sidebar and a daily update check are in Tools / Settings. |
| **Merge packs** | Packs built from other mods (FRZN's Merge Modpack) get an **Install the dependencies** window: the exact file of each source mod in the article's order (McKenyu pinned to 1.3.11), downloaded automatically (Premium) or via Nexus's Mod Manager Download button, then layered into *Drag Files Into Here* with the merge moved on top. Resumable. |
| **Clean up** | Tools -> Storage -> *Choose downloads to delete...*: every downloaded archive with why it can go (installed, older copy, used for a layered pack); nothing is removed until you tick it and confirm. Settings -> Updates and safety can also keep only the newest few archives per mod and trim old backups automatically (both off by default). |
| **Setup steps** | Overview tab -> **Setup steps**: programs a mod needs run first (a randomizer, a config tool). Choose *ask each time*, *every launch* or *only when I click Run*; PLAY runs them, waits for you to close them, then launches. The Item & Enemy Randomizer is recognised automatically and, once it has generated files, the manager offers to load them in the profile. Desktop shortcuts run only the *every launch* steps. |
| **Mod launchers** | A mod's own launcher program (Convergence's `ConvergenceLauncher.exe`) can be added from its Overview tab (**Add a launcher...**, or accept the suggestion when one is found in the mod's folder or Downloads). It then appears in the Play list - for Convergence as its own window, *launch* and *update, then launch* - and works from desktop shortcuts too. |
| **Clean game folder** | Mods like Convergence break when other mods hook the game from the game folder (ReShade's `dxgi.dll`, Elden Mod Loader's `dinput8.dll` / `mods\`), while others rely on them. PLAY moves those files aside only for the mods that need a clean folder (tick *Needs a clean game folder* in Profile options; Convergence is on by default) and puts them back when the game closes. Nothing is deleted; **Tools -> Put game-folder files back** is the manual fallback. |
| **Self-managed mods** | Mods that install, update and launch themselves (Convergence) are left alone: *Fix problems* only explains, *Organize DLL mods* skips them and the manager never generates or edits their profiles. Use their own launcher for repairs. |
| **Delete a mod** | **Delete...** on a mod page moves its folder to `Retired\Deleted mods` with the manager's notes about it (nothing is erased). **Tools -> Deleted mods...** restores it or deletes it for good (asks first). |
| **DLL add-ons** | DLL-only mods (Transmogrify, Armor Dyes, Freecam, Map for Goblins) can be added to the mods you play: the installer offers *Add it to my mods*; **Attach to other mods...** (Components tab) does it for ones already installed. Files go into each mod's `extra dll mods` and its profiles; **Undo last add-on install** reverses it. To update an add-on, install the new version over it (old files are backed up). |
| **Doctor** | Tools -> PC check (and *Doctor* on a mod page): game folder and version, me3, Visual C++ runtime, Steam, OneDrive, disk space; for a mod, every profile, DLL (loadable, 64-bit, developer build), save file and Seamless version. *Copy report* for help requests. |
| **Watched launch** | After PLAY the manager reads me3's log for a minute and says at once if the game started without your mod (and why), or confirms how many DLL mods loaded. |
| **Co-op check** | *Co-op check...* on a mod page: save a small description of your setup (versions, DLL hashes, Seamless settings, a code for the password) and compare it with a friend's - lists exactly what differs. |
| **Known mods list** | Per-mod knowledge (main profile, never-working DLLs, self-managing mods, notes) as data in `data/recipes.json` + a built-in list. Tools -> Known mods list imports/exports it. |
| **Nexus download button** | Settings -> *Nexus download buttons* registers the manager for `nxm://` links; the 'Mod Manager Download' button then sends files here (free accounts too). |
| **Add-on updates** | Add-ons are listed on the mod's Overview with their version; Nexus-linked ones show 'v2.0 available'; *Update from file...* updates every copy. |
| **Storage** | Tools -> Storage: sizes of mods, Retired, backups, downloads; empty downloads / trim old backups (originals and latest undo kept). |
| **Self-update** | Packaged copies can update from a GitHub release: Settings -> *Update the manager from* `owner/name` (the repo must publish the `-windows.zip` from `packaging/build.py --exe`). |
| **Errors** | Unexpected errors go to `data/logs/errors.log` and show a *Copy details* dialog (Tools -> Open the error log). |
| **DLL presets** | Tools -> DLL presets...: save the DLL mods you use everywhere as a preset, add it to any mod in one click (*Add DLL preset* on Components), or have it ticked for every new mod. |
| **Install tracked mods** | Tools -> Import tracked mods -> *Install the ones I don't have...*: installs tracked Nexus mods that aren't here yet (automatic for Premium; opens each Files page and uses the Mod Manager Download button for free accounts). |
| **Add Seamless Co-op** | *Add Seamless Co-op...* on a mod (or Settings -> add it to every new mod): copies the newest Seamless into the mod, writes a co-op profile and gives it a unique save extension. Undo: Tools -> Undo last Seamless Co-op add. |
| **Save-file extension** | *Save-file extension...* on a mod with Seamless: change the ending of its co-op save, see collisions with other mods, optionally copy the existing save across. |
| **App icon** | Tools -> Create a shortcut with the app icon (desktop + Start menu). Setup.bat does this once for source copies. |
| **Favourites, tags, notes** | *Organize ▾* on a mod. Favourites sort first (★ chip filters them); search finds names, notes and tags (`#tag`). |
| **Verify files** | *Organize -> Verify files...*: record a fingerprint of a working mod, later see what's missing, cut short or changed. Read-only. |
| **Guided tour and light theme** | A first-run tour lights up the real buttons one at a time; Appearance has an Ivory light base. Bloodborne has a guided controller check. |
| **All tools** | Tools -> All tools...: every tool in one window, grouped on tabs with a line about each. Opening a window from another replaces it and adds a Back link. |
| **Motion** | Appearance -> Motion: Off / Calm / Fluid / Lavish - how much pages, tabs and cards glide and fade as you move around. |
| **Mod pages in the installer** | *Install a mod* shows the highlighted mod's picture, tags, description and recent changes beside the results; buttons open its comments, bug reports and images on Nexus. |
| **Quick launches** | Overview -> Quick launches: name a setup (mod + profile + saved on/off combination) and start it in one click; also in Ctrl+K. |
| **The room** | Friends' setups -> Room view: everyone's mods side by side with a ready light per friend, and a note after start-up on who you match. |
| **Why won't it start?** | One button that collects every clue (Windows Defender removing a file, missing files, the PC check, the last launch's logs) and lists the likely cause first. The conflict check also lets you fix clashes. |
| **Overview** | Each modded game has an Overview page: counts, the Updates hub, and every mod as a sortable table or a card gallery. |
| **Game library** | All games... opens a Steam-style library of every supported game (Elden Ring, Nightreign, Dark Souls 1-3, Bloodborne). Games installed through Steam are found by themselves; Dark Souls 1 and 2 get Play and save backups. |
| **Bloodborne (Windows port)** | Pick Bloodborne in the game box: Play, a health check, every setting of the port's launcher (graphics, language, cheats, mods, online co-op with a connection test), controller tools and save backups. Roundtable never changes the game files. |
| **Several games** | The box at the top of the sidebar switches between Elden Ring, Elden Ring Nightreign and Dark Souls III. Each has its own mods folder, profiles, mod records and save backups. |
| **Friends' setups** | Tools -> Mods -> Friends' setups...: keep your friends' setup links here and see at a glance whether you match (missing mods, other versions, differing DLL switches); one click matches theirs. |
| **Quick actions** | Drop a mod on the window to install it; Ctrl+K go to anything, Ctrl+F search, Ctrl+N install, Ctrl+Enter play, F1 lists them; a bell in the footer keeps past messages; Report a problem opens a pre-filled GitHub issue. |
| **Getting started** | A three-step checklist on first run (find the game, install me3, add a mod). Before you play, a warning when two enabled mods replace the same game files. |
| **Go back** | Tools -> This program -> Go back to an earlier version...: if an update misbehaves, return to the previous version (saved automatically on your PC) or any older release. Your data stays. |
| **Share my setup** | Tools -> Mods -> Share my setup... / Install a friend's setup...: a code (or file) with your mods' exact versions, which DLLs are on and in what order, add-ons, Seamless Co-op setup, and optionally the password and settings files. The friend's manager rebuilds it step by step. No mod files or secrets unless you tick the password. The friend sees a preview first, can undo it afterwards, and can sync from a gist link when you update your setup. |
| **Install / update me3** | Tools -> Install or update me3...: downloads me3 from its official GitHub release and runs its installer; also installs the Visual C++ runtime (Microsoft-signed only). The manager checks daily for a newer me3 and finds me3 by itself if it's installed later. |
| **Recommended DLL sets** | DLL presets -> Recommended sets...: builds a preset from a built-in list of Nexus mods (nothing is redistributed; each mod is fetched from its own page). |
| **Seamless settings copies** | When a mod has several Seamless folders, the Configuration tab labels them and offers to make their settings match. |
| **Repair on install** | New mods have their profiles repaired automatically (moved paths, Mod Engine 2 / debug DLLs, entries for files the author didn't ship); undo with *Undo last fix*. Setting: *Repair a new mod's profiles as it installs*. |
| **Appearance** | Tools -> This program -> Appearance: twelve Elden Ring themed colour schemes, your own accent/scheme, text size, list width, font, corners, high contrast, colour-blind status colours - all live; Cancel undoes the preview. |
| **Characters in saves** | Characters page: see each save's characters (name, level, slot) and copy one into another save of the same Steam account (backups first, checksums verified). |
| **Second copy of backups** | Characters -> Backups: also copy every save backup to another drive, NAS share or cloud-synced folder. |
| **Play with friends** | Button on a mod: co-op readiness checklist + a ready-to-send invite; *Compare setups* is the old Co-op check. |
| **Discord** | Settings -> Discord webhook; Tools -> Mods -> Post an update to Discord (you see and approve the message). |
| **Passwords and save files** | Tools -> Seamless Co-op: every Seamless instance's password and save extension in one window; fix clashes; copy saves to new names. |
| **Guarded deletes** | Characters page: delete a character or a whole save file only after a protected backup and typing its name; deleted saves are moved aside, not erased. |
| **Preset duplicates** | Adding your DLL preset to a mod that already has the same DLL asks which copy to keep (or follows the Settings rule); the other is left out, so nothing loads twice. Undoable. |
| **Components** | Tick/untick each DLL and asset folder in a profile; add or remove entries; savefile override; Arxan / online toggles. |
| **Configuration** | Finds the pack's `.ini/.toml/.json` files. INI settings get typed controls with the file's own comments as help. Only the changed value is rewritten - comments and layout stay. A Raw text tab handles anything else. |
| **Updates** | Paste a mod's GitHub or Nexus link on its Updates tab. GitHub works with no setup. Nexus needs your own (free) personal API key in Settings. |
| **Update this mod** | Updates tab -> **Update to x.y.z**. GitHub mods and Nexus *Premium* accounts download automatically (https, GitHub/Nexus hosts only, after you confirm). Nexus free accounts: it opens the Files page and takes the file you downloaded. **Update from file...** works for any mod. Before anything is changed you see a preview; every file it replaces is backed up, your `.me3` profile is kept (re-pointed at a new version folder if needed), your edited INI settings are carried into the new files, and old version folders are never deleted. **Undo last update** reverses it. It refuses to run while Elden Ring is open. |
| **Nexus tracking** | Settings -> **Test key**, and **Import tracked mods...** links the mods you "Track" on Nexus to your packs. Update checks batch into one request. |
| **Search Nexus** | **Install a mod** opens on a Nexus search (public - no API key needed): type a name or browse the most popular, sort by endorsements / downloads / recently updated, see thumbnails, author, version and stats. **Install this mod** downloads it automatically on a Premium account (key in Settings); otherwise it opens the mod's Files page and picks up the finished download from your Downloads folder by itself. The installed mod is linked to its Nexus page, so update checks and its picture work straight away. |
| **Install a mod** | Pick a `.zip` (or `.7z`/`.rar` if [7-Zip](https://www.7-zip.org/) is installed) or a folder. It shows what it detected (asset folders, DLLs; known libraries unticked), you confirm, then it lands in `Mods\<name>` with a generated `.me3`. If the mod ships its own `.me3`, that is used as-is. |
| **Tidy desktop shortcuts** | Moves old mod shortcuts into one desktop folder (nothing is deleted). **Desktop shortcut** on a pack creates a single clean shortcut that launches it directly. |

## Sharing it

`python packaging/build.py` writes `dist/Roundtable-<version>-source.zip` (about 0.2 MB; the other person runs *Setup (run me first).bat*,
which needs Python 3.11+). `python packaging/build.py --exe --python <interpreter with pyinstaller>` also writes
`dist/Roundtable-<version>-windows.zip` (about 40 MB, no Python needed; add `--installer` for a setup.exe via Inno Setup, and set `ERMM_SIGN_CMD` to sign with your certificate; Windows may show a one-time "unknown publisher" screen
because the app isn't code-signed). Your `data` folder, Nexus key and backups are never included. The other person still needs
Elden Ring and me3; the app tells them what's missing on first start.

## Safety

* Every profile/config save first copies the old file to `data/backups/`.
* Zip extraction rejects path-escape tricks.
* Online play with mods can get you banned. The manager never enables it silently.
* Nothing is sent anywhere except GitHub / Nexus API requests for update checks.

## Files

* `data/settings.json` - paths and your Nexus key (local only). `data/packs.json` - versions, source links, notes per pack.
* `er_mod_manager/core` - engine (profiles, launcher, updates, installer, configs). `er_mod_manager/ui` - PySide6 interface.

## Known limits

* Nexus doesn't allow automated downloads for free accounts, so "install" starts from a file you downloaded.
* Mods without a GitHub/Nexus link can't be auto-checked; use the Updates tab to record a link and version by hand.
* Pack-specific setup scripts (e.g. Elden Vins' `OPEN-THIS-TO-INSTALL-MOD.bat`) still need to be run once; the health check shows what's missing until you do.
