<p align="center"><img src="docs/images/logo.png" alt="Roundtable - Elden Ring mod manager" width="260"></p>

# Roundtable

**A friendly way to install, organise and play Elden Ring mods - and to play co-op with your friends - without digging through folders.**

![The manager showing a mod, with a big PLAY button](docs/images/p-modpage.png)

If you've ever unzipped a mod, wondered which folder it goes in, and then watched the game start without it - this is for you. You pick a mod, press **PLAY**, and the manager takes care of the awkward parts: putting files in the right place, checking for problems *before* the game starts, keeping your saves safe, and keeping everything up to date.

> **Windows only.** Needs Elden Ring on Steam. You do **not** need to know anything about programming.

[**Download the latest version**](https://github.com/Nexus-Primes/Roundtable/releases/latest)

---

## What it does for you

| You want to... | The manager... |
|---|---|
| **Install a mod** | Searches Nexus Mods or opens the file you downloaded, shows you what's inside, installs it, and fixes the usual profile mistakes automatically. |
| **Play it** | One **PLAY** button. It looks the mod over first and tells you in plain words if something will go wrong - then watches the game start and tells you if your mod didn't load. |
| **Fix what breaks** | Explains why a mod won't start, repairs what it can (with undo), and can find which DLL is crashing the game. |
| **Set up big mod packs** | Knows what the major overhauls need, and layers in the other mods a pack like FRZN's Merge Modpack is built from. |
| **Play with friends** | Checks your co-op setup, helps everyone use the same password and versions, and writes you an invite to send. |
| **Keep your characters safe** | Backs up your saves automatically, can keep a second copy somewhere else, and asks twice before anything involving a save is deleted. |
| **Stay up to date** | Tells you when a mod, me3 or the manager itself has a new version - and updates without you leaving the app. |
| **Tidy up** | Shows which old downloads can go, and clears them only when you say so. |
| **Undo mistakes** | Almost everything it does is backed up and can be undone. |

![Animated tour: picking mods, switching tabs, spotting an update and a problem](docs/images/clip-tour.png)

---

## Get started

### 1. Download and unzip

Open the **[Releases page](https://github.com/Nexus-Primes/Roundtable/releases/latest)** and download the file ending in **`-windows.zip`** (it's under *Assets*). Right-click it, choose **Extract All...**, and put it in a simple folder such as `C:\Tools\Roundtable`.

> **Please don't** run it from inside the zip, from *Downloads* or *Desktop*, from a **OneDrive** folder, or from inside the Elden Ring folder. Windows and OneDrive can lock or hide files there, which causes confusing errors.

### 2. Open `Roundtable.exe`

The first time, Windows may say **"Windows protected your PC"**. That's only because the program isn't signed with a paid certificate. Click **More info**, then **Run anyway**.

### 3. Let it set itself up

![The Welcome window listing the three things to set up](docs/images/p-welcome.png)

On the first start Roundtable checks three things: your **Elden Ring game folder**, **me3** (ModEngine 3 - the small program that actually loads mods into the game) and your **Mods folder**. Press **Open Settings** to fix whatever it flags.

- **me3:** choose **Tools → This program → Install or update me3...** and follow the installer like any other. When it closes, Roundtable finds it by itself. If a Microsoft Visual C++ runtime is missing, the same window offers to install it.
- **Mods folder:** an empty folder is fine - Roundtable fills it.

![The Folders tab of Settings with the me3, Mods and game folders](docs/images/p-settings-folders.png)

### 4. (Optional, but handy) Add your Nexus key

A free Nexus Mods account lets Roundtable search for mods, show their pictures, and check for updates. On nexusmods.com open your account's **API Keys** page, copy the **Personal API Key**, paste it into **Settings → Online → Nexus API key**, and press **Test key**. The key stays on your PC, is stored encrypted, and is only ever sent to nexusmods.com.

Also on this tab: **Nexus download buttons** - turn it on and the *Mod Manager Download* button on a Nexus mod page sends the file straight to Roundtable. This works with free accounts.

![The Online tab of Settings with the Nexus API key and download buttons](docs/images/p-settings-online.png)

---

## Install a mod

Press **＋ Install a mod** (bottom left). There are two ways in:

- **Search Nexus Mods** - type a name, pick a result, and read its description, pictures and recent changes before you install. Buttons open its comments and bug reports on Nexus.
- **From a file or folder** - choose a `.zip`, `.7z` or `.rar` you already downloaded (`.7z` and `.rar` need [7-Zip](https://www.7-zip.org/); Roundtable tells you if it can't find it). You can also just drag the file onto the window.

![The Install a mod window on its From a file or folder tab](docs/images/p-install.png)

Roundtable unpacks the mod, shows what it found (DLL files and asset folders, and which to switch on), and installs it only when you press **Install**. Common profile mistakes are repaired as it goes, and the whole install can be undone. Small DLL mods (free camera, UI tweaks) are offered as an **add-on** to a mod you already play instead of a separate mod.

### Some mods need one more step

If a mod's author says something must be run once before the first launch - an install `.bat`, a *Setup UI images* shortcut, a zip of DLLs meant for the game folder - Roundtable offers to do it right after the install. **Nothing runs until you press a button.** Each item opens in its own window, Roundtable waits for it to finish, checks that it succeeded, and lets you retry if it didn't.

![The Finish setting up window offering to run a mod's install script](docs/images/p-postinstall.png)

### Packs built from other mods

Some packs, like **FRZN's Merge Modpack**, are made by layering several other mods you download yourself. After you install one, the **Install the dependencies** window opens (or press the button on the pack's *What this mod needs* card):

1. Press **Get it** on each mod. A Premium Nexus account downloads it for you; a free account opens that file's Nexus page and the *Mod Manager Download* button there hands the file back. Already downloaded it? Roundtable spots it in your Downloads folder.
2. When all are ready, press **Build it**. Each is unpacked and layered in the order the author's instructions give, using the right old version where needed (FRZN needs McKenyu's 1.3.11, not the newest).

![The Install the dependencies window](docs/images/p-dependencies.png)

If a build stops, press **Build it** again - finished steps are remembered. When the pack later publishes an update file, apply it from the pack's **Updates** tab (*Update from file...*); Roundtable shows the author's steps first, then offers to move the update's files on top of the layers, with a backup of everything it replaces.

---

## A mod's page

Click a mod in the list on the left. The top shows its version, where it's published and whether it's ready. Under the **PLAY** button are four tabs.

**Overview** - the health check (*"All good - everything this mod points to is there"*), setup steps, and what happened on the last launch.

![A mod's Overview tab with the health check and PLAY button](docs/images/p-modpage.png)

**What this mod needs** - on a known mod the Overview also shows a checklist for your PC - me3, the DLC, ray tracing, the game version - with a button next to anything that's missing, plus the author's own warnings and how to update.

![The What this mod needs card with a checklist and the author's warnings](docs/images/p-needs.png)

**Components** - every DLL and asset folder the mod loads. Tick to switch one on, untick to switch it off; drag or use the arrows to change the load order; **Add DLL...** and **Add asset folder...** add your own; **Loadouts** saves named combinations you can switch between; **Check conflicts** finds two mods replacing the same files.

![The Components tab listing a mod's DLLs with on and off ticks](docs/images/p-components.png)

**Configuration** - the mod's settings files shown as a tidy form (or raw text), with *Revert*, *Save changes* and *Open in editor*. Only the value you change is rewritten, so the file's comments and layout stay. Edited files are backed up first and the author's original is always kept.

![The Configuration tab showing a settings file as a form](docs/images/p-configuration.png)

**Updates** - covered [below](#keeping-up-to-date).

---

## Press PLAY

Pick the mod, pick a profile if it has several, and press **PLAY**. Before the game starts, Roundtable looks the profile over and, if something is likely to go wrong, tells you in plain words and lets you decide.

![The Before you play window listing a missing DLL and an out-of-date Seamless Co-op](docs/images/p-prelaunch.png)

While the game runs, the button shows **RUNNING** (and blocks a second launch) and playtime is tracked per mod. A minute after the game starts Roundtable reads me3's log and tells you at once if it started *without* your mod, and why.

Vanilla Elden Ring starts through Steam with Easy Anti-Cheat. Mods start through me3. Modded **online** play can get an account banned - Roundtable never turns online mode on and warns you if a profile has it.

---

## When something goes wrong

Start with the buttons on the mod's **Overview** tab:

- **Why won't it start?** collects every clue (including files Windows Defender removed) and lists the likely cause first.
- **Doctor** checks your whole PC: game folder, me3, the Visual C++ runtime, Steam, OneDrive and disk space.
- **Fix problems...** scans the mod and offers repairs you tick one by one - re-linking moved files, copying in a missing shared DLL, switching off files that can't work. Everything is backed up and **Undo last fix** reverses it.

![A mod whose health check reports a missing DLL, with Why won't it start, Doctor and Fix problems buttons](docs/images/p-health.png)

![The Why won't it start window listing likely causes](docs/images/p-why.png)

**Fix problems** lists each repair with a tick box and says what will happen. Nothing is overwritten, and what can't be fixed automatically is explained underneath.

![The Fix problems window with a repair to tick](docs/images/p-fix.png)

**The game crashes?** Roundtable reads Windows' own crash records and, if one DLL is to blame, offers to switch it off. If it can't tell, **Find the cause** switches half of a mod's DLLs and folders off, asks you whether it still crashes, and narrows it down to the one that matters. **Copy report** gathers everything for a help request, with personal paths removed.

![The Find the cause window with the mod's DLLs ticked](docs/images/p-bisect.png)

---

## Play with friends

Co-op only works when **everyone has the same mod versions, the same Seamless Co-op version and the same password.** Roundtable makes that much less painful.

On a mod's page press **Play with friends**. A green checklist covers the Seamless version, a password, your own save file, me3 and the game version, and you can copy a ready-to-send **invite** or post it to Discord. **Compare setups** finds out exactly *why* two people can't connect.

![The Play with friends window with a green checklist and an invite](docs/images/p-friends.png)

**Share my setup / Install a friend's setup** (in *Tools*): a friend pastes your setup (or a link to it) and Roundtable fetches the same mod versions, adds your add-on DLLs, sets up Seamless and switches the same DLLs on in the same order. The password and settings files are only included if you tick them. Your friend sees a plain list of changes first and can undo them.

![The Share my setup window with a list of mods and tick boxes](docs/images/p-share.png)

**All your passwords and save files in one place:** *Tools → Seamless Co-op → Passwords and save files...* lists every co-op setup on your PC. Change passwords and save-file endings (even set one password for everything), spot clashes, and let Roundtable give each mod its own. Changing an ending can copy your existing save across so your character comes with you.

![One window listing every Seamless Co-op instance with its password and save extension](docs/images/p-passwords.png)

**Seamless versions:** Seamless refuses to start when its DLL is out of date. *Tools → Seamless Co-op → Seamless versions...* lists every copy on your PC and updates the older ones from the newest.

![Every copy of ersc.dll with its version and status](docs/images/p-seamless.png)

---

## Your saves

![The Characters page listing the characters in each save](docs/images/p-characters.png)

Click **Characters** in the list. You see every save file, which mod uses it, and the characters inside.

- **Backups happen automatically** before each launch and before anything that touches a save. Unchanged saves share space, so keeping many costs little. *Back up now* takes one on demand, and a second copy can go to another drive or a synced folder.
- **Copy a character** from one save to another (for example into your co-op save) with *Copy this character to another save...*. It only works between saves from the same Steam account, checks everything first and backs up first.
- **Deleting is guarded.** Deleting a character or a whole save makes a protected backup, shows exactly what will go, and makes you **type the name**. Deleted saves are moved aside, not erased, and *Restore* brings them back.

Please **play offline** with copied or edited characters - modded online play can get an account banned.

---

## Keeping up to date

**Mods.** Open a mod's **Updates** tab. Roundtable compares your version with the mod's Nexus or GitHub page; when a new one is out a badge appears in the list and **Update to ...** downloads and applies it safely. **Undo last update** reverses it.

![The Updates tab with an update available, release notes and Update, Undo and Check buttons](docs/images/p-updates.png)

- **Patches are found and applied safely.** Some mods publish a small patch for the previous version as well as the full download. Roundtable tells them apart and offers the patch only when it was made for exactly the version you have.
- **The author's instructions are read.** If an update comes with a README that explains how to apply it, Roundtable shows those steps before changing anything.
- **Update from file...** applies a download you made yourself. Nothing changes without a preview, and every replaced file is backed up.

**me3** is checked about once a day (*Tools → This program → Update me3...*). **The game:** Roundtable remembers your `eldenring.exe` version; when a patch changes it, you're told and mods whose logs show they don't support it are marked. **Roundtable itself:** when a new version is published a banner appears in the sidebar; click it and the update downloads, its **signature is checked**, and it restarts with all your settings and backups kept. If a new version misbehaves, *Tools → This program → Go back to an earlier version...* returns to the one you had.

### Finding things and tidying up

Press **Ctrl+K** to jump to any mod or tool by typing a few letters; **F1** lists the shortcuts. **All tools...** lists every tool and setting on tabs, with a search box.

![Animated: typing a few letters in the Go to window finds a tool](docs/images/clip-search.png)

![The All tools window with a search box and tools grouped on tabs](docs/images/p-alltools.png)

![The Tools menu, grouped, with the Seamless Co-op group open](docs/images/p-tools-menu.png)

**Clean up downloads.** *Tools → Storage... → Choose downloads to delete...* lists every downloaded archive with why it can go: the mod is already installed, it's an older copy, or it was used to build a layered pack (kept unless you tick it, because a rebuild needs it again). Older copies are ticked for you, and **nothing is deleted until you confirm**. Installed mods are never touched. In *Settings → Updates and safety* you can also keep only the newest few archives per mod and trim old backups automatically - both are off by default.

![The Clean up downloads window](docs/images/p-cleanup.png)

---

## Make it yours

Open **Tools → This program → Appearance...** and pick a theme. Each is a complete colour scheme named after something from the Lands Between, and the whole manager changes straight away - **Cancel** puts everything back, **Save** keeps it.

![The Appearance window with twelve themes to choose from](docs/images/p-appearance.png)

### The twelve themes

Every theme, shown on the plain Elden Ring page exactly as it looks in the manager. Click a picture to open it at full size.

#### Erdtree

*The classic: warm parchment and gold.*

[![Erdtree theme](docs/images/theme-erdtree.png)](docs/images/theme-erdtree-full.png)

#### Tree Sentinel

*Gilded filigree plate over a dark ochre cape.*

[![Tree Sentinel theme](docs/images/theme-tree_sentinel.png)](docs/images/theme-tree_sentinel-full.png)

#### Night's Cavalry

*Jet-black armour, dried blood and a funeral steed.*

[![Night's Cavalry theme](docs/images/theme-nights_cavalry.png)](docs/images/theme-nights_cavalry-full.png)

#### Carian Knight

*Lapis-blue steel in the Lunar Queen's moonlight.*

[![Carian Knight theme](docs/images/theme-carian_knight.png)](docs/images/theme-carian_knight-full.png)

#### Black Knife Assassin

*Silent silver scale beneath a hooded black cloak.*

[![Black Knife Assassin theme](docs/images/theme-black_knife.png)](docs/images/theme-black_knife-full.png)

#### Crucible Knight

*Reddish bronze plate with an old green patina.*

[![Crucible Knight theme](docs/images/theme-crucible_knight.png)](docs/images/theme-crucible_knight-full.png)

#### Starscourge Radahn

*Amber starlight over a deep cosmic blue.*

[![Starscourge Radahn theme](docs/images/theme-radahn.png)](docs/images/theme-radahn-full.png)

#### Dark Moon Ranni

*Cold teal under a midnight sky.*

[![Dark Moon Ranni theme](docs/images/theme-ranni.png)](docs/images/theme-ranni-full.png)

#### Lord of Blood

*Mohgwyn's blood-dark plum and crimson.*

[![Lord of Blood theme](docs/images/theme-mohg.png)](docs/images/theme-mohg-full.png)

#### Scarlet Rot

*Rust-orange bloom over murky Caelid swamp.*

[![Scarlet Rot theme](docs/images/theme-scarlet_rot.png)](docs/images/theme-scarlet_rot-full.png)

#### Haligtree

*Pale green light in a quiet forest.*

[![Haligtree theme](docs/images/theme-haligtree.png)](docs/images/theme-haligtree-full.png)

#### St. Trina's Lily

*Pale lily-white on a dreamy lilac dusk.*

[![St. Trina's Lily theme](docs/images/theme-trina.png)](docs/images/theme-trina-full.png)

Prefer to mix your own? Choose **Custom mix** and pick any accent colour (or your own) and one of four colour schemes. You can also change the **text size**, the **font**, how **rounded** the corners are, the **width of the mod list**, how much **animation** you want (Off, Calm, Fluid, Lavish), switch on **high contrast**, or use **colour-blind friendly status colours**.

---

## Everything it can do

A complete list, by topic. Most items are in the **Tools** menu or on a mod's page - and **Ctrl+K** finds any of them by name.

### Installing

- Search Nexus Mods (no key needed) with pictures, tags, descriptions, comments and bug reports; install from a `.zip` / `.7z` / `.rar` or a folder; drag a mod onto the window.
- Every install is previewed first and can be undone; profiles are repaired as a mod installs (moved paths, Mod Engine 2 / debug DLLs, missing files).
- DLL-only mods become **add-ons** attached to the mods you play, with undo and updates.
- **Nexus download buttons** (`nxm://`) send files here, free accounts included; **Import tracked mods** links your Nexus tracking list to your packs and can install the ones you don't have.
- One-time setup after install (install scripts, *Setup UI images*, a game-folder zip) is offered, never run silently.
- Packs built from other mods (FRZN's Merge Modpack) get a guided, resumable dependency install.
- Installs and updates me3 and the Visual C++ runtime from their official sources.

### Playing

- One **PLAY** button; vanilla through Steam, mods through me3; a mod's own launcher (such as Convergence's) can be added as a target.
- **Before you play** check: missing files, skipped DLLs, an old Seamless, a mod that refused this game version last time, a save file last used by a different mod.
- **Watched launch**, session tracking, playtime and a launch history that can switch off whatever you changed since the last good launch.
- **Setup steps** (a randomizer, a config tool) run before the game, on your terms; **Quick launches** start a named mod + profile + on/off combination in one click.
- **Clean game folder**: for mods that break when ReShade or Elden Mod Loader files sit in the game folder, PLAY moves them aside and puts them back afterwards. Nothing is deleted.
- Self-managing mods (Convergence) are left alone: no profile edits, no repairs that would fight their launcher.
- Desktop shortcuts that start a mod directly.

### When something goes wrong

- Health check, profile check, **Fix problems** (undoable), **Why won't it start?**, last-launch report, **Doctor**, a requirements card for known mods, conflict check and file verification.
- Reads Windows crash records and offers to switch off the DLL to blame; **Find the cause** narrows a crash down by switching halves off.
- **Copy report** for help requests (personal paths removed); an error log with a *Copy details* dialog; *Report a problem* opens a pre-filled GitHub issue.
- **Go back to an earlier version** of Roundtable if an update misbehaves.

### Updates

- Mod updates from GitHub or Nexus with preview, backups and undo; patch-aware; the author's README steps are shown first; **Update from file...** for anything else.
- Add-on updates, me3 updates, game-patch awareness, and signed Roundtable updates (checked before anything is unpacked).
- A daily background check you can turn off.

### Co-op

- **Play with friends** checklist and invite; **Compare setups**; **Share my setup / Install a friend's setup** (a code, file or link); **Friends' setups** with a ready light per friend and a **Room** view.
- **Passwords and save files** in one window; **Seamless versions** sync; **Add Seamless Co-op** to any mod with its own save ending; change a save-file extension with the existing save copied across.
- **DLL presets** (and recommended sets) that never load a DLL twice; optional Discord posts that you approve first.

### Saves

- Automatic backups before every launch (and optionally every few minutes while you play), a second copy on another drive, restore, guarded deletes, character copying between saves, and a handoff to a save editor you already have for appearance changes. Roundtable never edits a save itself.

### Organising

- Components and load order, **Loadouts**, a tidy **Configuration** editor, favourites, tags and notes, **Organize DLL mods** (every mod gets its own copy, fully undoable), a **Known mods** list you can edit and share, setup backup and restore, and **Delete** that moves a mod aside (*Tools → Deleted mods* restores it).
- **Storage** and **Clean up downloads** with optional automatic limits.

### More games

- Elden Ring, **Elden Ring Nightreign** and **Dark Souls III** each keep their own mods folder, profiles and save backups. A game library finds the others you own; Dark Souls 1 and 2 get Play and save backups, and **Bloodborne** (the community Windows port) gets Play, a health check, every launcher setting and a controller check without touching the game files.

### Look and feel

- Twelve themes, a light theme, text size, fonts, corner style, motion levels, high contrast and colour-blind status colours; a first-run tour and a *Getting started* checklist; **Ctrl+K**, **Ctrl+F**, **Ctrl+N**, **Ctrl+Enter** and **F1**.

### Safety

- Every file Roundtable changes is backed up first, and the author's originals are kept.
- Archives that try to write outside their folder are rejected; releases are signed; your Nexus key and Discord webhook are stored encrypted with Windows' own protection.
- Online mode is never switched on for you.

---

## Questions

<details>
<summary><b>The game started but my mod isn't there / "ModEngine3 failed to load"</b></summary>
<br>
1. Press <b>Why won't it start?</b> on the mod's page, or open <b>Tools → PC check (Doctor)</b>. They list what's wrong in plain words and have buttons for the common fixes.<br>
2. Press <b>Fix problems...</b> on the mod's page.<br>
3. Make sure the mod is <b>not</b> inside a OneDrive folder, and that Roundtable and your mods aren't inside the Elden Ring game folder.<br>
4. Still stuck? Press <b>Check last launch</b>, then <b>Copy report</b>, and send it to whoever is helping you.
</details>

<details>
<summary><b>My friend can't join my game</b></summary>
<br>
Use <b>Play with friends → Compare setups</b> on both PCs. It lists what differs - Seamless version, DLLs, settings, password. The most common cause is a different Seamless Co-op version or password.
</details>

<details>
<summary><b>I changed a save-file ending and my character "disappeared"</b></summary>
<br>
The character is still in the old save file. In <b>Passwords and save files...</b> tick <i>copy the existing save to the new name</i> when you change an ending - or use the <b>Characters</b> page to copy it across afterwards.
</details>

<details>
<summary><b>Do I need Nexus Premium?</b></summary>
<br>
No. Free accounts work: use the <i>Mod Manager Download</i> button on a mod page. Premium adds fully automatic downloads.
</details>

<details>
<summary><b>Can I get banned?</b></summary>
<br>
Modded <b>online</b> play can get an account banned. Roundtable never turns online mode on and warns you if a profile has it. Play offline, or use Seamless Co-op, which is its own network.
</details>

<details>
<summary><b>Where does Roundtable keep my information? How do I uninstall it?</b></summary>
<br>
Your settings, Nexus key and backups are in the <code>data</code> folder next to <code>Roundtable.exe</code>. Nothing is uploaded. To uninstall, close Roundtable and delete its folder - your mods and saves are not touched. (me3 can be removed from Windows' <i>Installed apps</i>.)
</details>

<details>
<summary><b>What does it send over the internet?</b></summary>
<br>
It contacts GitHub (its own updates and me3), Nexus Mods, Microsoft (only if you ask it to install the Visual C++ runtime) and - only if you set one up - your Discord webhook. Mods are always downloaded from the author's own page; this project never hosts or shares mod files. Your Nexus key is only ever sent to nexusmods.com.
</details>

---

## Credits

An unofficial fan tool, not affiliated with FromSoftware, Bandai Namco, Nexus Mods, or the authors of me3 or Seamless Co-op - please support the mod authors whose work you install. Thanks to **me3 / ModEngine 3** (garyttierney), **Seamless Co-op** (LukeYui) and **ER-Save-Editor** (ClayAmore). *Elden Ring* is a trademark of FromSoftware / Bandai Namco. Screenshots show the game's artwork and the pictures mod authors publish on their Nexus pages; those belong to their owners. Third-party software is listed in `THIRD-PARTY-NOTICES.txt`.

**Found a bug or have an idea?** Open an [issue](https://github.com/Nexus-Primes/Roundtable/issues) and, if you can, paste the text from the *Copy report* button.
