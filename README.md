# Project Deus - client files

Files for a World of Warcraft 3.3.5a (12340) enUS client.

## Install

1. Put `Wow.exe` in your WoW folder in place of the old one (keep a copy of the original if you like).
2. Start it. The first start downloads the `Data/patch-*.MPQ` files from
   https://warlordhermes.dynv6.net/client/ before the game opens.

From then on `Wow.exe` keeps itself and the patch files up to date at every start, restarts
itself into a new update when it sits at the login screen, clears `Cache/` when the realm's
data changes, and always connects to the Deus realm (no realmlist to edit). Its log is
`Logs/DeusUpdate.log`; `Wow.exe -noupdate` skips the check once.

Manual install (no updater, or to repair by hand): download the archives from
`https://warlordhermes.dynv6.net/client/files/Data/<name>` (list:
https://warlordhermes.dynv6.net/client/manifest.txt) into your `Data/` folder and delete `Cache/`.

## What the archives hold (downloaded by Wow.exe)

| File | Contents |
| --- | --- |
| `patch-4.MPQ` | game data tables (DBC) for the classless realm |
| `patch-5.MPQ` | interface: Classless and Racials window, specs, glyph shop, Wilderness zone text, casino table |
| `patch-6.MPQ` - `patch-9.MPQ` | cosmetics: models, textures and their data |
| `patch-A.MPQ` | transmogrification window |
| `patch-B.MPQ` | item stat rolls |
| `patch-C.MPQ` | spell, talent and item data; must load last |
