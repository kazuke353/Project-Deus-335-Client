# Project Deus - client files

Files for a World of Warcraft 3.3.5a (12340) enUS client.

## Install

1. **Code -> Download ZIP** (or the Download button on the website) and unzip everything in
   its folder into your WoW folder, replacing the files there.
2. Start `Wow.exe`.

`Wow.exe` is Blizzard's own, unmodified and signed by Blizzard. The Deus changes (classless
spells, the updater, the fixed realmlist, the login screen, animations) are in `dinput8.dll`:
Wow.exe loads a `dinput8.dll` from its own folder, and this one applies them in memory as the
game starts, then hands DirectInput to Windows' own dinput8.dll. Source:
`build_dll.py` and `loader/` in wow-3.3.5a-fix. `Logs/DeusLoader.log` says what it did.

At every start the game keeps `dinput8.dll` and the `Data/patch-*.MPQ` files up to date, restarts
itself into a new update when it sits at the login screen, clears `Cache/` when the realm's data
changes, and always connects to the Deus realm (no realmlist to edit). Its log is
`Logs/DeusUpdate.log`; `Wow.exe -noupdate` skips the check once.

Manual install (no updater, or to repair by hand): the files are listed in
https://warlordhermes.dynv6.net/client/manifest.txt and downloadable from
`https://warlordhermes.dynv6.net/client/files/<path>`; delete `Cache/` afterwards.

The patch archives are in this repo too (`Data/`), so the ZIP has the whole set.

## What the archives hold

| File | Contents |
| --- | --- |
| `patch-4.MPQ` | game data tables (DBC) for the classless realm |
| `patch-5.MPQ` | interface: Classless and Racials window, specs, glyph shop, Wilderness zone text, casino table, zone event tracker, dance emote commands, level-up unlocks display |
| `patch-6.MPQ` - `patch-9.MPQ` | cosmetics: models, textures and their data |
| `patch-A.MPQ` | transmogrification window |
| `patch-B.MPQ` | item stat rolls |
| `patch-C.MPQ` | spell, talent and item data; must load after the cosmetics archives |
| `patch-D.MPQ` | character models: every race kneels and feeds when channelling Cannibalize, and dances the Orange Justice (`/oj`) and Dance Moves (`/dm`, `/dancemoves`, `/defaultdance`) |
| `patch-E.MPQ` | login, character select and character create screens: the Deus keep in Stormwind |
