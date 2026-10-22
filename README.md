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
| **Keep your characters safe** | Backs up your saves automatically, can keep a second copy somewhere else, keeps two PCs in step without ever losing a character, lets you try a mod on a copy of your save, and asks twice before anything involving a save is deleted. |
| **Stay up to date** | Tells you when a mod, a DLL add-on, me3 or the manager itself has a new version - and updates without you leaving the app, one at a time or all at once with a restore point. |
| **Tidy up** | Shows which old downloads can go, and clears them only when you say so. |
| **Undo mistakes** | Almost everything it does is backed up and can be undone. |
| **Not know where to start** | Starter packs: Seamless Co-op, an overhaul to try, small DLL add-ons - with what you already have ticked off. |
| **Make mods** | Checks a mod folder before you publish it, packs it for Nexus, and writes the Requirements text for the page. |
| **Script it** | A command line (`Roundtable-cli.exe`) for checks, backups and launching from a script or a scheduled task. |

![Animated tour: picking mods, switching tabs, spotting an update and a problem](docs/images/clip-tour.png)

---

## Get started (about 5 minutes)

### 1. Download

Open the **[Releases page](https://github.com/Nexus-Primes/Roundtable/releases/latest)** and download the file ending in **`-windows.zip`** (it's listed under *Assets*).

### 2. Unzip it somewhere permanent

Right-click the zip and choose **Extract All...** into a simple folder such as `C:\Tools\Roundtable`.

> **Please don't** run it from inside the zip, from your *Downloads* or *Desktop*, from a **OneDrive** folder, or from inside the Elden Ring folder. Windows and OneDrive can lock or hide files there, which causes confusing errors.

### 3. Open `Roundtable.exe`

The first time, Windows may say **"Windows protected your PC"**. That's because the program isn't signed with a paid certificate. Click **More info**, then **Run anyway**.

### 4. Let it set itself up

![The Welcome window listing the three things to set up](docs/images/p-welcome.png)

On the first start the manager tells you what's missing. The things it needs are:

- **me3** (ModEngine 3) - the small program that actually loads mods into the game.
  In the manager choose **Tools → This program → Install or update me3...** and follow the installer's window like any other installer. When it closes, the manager finds it by itself.
- **The Microsoft Visual C++ runtime** - almost every DLL mod needs it. If it's missing, the same window offers to install it for you.

Then open **Settings** and make sure the **Mods folder** is the folder where your mods will live (an empty folder is fine - the manager will fill it).

![The Folders tab of Settings with the me3, Mods and game folders](docs/images/p-settings-folders.png)

### 5. (Optional but handy) Add your Nexus Mods key

A free Nexus Mods account lets the manager search for mods, show their pictures, and check for updates. To connect it you give the manager your **Personal API Key** - a long password-like code that Nexus makes for you. Most people have never seen it, so here is exactly where it is:

1. Go to [nexusmods.com](https://www.nexusmods.com) and **log in**. (No account yet? Sign-up is free.)
2. Click your **profile picture** in the top-right corner of the page.
3. Choose **Site preferences** (on some versions of the site the menu says *Account settings* or *Preferences*).
4. In the menu on the left, click **API Keys** (older versions call this tab **API**).
5. Scroll to the very bottom of that page to **Personal API Key**. If a key isn't shown yet, press the button there to **request / generate** one.
6. **Copy** the whole key - it is a long mix of letters and numbers, often ending in `==`.
7. In Roundtable open **Settings → Online**, paste it into **Nexus API key**, and press **Test key**. It tells you the account it belongs to and whether you have Premium.

![The Online tab of Settings with the Nexus API key and download buttons](docs/images/p-settings-online.png)

- **Treat it like a password.** Don't post it in screenshots, Discord or issue reports. The manager stores it encrypted on your PC and only ever sends it to nexusmods.com. If it ever leaks, request a new one on the same Nexus page and the old one stops working.
- **Free or Premium?** Both work. With a free account Roundtable opens the mod's Nexus page and you press Nexus's *Mod Manager Download* button (turn on **Nexus download buttons** in the same Settings tab); Premium accounts download fully automatically.
- **Can't find it?** Nexus occasionally renames menus. Look for anything called *API* in your profile or site preferences, or search "Personal API Key" in Nexus's help pages.

---

## Installing and playing your first mod

1. Press **＋ Install a mod** (bottom-left).
2. Either **search Nexus** and pick a mod, or choose a `.zip`, `.7z` or `.rar` you already downloaded (or just drag it onto the window).
3. Look over what the manager found, press **Install**. It repairs common problems for you and says what it did.
4. Click the mod in the list on the left and press **PLAY**.

![The Install a mod window on its From a file or folder tab](docs/images/p-install.png)

**Tip - the "Mod Manager Download" button.** In **Settings**, turn on **Nexus download buttons**. After that, the *Mod Manager Download* button on a Nexus mod page sends the file straight here. This works with free Nexus accounts, too.

**Some mods are "add-ons"** (small DLL files like free-camera or UI tweaks). When you install one, the manager offers to add it to the mods you already play instead of making it a separate mod.

### Not sure where to start?

*Tools → Mods → Starter packs...* (the Overview offers it while you have no mods) starts from **what you want to do**, not from a list of mods: *Play with friends*, *Handy extras*, *A whole new game (overhauls)*, and *Tools for making and fixing mods*. A **Before you start** strip checks the PC - me3, your Mods folder, the game, your Nexus key - and puts a button next to anything missing.

![The Starter packs window: goals instead of topics, with a before-you-start check](docs/images/p-starters-list.png)

Inside a pack every mod is a card with **its own picture, description, endorsements and downloads, read live from its Nexus page** - the manager doesn't write these itself - plus what you already have, what it needs (the Shadow of the Erdtree DLC, a runtime), and the one thing most worth knowing from the manager's own notes. A group is a clear **Pick ONE** (overhauls are made to be played on their own); everything else is **Add any of these**. **What happens next** says what the install does and what to do afterwards - for an overhaul, to try it on a copy of your save first. Nothing downloads until you press Install, and without internet the packs still show from the manager's own notes.

![A starter pack: four overhauls with their own pictures and descriptions, pick one](docs/images/p-starters.png)

### Some mods need one more step

If a mod's author says something must be run once before the first launch - an install `.bat`, a *Setup UI images* shortcut, a zip of DLLs meant for the game folder - the manager offers to do it right after the install. **Nothing runs until you press a button.** Each item opens in its own window, the manager waits for it to finish, checks that it worked, and lets you retry if it didn't.

![The Finish setting up window offering to run a mod's install script](docs/images/p-postinstall.png)

### Packs built from other mods

Some packs, like **FRZN's Merge Modpack**, are made by layering several other mods you download yourself. After you install one, the **Install the dependencies** window opens (or press the button on the pack's *What this mod needs* card):

1. Press **Get it** on each mod. A Premium Nexus account downloads it for you; a free account opens that file's Nexus page and the *Mod Manager Download* button there hands the file back. Already downloaded it? The manager spots it in your Downloads folder.
2. When all are ready, press **Build it**. Each is unpacked and layered in the order the author's instructions give, using the right old version where needed (FRZN needs McKenyu's 1.3.11, not the newest).

![The Install the dependencies window](docs/images/p-dependencies.png)

If a build stops, press **Build it** again - finished steps are remembered. When the pack later publishes an update file, apply it from the pack's **Updates** tab (*Update from file...*); the manager shows the author's steps first, then offers to move the update's files on top of the layers, with a backup of everything it replaces.

---

## A mod's page

![A mod's Overview tab with the health check and PLAY button](docs/images/p-modpage.png)

Click a mod in the list. The top shows its version, where it's published and whether it's ready. Under the **PLAY** button are four tabs:

- **Overview** - the health check, setup steps, and what happened on the last launch. On a known mod it also shows **What this mod needs**: a checklist for your PC (me3, the DLC, ray tracing, the game version) with a button next to anything that's missing, plus the author's own warnings. If the mod hasn't been updated since before your last game patch, it says so - the most common cause of a crash after a patch.
- **Components** - every DLL and asset folder the mod loads. Tick to switch one on, untick to switch it off; drag or use the arrows to change the load order. **Loadouts** saves named combinations, and **Check conflicts** finds two mods replacing the same files.
- **Configuration** - the mod's settings files as a tidy form (or raw text). Only the value you change is rewritten, so the file's comments and layout stay. Edited files are backed up first and the author's original is always kept.
- **Updates** - see [Keeping up to date](#keeping-up-to-date).

![The What this mod needs card with a checklist and the author's warnings](docs/images/p-needs.png)

![The Components tab listing a mod's DLLs with on and off ticks](docs/images/p-components.png)

![The Configuration tab showing a settings file as a form](docs/images/p-configuration.png)

### Pressing PLAY

Before the game starts, the manager looks the profile over and, if something is likely to go wrong, tells you in plain words and lets you decide.

![The Before you play window listing a missing DLL and an out-of-date Seamless Co-op](docs/images/p-prelaunch.png)

While the game runs, the button shows **RUNNING** (and blocks a second launch) and playtime is tracked per mod. A minute after the game starts the manager reads me3's log and tells you at once if it started *without* your mod, and why. Vanilla Elden Ring starts through Steam with Easy Anti-Cheat; mods start through me3.

---

## When something goes wrong

Start with the buttons on the mod's **Overview** tab:

- **Why won't it start?** collects every clue (including files Windows Defender removed) and lists the likely cause first.
- **Doctor** checks your whole PC: game folder, me3, the Visual C++ runtime, Steam, OneDrive and disk space.
- **Fix problems...** scans the mod and offers repairs you tick one by one - re-linking moved files, copying in a missing shared DLL, switching off files that can't work. Everything is backed up and **Undo last fix** reverses it.
- **Find the cause** (for a crashing game) switches half of a mod's DLLs and folders off, asks you whether it still crashes, and narrows it down to the one that matters. If Windows has recorded which DLL crashed, the manager offers to switch that one off for you.
- **DLL trust** (*More → DLL trust...*) says what each DLL a mod loads is and can do, read from the file without running it: its size and SHA-256 fingerprint, whether it is signed (and whether Windows says the signature is intact), and whether it can use the internet, start other programs or start code inside other programs - as facts, not accusations (Seamless Co-op *has* to use the internet; most mods are unsigned, and that says nothing bad). The part that matters most: press **I'm happy with these** once you trust a mod and from then on a DLL that was swapped, added or dropped out is called out. It never says a file is "safe" - it can't - it tells you what changed. *Look one up on VirusTotal...* opens the file's page by its fingerprint; nothing is uploaded.
- **Try on a copy of my save** (*More → Try on a copy of my save...*) is for a mod you aren't sure about. The mod is pointed at its own copy of your current save, so it plays on the copy and can never open your real characters; the mod page says **On trial** while it lasts. *More → Finish the trial...* puts the profiles back exactly as they were and keeps or deletes the copy (deleted saves go to a folder, after a snapshot). It works for plain profiles and Seamless Co-op ones.
- **Timeline** (*More → Timeline...* on a mod's page) is for "it worked yesterday - what changed?". It lists everything recorded about the mod, newest first - each launch and whether it worked, updates, repairs, DLL add-ons, and any game crash Windows recorded afterwards - and at the top shows what happened *since the last launch that worked*: the DLLs switched on or off since then, and a button to put the switches back as they were.

![A mod whose health check reports a missing DLL, with Why won't it start, Doctor and Fix problems buttons](docs/images/p-health.png)

![The Why won't it start window listing likely causes](docs/images/p-why.png)

![The Fix problems window with a repair to tick](docs/images/p-fix.png)

![The Find the cause window with the mod's DLLs ticked](docs/images/p-bisect.png)

![The Timeline window: what changed since the last launch that worked, then every launch, update and crash](docs/images/p-timeline.png)

![The DLL trust window: three DLLs, one swapped since the person said they were happy, one that can use the internet](docs/images/p-trust.png)

**Copy report** gathers everything for a help request, with personal paths removed. **Save report as zip...** (in *Why won't it start?*) makes one zip for a mod author or a helper: the findings, the versions, the mod's profile files, a list of its files and the tail of the logs - text only, with your Windows user name removed, and no saves, settings or Nexus key.

---

## Playing co-op with friends (Seamless Co-op)

Co-op only works when **everyone has the same mod versions, the same Seamless Co-op version, and the same password.** The manager makes that much less painful.

![The Play with friends window with a green checklist and an invite](docs/images/p-friends.png)

- **Play with friends → Ready to play?** on a mod's page shows a checklist (Seamless version, password, your own save file, me3, game version) and a ready-to-send **invite** you can copy or post to Discord.
- **Add Seamless Co-op...** (on the mod's *Components* tab) puts Seamless into a mod for you, with its own save file so characters never get mixed up.
- Friends who have the manager can use **Tools → Mods → Install a friend's setup** - paste the setup (or a link to it) you made with **Share my setup** and it downloads the same mod versions, adds your add-on DLLs, sets up Seamless Co-op, and switches the same DLLs on in the same order. The co-op password and settings files are only included if you tick them.
  Before it changes anything, the friend sees a plain list of what will change and can go back; **Tools → Backups and undo → Undo last friend's setup** reverses it. Tip: put your setup in a GitHub gist and send friends the link - when you change your setup you update the gist, and they just open *Install a friend's setup* and press *Read it* again.
- **Play with friends → Compare setups** finds out exactly *why* two people can't connect.
- **Friends' setups** (Tools → Mods) keeps your friends' setup links in one list and shows at a glance whether you match each of them, with a **Room** view that lines everyone up side by side.

![The Share my setup window with a list of mods and tick boxes](docs/images/p-share.png)

### Your DLL preset, without duplicates

Save the DLL mods you use everywhere as a **DLL preset** (*Tools → Mods → DLL presets...*) and add it to any mod in one click. Press **Edit...** on a preset to take DLLs out or add more, then overwrite it or save the result as a new preset; **Settings...** edits the settings files that come with it, so you can make a generic version to share. **Export...** packs a preset - its DLLs, their settings and its description - into one zip, and **Import file...** brings one in (it asks you to trust the sender first, never overwrites a preset with the same name, and refuses a damaged or unsafe zip). If a mod already has one of the same DLLs, the manager asks which copy to use - the mod's or yours - so nothing is ever loaded twice, and undoing it puts everything back.

![The DLL presets window: your presets on the left, the selected preset's DLLs and their settings on the right](docs/images/p-presets.png)

### All your passwords and save files in one place

![One window listing every Seamless Co-op instance with its password and save extension](docs/images/p-passwords.png)

**Tools → Seamless Co-op → Passwords and save files...** (also a button on the Overview page) lists every co-op setup on your PC as a card: its password, its save extension, the save file that becomes, and a badge that says whether it is fine. Change passwords and save-file endings there (even set one password for everything), see which ones clash, and let the manager give each mod its own. If you change a save ending, it can copy your existing save across so your character comes with you.

### Seamless versions

Seamless refuses to start when its DLL is out of date. **Tools → Seamless Co-op → Seamless versions...** lists every copy on your PC and updates the older ones from the newest.

![Every copy of ersc.dll with its version and status](docs/images/p-seamless.png)

---

## Your saves are protected

Roundtable backs up your saves before every launch, can keep a second copy somewhere else, and can **keep two PCs in step**: *Tools → Backups and undo → Sync saves with another folder...* compares your saves with a cloud-synced folder, a NAS or a USB stick and copies what changed, in both directions - and never by "newest wins", which is how characters get lost. It remembers each save's fingerprint from the last time both sides matched, so a save changed on only one side is copied across, and one changed on **both** sides is a conflict you decide, save by save. What a copy replaces is backed up first, copies are verified before they go into place, nothing happens while the game is running, and it only syncs when you press **Sync now**.

![The Sync saves window: a save to copy each way and one that changed on both sides](docs/images/p-sync.png)

![The Characters page listing the characters inside each save](docs/images/p-characters.png)

The **Characters** page (top of the list) shows every save file and the characters inside it.

- **Backups happen automatically** before you launch, and before anything that touches a save. Unchanged saves share space, so keeping many costs little. **Back up now** takes one on demand, and the manager can also back up every few minutes while the game runs (*Settings*).
- **A second copy** can be sent to another drive, a NAS or a cloud-synced folder (*Backups → Second copy*).
- **Copy a character** from one save to another - for example from your normal game into your co-op save - with *Copy this character to another save...*. It only works between saves from the same Steam account, checks everything first, and makes a backup first.
- **Deleting is guarded.** Deleting a character or a whole save file makes a protected backup first, shows you exactly what will go, and makes you **type the name** before it does anything. Deleted save files are moved aside, not erased, and *Backups → Restore* brings them back.
- Please **play offline** with copied or edited characters. Online play with mods can get an account banned, and the manager never turns online mode on by itself.

---

## Keeping up to date

![The Updates tab with an update available, release notes and Update, Undo and Check buttons](docs/images/p-updates.png)

- **Mods:** open a mod's **Updates** tab, or use *Tools → Check all for updates*. A badge appears in the list when a new version is out, and *Update to ...* downloads and applies it safely. *Undo last update* reverses it.
- **One button checks mods and DLL add-ons.** *Check for updates* on the Overview (and *Tools → Check all for updates*) looks at your mods and your DLL add-ons together, keeps saying *Checking...* until both are done, and ends with one line that names both - *"1 mod update and 2 DLL add-on updates available"* or *"Everything is up to date (checked 8 mods and 2 DLL add-ons)"* - so you can tell the DLLs were looked at. The Overview also shows when it last ran. It checks the game you are on, so switch games to check another game's mods. A linked mod that has no version recorded can't be compared, so the Overview lists it with the newest version on its page instead of leaving it out; enter the version you have on its **Updates** tab. The newest *file* on a Nexus page counts as well as the page's version number, because authors often upload a new file and leave the number on the page as it was. **DLLs a mod's author bundled** (Free Camera, Expanded Memory Slots and the other well-known ones from the *Main DLL Setup* list) are checked as well, even though they were never added as add-ons: by the version inside the DLL when it has one, otherwise by its file date against Nexus's newest main file. They are listed as *DLL inside <mod>* with an **Open page** button, since the manager can't swap a DLL that sits wherever the mod's author put it. A date-only match is a good guess, not a certainty. Elden Ring only.
- **DLL add-ons are checked too.** The DLLs you attached to your mods (when they came from a Nexus page) show up on the Overview page when a newer version is out. **Update...** can download and install it for you (Nexus Premium) in every mod that carries it, or open its Nexus page, or install a file you downloaded - with a backup first. An add-on that has no Nexus page (one made by a DLL preset) has a **Link to Nexus...** button so it can be checked as well.
- **Update all.** The Overview page's **Update all...** updates every mod that has an update in one go (Premium). It only does the safe cases - a mod that is linked to Nexus and whose new files line up with the old ones - and tells you why it left any other mod for you. Each mod is backed up, your changed settings are kept, and **Undo all of these** (or *Tools → Backups and undo → Undo last 'Update all'*) puts every one back.
- **Patches are found and applied safely.** Some mods publish a small patch for the previous version as well as the full download. The manager tells them apart and offers the patch only when it was made for exactly the version you have.
- **The author's instructions are read.** If an update comes with a README that explains how to apply it, the manager shows those steps before changing anything. *Update from file...* applies a download you made yourself.
- **me3:** the manager checks about once a day and tells you when a newer one is out - *Tools → This program → Update me3...*.
- **The game:** the manager remembers your `eldenring.exe` version. When a patch changes it you're told, and mods whose logs show they don't support it are marked.
- **What the manager knows about particular mods stays current.** The notes, requirements and layering recipes for the big overhauls (Reforged, Convergence, Reborn, Elden Vins, FRZN's pack and the rest) also arrive as a small **signed** file that the manager fetches about once a day, so a correction doesn't wait for a new release. It is checked against the same key that signs releases; a file that is unsigned, altered, older than the one it has, or meant for a newer manager is refused, and nothing in it is ever run - it is text and settings shown to you. Your own *Known mods list* still wins. *Tools → Health and storage → Known mods list* shows its version and has **Check for new notes now**; *Settings → Online* turns it off.
- **The manager itself:** when a new version is published, a banner appears in the sidebar. Click it and the manager downloads the update, checks its signature, restarts, and keeps all your settings and backups. If a new version ever misbehaves, **Tools → This program → Go back to an earlier version...** returns to the one you had before.

### The Overview page

![The Overview page with updates for a mod and a DLL add-on, and a mod older than the game's last patch](docs/images/p-overview.png)

The first thing to open each day. It counts your mods, lists every update waiting (mods **and** DLL add-ons), and has a card for mods that are **older than the game's last patch** - the most common reason for a crash at start-up, so it tells you before you find out the hard way. Under *Your mods* a filter - *All mods / Needs attention / Has an update / Older than the game patch* - narrows the table or the cards to the ones that need a look.

![The Update all summary: two mods updated, one skipped, with Undo](docs/images/p-updateall.png)

### Quietly in the background (optional)

Turn on *Settings → Updates and safety → In the background* and closing the window hides it next to the clock instead of quitting. The manager keeps running, so its checks go on - mod, DLL add-on and Roundtable updates once a day, the game's version every half hour - and a **Windows notification** appears when one finds something, or when a friend you follow by link changes their shared setup. A notification shows only when the window is hidden or isn't the one you're using, never twice in a day for the same news, and clicking it opens the window. Right-click the icon for **Open**, **Check for updates now** and **Quit**; starting Roundtable again brings the hidden window back instead of opening a second one. Playtime is still counted. It is off until you turn it on.

![The Updates and safety tab of Settings, with the option to keep Roundtable in the tray and the automatic setup backup](docs/images/p-settings-updates.png)

### The game's own settings

Some mods ask for borderless window or ray tracing off, buried in the game's menus. *Tools → Health and storage → Game settings...* shows the game's graphics settings and changes just those: the screen mode, and switching off motion blur, depth of field, anti-aliasing or ray tracing. Only the one setting is replaced - the rest of the file stays byte for byte as it was - the file is backed up first, the last change can be undone, and nothing is written while the game runs. A mod that asks for borderless or ray tracing off has an **Open game settings...** button on its requirements card.

![The Game settings window: screen mode, and picture effects that can be switched off](docs/images/p-gamesettings.png)

### Finding things

Press **Ctrl+K** and type a few letters to jump to any mod or tool; **F1** lists the keyboard shortcuts. **All tools...** lists every tool and setting on tabs, with a search box.

![Animated: typing a few letters in the Go to window finds a tool](docs/images/clip-search.png)

![The All tools window with a search box and tools grouped on tabs](docs/images/p-alltools.png)

Everything else lives in the **Tools** menu, grouped by topic:

![The Tools menu, grouped, with the Seamless Co-op group open](docs/images/p-tools-menu.png)

### Tidying up

*Tools → Storage... → Choose downloads to delete...* lists every downloaded archive with why it can go: the mod is already installed, it's an older copy, or it was used to build a layered pack (kept unless you tick it, because a rebuild needs it again). Older copies are ticked for you, and **nothing is deleted until you confirm**. Installed mods are never touched. In *Settings → Updates and safety* you can also keep only the newest few archives per mod and trim old backups automatically - both are off by default.

![The Clean up downloads window](docs/images/p-cleanup.png)

### More than one game

The box at the top of the sidebar switches between **Elden Ring**, **Elden Ring Nightreign** and **Dark Souls III** - each keeps its own mods folder, profiles and save backups, and the manager launches the right game through me3. **All games...** shows every supported game as a card; Dark Souls 1 and 2 get Play and save backups, and **Bloodborne** (the community Windows port) gets Play, a health check, every launcher setting and a controller check, without touching the game files.

---

## Make it yours

Open **Tools → This program → Appearance...** and pick a theme. Each one is a complete colour scheme named after something from the Lands Between:

![The Appearance window with twelve themes to choose from](docs/images/p-appearance.png)

Click a theme and the whole manager changes straight away - **Cancel** puts everything back, **Save** keeps it.

**Interface size** scales *everything* - text, buttons, pictures and spacing, not just the lettering - from 80% up to what your screen can hold, and it changes the moment you press Save (no restart). Pop-up windows and menus wear a cool slate-and-arcane-blue look, whatever theme the main window has, so you always know which window you are in; warnings stay amber, problems red and good news green.

![The manager in each of the twelve themes](docs/images/themes.png)

<details>
<summary><b>See every theme at full size</b></summary>

**Erdtree**

[![Erdtree theme](docs/images/theme-erdtree.png)](docs/images/theme-erdtree-full.png)

**Tree Sentinel**

[![Tree Sentinel theme](docs/images/theme-tree_sentinel.png)](docs/images/theme-tree_sentinel-full.png)

**Night's Cavalry**

[![Night's Cavalry theme](docs/images/theme-nights_cavalry.png)](docs/images/theme-nights_cavalry-full.png)

**Carian Knight**

[![Carian Knight theme](docs/images/theme-carian_knight.png)](docs/images/theme-carian_knight-full.png)

**Black Knife Assassin**

[![Black Knife Assassin theme](docs/images/theme-black_knife.png)](docs/images/theme-black_knife-full.png)

**Crucible Knight**

[![Crucible Knight theme](docs/images/theme-crucible_knight.png)](docs/images/theme-crucible_knight-full.png)

**Starscourge Radahn**

[![Starscourge Radahn theme](docs/images/theme-radahn.png)](docs/images/theme-radahn-full.png)

**Dark Moon Ranni**

[![Dark Moon Ranni theme](docs/images/theme-ranni.png)](docs/images/theme-ranni-full.png)

**Lord of Blood**

[![Lord of Blood theme](docs/images/theme-mohg.png)](docs/images/theme-mohg-full.png)

**Scarlet Rot**

[![Scarlet Rot theme](docs/images/theme-scarlet_rot.png)](docs/images/theme-scarlet_rot-full.png)

**Haligtree**

[![Haligtree theme](docs/images/theme-haligtree.png)](docs/images/theme-haligtree-full.png)

**St. Trina's Lily**

[![St. Trina's Lily theme](docs/images/theme-trina.png)](docs/images/theme-trina-full.png)

</details>

Prefer to mix your own? Choose **Custom mix** and pick any accent colour (or your own) and one of four colour schemes. You can also change the **text size**, the **font**, how **rounded** the corners are, the **width of the mod list**, how much **animation** you want (Off, Calm, Fluid, Lavish), switch on a **high-contrast** mode, or use **colour-blind friendly status colours** (blue / yellow / orange instead of green / amber / red).

---

## If you make mods

Open your mod in the manager and choose **More → For mod authors...** before you publish it:

- **It checks the folder** for what makes a mod fail on someone else's PC: paths that only exist on yours (`C:/Users/you/...`), a path spelled with different letters than the file (fine on Windows, broken elsewhere), paths that climb out of the folder, a profile with no `profileVersion` or no game, parts left switched off, a DLL that is damaged or needs the developer's debug runtime, logs and backup files that shouldn't ship, and a missing readme. Each finding says what it means and what to do.
- **It packs the zip** for Nexus: everything inside one tidy folder named after the mod and its version, with the leftovers (logs, `.bak`, `.git` and the like) left out unless you tick them in. The zip is made beside your mod, never inside it, and nothing in your mod's folder is changed.
- **It writes the Requirements text** for the Nexus page - the game and its version, Mod Engine 3, the Visual C++ runtime if one of your DLLs needs it, the DLLs and the profile to start - in the formatting Nexus understands (**Copy the Requirements text** puts it on the clipboard; it is also saved beside the zip).

![The For mod authors window: checks on a mod folder, then the options for packing it for Nexus](docs/images/p-authors.png)

---

### Tools for making mods - installed from Nexus or GitHub

In *Tools → Mods → My tools*, **Add a tool...** offers **Get a known tool (Nexus / GitHub)...** next to *I already have the program*. It lists the modding tools other modders use - **Smithbox**, **WitchyBND**, **Nuxe**, **Yapped Rune Bear SE** and **Elden Ring Save File Manager** (and Yapped for Dark Souls III) - each with its author's own description and numbers from its Nexus or GitHub page, so there is nothing to search for. Which tools show depends on the game: Nuxe and the save file manager cover several.

![The Get a tool window: modding tools with Install buttons for the places each is published, and WitchyBND saying it goes with Nuxe](docs/images/p-toolcatalog.png)

**Install** downloads the newest file, unpacks it into a `Tools` folder next to your Mods folder, finds the program inside and adds it to My tools. Nothing is run - you start it yourself. A **Premium** Nexus account installs in one click; with a free account the window opens the Nexus page and installs the file the moment you press **Mod Manager Download** there (or you can **Install from GitHub** when the tool has a release there). Several programs in one download and no clear choice? You're asked. A newer version shows **Update available**, and an update keeps the old folder as `.previous`. Downloads come only from GitHub and Nexus over https, and an archive that tries to write outside its folder is refused.

**Tools that go with each other.** WitchyBND's own page lists **Nuxe** - a separate program that unpacks the game's archives - under Requirements, so its card says so and offers **Get Nuxe too**; the first time you install WitchyBND the manager also asks whether to get Nuxe. Each is its own download with its own question, and saying no installs only the one you chose.

**Elden Ring Save File Manager** (by Hapfel) is the save editor on offer: when you install it, the **Characters** page finds it for its *Back up, then open the save editor* handoff, whatever its file is called. The Characters page's **Get a save editor...** button opens this list.

---

## On the command line

`Roundtable-cli.exe` sits next to `Roundtable.exe`. It is for scripts, scheduled tasks and "run this and paste what it says" support. It uses the same code as the window, never opens the window, and changes nothing of yours unless you ask (`launch`, the backups and `package` write files).

| Command | What it does |
|---|---|
| `status` | The game and its version, Mod Engine 3, the mods folder, and which mods need attention. |
| `list` | Every mod with its health, version and DLLs. |
| `check [mod]` | The PC check, plus that mod's checks. `--anonymize` hides your user name and folders, so it is safe to paste into a help request. |
| `launch <mod>` | Starts a mod like its desktop shortcut does (`vanilla` starts the unmodded game). |
| `backup-saves` · `backup-setup [file]` | Back up your saves now, or the manager's own setup (never your Nexus key) to a zip. |
| `timeline <mod>` | Launches, updates, repairs and crashes of one mod. |
| `lint <mod>` · `package <mod> <zip>` | The mod-author checks, and the Nexus zip. |
| `trust <mod>` | What each DLL of a mod is and can do, and whether one changed (exit 1) since you last noted them; `--remember` notes them. |
| `game-settings` | Show or change the screen mode and picture effects (`--screen-mode borderless`, `--off ray-tracing`, `--undo`). |
| `sync-saves` | Compare your saves with another folder; `--apply` keeps them in step (`--prefer local\|other` settles conflicts; exit 1 if something is left to decide). |
| `trial <mod>` | Try a mod on a copy of your save (`--start`), then go back (`--finish`, `--delete-save`). |
| `starters [pack]` | The starter packs, and what you have of each. |
| `tools [key]` | The installable modding tools; `tools KEY --install [--from nexus\|github]` gets one and adds it to My tools. |
| `feed [--refresh]` | The signed list of known mods the manager downloads once a day. |

Add `--json` for output a program can read and `--game <id>` (`eldenring`, `nightreign`, `darksouls3`, `sekiro`, `armoredcore6`) for another game; part of a mod's name is enough. **Exit codes:** `0` fine, `1` problems found (`check`, `lint`, `status`), `2` wrong usage, `3` couldn't do it - so a scheduled `Roundtable-cli.exe check` can fail a job when something is wrong. `Roundtable.exe --cli ...` and `python -m er_mod_manager --cli ...` work too, but only `Roundtable-cli.exe` is a program a terminal waits for and gets an exit code from.

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
- **Starter packs** by goal, for people who don't know where to start: a before-you-start check, each mod's own picture and description read live from Nexus, what you have and what each needs, pick-one groups for overhauls, and what to do next.
- **Get a known tool**: Smithbox, WitchyBND, Nuxe, Yapped Rune Bear SE and Elden Ring Save File Manager installed from Nexus or GitHub straight into My tools, with update detection and companion tools offered together (WitchyBND + Nuxe).

### Playing

- One **PLAY** button; vanilla through Steam, mods through me3; a mod's own launcher (such as Convergence's) can be added as a target.
- **Before you play** check: missing files, skipped DLLs, an old Seamless, a mod that refused this game version last time, a save file last used by a different mod.
- **Watched launch**, session tracking, playtime and a launch history that can switch off whatever you changed since the last good launch.
- **Setup steps** (a randomizer, a config tool) run before the game, on your terms; **Quick launches** start a named mod + profile + on/off combination in one click.
- **Clean game folder**: for mods that break when ReShade or Elden Mod Loader files sit in the game folder, PLAY moves them aside and puts them back afterwards. Nothing is deleted.
- Self-managing mods (Convergence) are left alone: no profile edits, no repairs that would fight their launcher.
- Desktop shortcuts that start a mod directly.

### When something goes wrong

- A warning when a mod is older than your last game patch - on the mod, and as a card and a filter on the Overview; health check, profile check, **Fix problems** (undoable), **Why won't it start?**, last-launch report, **Doctor**, a requirements card for known mods, conflict check and file verification.
- Reads Windows crash records and offers to switch off the DLL to blame; **Find the cause** narrows a crash down by switching halves off.
- **DLL trust** for each mod (what each DLL is and can do, and whether it is still the file you looked at) and **Try on a copy of my save** (an isolated trial that can't touch your real characters).
- **Timeline** for each mod: every launch (did it work?), update, repair, add-on and crash in one list, and *what changed since the last launch that worked*.
- **Copy report** and **Save report as zip...** for help requests (personal paths removed); an error log with a *Copy details* dialog; *Report a problem* opens a pre-filled GitHub issue.
- **Go back to an earlier version** of Roundtable if an update misbehaves.

### Updates

- Mod updates from GitHub or Nexus with preview, backups and undo; patch-aware; the author's README steps are shown first; **Update from file...** for anything else.
- DLL add-on updates (shown on the Overview, with **Update...** and a Premium one-click install, and **Link to Nexus...** for add-ons without a page), **Update all** with a restore point and undo, me3 updates, game-patch awareness, and signed Roundtable updates (checked before anything is unpacked).
- A daily background check you can turn off, and an optional **tray mode** that keeps checking with the window closed and tells you with a Windows notification.
- What the manager knows about particular mods arrives between releases as a **signed** file (corrections, new overhauls); it can be turned off.

### Co-op

- **Play with friends** checklist and invite (with an optional "When are you playing?" line at the top); **Compare setups**; **Share my setup / Install a friend's setup** (a code, file or link); **Friends' setups** with a ready light per friend and a **Room** view.
- **Passwords and save files** in one window; **Seamless versions** sync; **Add Seamless Co-op** to any mod with its own save ending; change a save-file extension with the existing save copied across.
- **DLL presets** (and recommended sets) that never load a DLL twice and can be exported and imported as one file; optional Discord posts that you approve first.

### Saves

- Automatic backups before every launch (and optionally every few minutes while you play), a second copy on another drive, **two-way sync** with a cloud folder or another PC (conflicts are always your choice), restore, guarded deletes, character copying between saves, and a handoff to a save editor you already have for appearance changes. Roundtable never edits a save itself.

### Organising

- Components and load order, **Loadouts**, a tidy **Configuration** editor, favourites, tags and notes, **Organize DLL mods** (every mod gets its own copy, fully undoable), a **Known mods** list you can edit and share, setup backup and restore, and **Delete** that moves a mod aside (*Tools → Deleted mods* restores it).
- **Storage** and **Clean up downloads** with optional automatic limits.
- **Game settings** (*Tools → Health and storage*): borderless window and the picture effects mods ask for, with backup and undo.
- **My tools** (*Tools → Mods → My tools...*): register Smithbox, a hex editor, Blender or any program - or install a known modding tool from Nexus or GitHub - and open a mod's folder in it from the mod's **More** menu.
- **Automatic setup backup** (every 7 days by default, never your Nexus key) and restore from *Tools → Backups and undo*.

### For mod makers and scripts

- **For mod authors...** checks a mod folder, packs it for Nexus and writes the Requirements text. **`Roundtable-cli.exe`** runs the checks, backups, timeline and launch from a script, with `--json` and exit codes.

### More games

- Elden Ring, **Elden Ring Nightreign** and **Dark Souls III** each keep their own mods folder, profiles and save backups. A game library finds the others you own; Dark Souls 1 and 2 get Play and save backups, and **Bloodborne** (the community Windows port) gets Play, a health check, every launcher setting and a controller check without touching the game files.

### Look and feel

- Works from the keyboard (Tab, Enter, Escape, a visible focus outline) and names every setting for screen readers.
- Twelve themes, a light theme, **interface size** (everything scales, live), text size, fonts, corner style, motion levels (a first run follows Windows' own *show animations* setting), high contrast and colour-blind status colours; a first-run tour and a *Getting started* checklist; **Ctrl+K**, **Ctrl+F**, **Ctrl+N**, **Ctrl+Enter** and **F1**.

### Safety

- Every file Roundtable changes is backed up first, and the author's originals are kept.
- Archives that try to write outside their folder are rejected; releases are signed; your Nexus key and Discord webhook are stored encrypted with Windows' own protection.
- Online mode is never switched on for you.

---

## Something went wrong?

<details>
<summary><b>The game started but my mod isn't there / "ModEngine3 failed to load"</b></summary>

1. Press **Why won't it start?** on the mod's page, or open **Tools → Health and storage → PC check (Doctor)**. They list exactly what's wrong in plain words and have buttons for the common fixes (install me3, install the Visual C++ runtime, find me3).
2. On the mod's page press **Fix problems...** - it repairs moved files, switches off mod files that can't work, and so on.
3. Make sure the mod is **not** inside a OneDrive folder, and that the manager and your mods aren't inside the Elden Ring game folder.
4. Still stuck? On the mod's page press **Check last launch**, then **Copy report**, and send it to whoever is helping you (personal paths are removed from the report).
</details>

<details>
<summary><b>Windows says "Windows protected your PC"</b></summary>

Click **More info → Run anyway**. The program isn't signed with a paid certificate, which is all this warning means.
</details>

<details>
<summary><b>My friend can't join my game</b></summary>

Use **Play with friends → Compare setups** on both PCs. It lists what differs - Seamless version, DLLs, settings, password. The most common cause is a different Seamless Co-op version or a different password.
</details>

<details>
<summary><b>I changed a save-file ending and my character "disappeared"</b></summary>

The character is still in the old save file. In **Tools → Seamless Co-op → Passwords and save files...** tick *copy the existing save to the new name* when you change an ending - or use the **Characters** page to copy it across afterwards.
</details>

<details>
<summary><b>Where does the manager keep my information? How do I uninstall it?</b></summary>

Your settings, Nexus key and backups are in the **`data`** folder next to `Roundtable.exe`. Nothing is uploaded. To uninstall, close the manager and delete its folder - your mods and saves are not touched. (me3 can be removed from Windows' *Installed apps*.)
</details>

<details>
<summary><b>Do I need Nexus Premium?</b></summary>

No. Free accounts work: use the *Mod Manager Download* button on a mod page (see above). Premium accounts additionally get fully automatic downloads.
</details>

<details>
<summary><b>Can I get banned?</b></summary>

Modded **online** play can get an account banned. The manager never switches online mode on by itself, and warns you if a profile has it enabled. Play offline, or use Seamless Co-op, which is its own separate network.
</details>

---

## Privacy and safety

- Your Nexus key and Discord webhook stay on your PC, stored **encrypted with Windows' own protection**, and are only sent to nexusmods.com / discord.com.
- **Updates are signed.** The manager refuses an update whose signature doesn't check out.
- The manager contacts GitHub (to check for its own updates and for me3, and once a day for the small signed file of mod notes - two public files, nothing about you is sent; *Settings → Online* turns it off), Nexus Mods, Microsoft (only if you ask it to install the Visual C++ runtime) and - only if you set one up - the Discord webhook you choose. It does not send your files or saves anywhere. The command line and tray notifications use the same checks as the window; notifications are made by Windows on your PC. The tool catalog and starter packs read each mod's or tool's public page (Nexus listing, GitHub repository) to show its own description - nothing about you is sent. DLL trust reads files and never uploads them (the VirusTotal link carries only a fingerprint, and only when you click it); save sync copies files only between your own folders, only when you press Sync now.
- Mods are always downloaded from the author's own page. This project never hosts or re-shares mod files.
- Nothing that touches your saves or your mods is done without a backup, and the common ones can be undone from inside the app.

## Credits and notes

This is an unofficial fan tool. It is not affiliated with FromSoftware, Bandai Namco, Nexus Mods, or the authors of me3 or Seamless Co-op - please support the mod authors whose work you install.

Thanks to **me3 / ModEngine 3** (garyttierney), **Seamless Co-op** (LukeYui), and the open-source **ER-Save-Editor** (ClayAmore, Apache-2.0), whose documentation of the save format made the character tools possible.

*Elden Ring* is a trademark of FromSoftware / Bandai Namco. Screenshots show the game's artwork and the pictures mod authors publish on their Nexus pages; those belong to their owners. Third-party software in the program is listed in `THIRD-PARTY-NOTICES.txt`.

**Found a bug or have an idea?** Open an **[Issue](https://github.com/Nexus-Primes/Roundtable/issues)** and, if you can, paste the text from the manager's *Copy report* button.
