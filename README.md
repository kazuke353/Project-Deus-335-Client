# Project Deus - client files

Files for a World of Warcraft 3.3.5a (12340) enUS client.

## Install

1. **Code -> Download ZIP** (or the Download button on the website) and unzip everything in
   its folder into your WoW folder, replacing the files there.
2. Start `Wow.exe`.

From then on the game keeps itself and the `Data/patch-*.MPQ` files up to date at every start,
restarts itself into a new update when it sits at the login screen, clears `Cache/` when the
realm's data changes, and always connects to the Deus realm (no realmlist to edit). Its logs are
`Logs/DeusUpdate.log` and `Logs/DeusLoader.log`; `Wow.exe -noupdate` skips the update check once.

`Wow.exe` here is Blizzard's own. The Deus changes are in `DivxDecoder.dll`, which carries
Blizzard's DivX decoder inside it (source: `build_dll.py` and `loader/` in wow-3.3.5a-fix).

## What the archives hold

| File | Contents |
| --- | --- |
| `patch-4.MPQ` | game data tables (DBC) for the classless realm |
| `patch-5.MPQ` | interface: Classless and Racials window, specs, glyph shop, Wilderness zone text, casino table, zone event tracker, dance emote commands, songs and icons, level-up unlocks display, zone level ranges on the world map, energy and rage bars |
| `patch-6.MPQ` - `patch-9.MPQ` | cosmetics: models, textures and their data |
| `patch-A.MPQ` | transmogrification window |
| `patch-B.MPQ` | item stat rolls |
| `patch-C.MPQ` | spell, talent and item data (dance items and their icons too); must load after the cosmetics archives |
| `patch-D.MPQ` | character models: every race kneels and feeds when channelling Cannibalize, and dances 114 Fortnite dances with moving fingers (`/oj`, `/dm`, `/getgriddy`, `/floss`... one command per dance name) |
| `patch-H.MPQ` | animations ported from Cataclysm Classic |
| `patch-I.MPQ` | the dances' songs (113 of them; `/dancemusic` turns them off) |
| `patch-J.MPQ` | the later dances' animations (patch-D would pass GitHub's 100 MB file limit) |
| `patch-E.MPQ` | login, character select and character create screens: the Deus keep in Stormwind; creation in three steps (race, appearance, homeland - start in any of the eight starting zones) |
| `patch-F.MPQ` | dungeon and raid maps for Classic and Burning Crusade instances ([WDM-patch](https://github.com/Trimitor/WDM-patch) 2.4.5 by Trimitor, shipped as `patch-enUS-M.MPQ` there) |
| `patch-G.MPQ` | the Collections window (Shift-P, or the horse button on the menu bar): Mounts, Pets, Toy Box and Appearances, shared by every character on the account; "Already known" on the tooltips of cosmetics the account has |
| `patch-L.MPQ` | gear with the look of later expansions (retail transmog sets): models, body textures and the 3D pieces WarcraftXL Equip Plus draws |

## WarcraftXL

`WarcraftXL.dll` and `Extensions/` are [WarcraftXL](https://github.com/WarcraftXL/wxl-core) and two of its
extensions, loaded by the Deus updater when the game starts. All three are free software under the GNU General
Public License v3; their source is in the linked repositories.

| File | What it does |
| --- | --- |
| `WarcraftXL.dll` | [wxl-core](https://github.com/WarcraftXL/wxl-core) v1.1.276 (release build) |
| `Extensions/wxl-equip-plus/` | [Equip Plus](https://github.com/TheDaveCalaz/wxl-equip-plus) v1.3.0: 3D models on every armour slot (belt buckles, gauntlets, boots) |
| `Extensions/wxl-unit-outline/` | [Unit Outline](https://github.com/WarcraftXL/wxl-unit-outline) (branch v1.1, commit 4e8123e, built for Deus): a coloured outline around your target and the unit under the mouse |
