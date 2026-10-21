# Roundtable mod-knowledge feed

`recipes.json` is what Roundtable knows about particular mods - which profile to start, which DLLs never load, what an overhaul needs, how it updates,
how a layered pack is built. Roundtable downloads it about once a day, so a correction or a new overhaul doesn't need a new release.

* `recipes.json` is signed (`recipes.json.sig`) with the same key that signs Roundtable releases. A manager refuses a feed whose signature doesn't check
  out, refuses one older than the one it has, and drops any entry that is malformed. It is data only: nothing in it is ever run.
* `recipes.src.json` is the editable list the signed file is made from. **To suggest a correction or a new mod, open a pull request that edits it**
  (or open an issue with the details). It is reviewed, then signed and published; nobody's manager accepts an edit that isn't signed.
* Each entry looks like the ones in the file: `match` (part of the mod's folder name), and any of `title`, `nexus_id`, `notes`, `steps`, `update`,
  `warnings`, `requires`, `game_build`, `launch`, `bad_dlls`, `hands_off`, `clean_game_folder`, `default_profile`, `game` ...
* What is sent when a manager fetches it: a plain request for two small public files. No account, no key, nothing about the user.
