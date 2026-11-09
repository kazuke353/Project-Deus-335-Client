# Optional graphics packs

Served by the website at /client/optional.txt and /client/optional/<pack>/<file> (deus-web app/clientdist.py);
never part of the updater manifest. Players turn the packs on in Esc > Interface > AddOns > Deus Graphics (/graphics);
the loader (DivxDecoder.dll, wow-3.3.5a-fix loader/gfx.c) downloads them in the background into Data\Optional\.

- `packs.json`: what each pack holds (written by azerothcore tools/client-patch/build_optional.py packs).
- `sources.json`: the third-party archives' pins (size, sha256, the host's ETag). The host re-uploads them without
  notice; the server's deus-hd-watch.timer (azerothcore tools/client-patch/hd_sources_watch.py) notices within
  10 minutes, downloads the new copy once, rebuilds our archives on it, re-pins and commits here by itself. Players
  always download those archives from the host, never from our server.
- `HD/`: our merged tables + HD character models with the Deus animations (the HD archives themselves come
  from their own host).
- `Forever/`: merged Light tables + LuxVelum (https://github.com/Raz0r1337/Luxvelum, GPL-3.0, release build-1;
  licence in LuxVelum-LICENSE.txt). Our LuxVelum.ini defaults: Overlay=0 (settings live in the game's options
  instead of Ctrl+F7), ForeverGlow=1, ColorGrading=0.5.

The big files here are not committed (see .gitignore); they are rebuilt by build_optional.py.
