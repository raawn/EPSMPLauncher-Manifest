# EPSMPLauncher-Manifest

Remote mod/version manifest for [EspacePlaisir Launcher](https://github.com/raawn/EPSMP-Launcher).

## How to push an update to every user

1. Edit `manifest.json`:
   - Bump `modpackVersion` (any change to this value triggers a re-sync on every launcher).
   - Add/remove/update entries in `mods`.
   - Leave `minecraftVersion` / `fabricLoaderVersion` as `"latest"` to always track the newest release, or pin an exact version string.
2. Upload the corresponding mod jar(s) into `mods/`.
3. For each mod entry, set:
   - `url` to the jar's raw GitHub URL, e.g. `https://raw.githubusercontent.com/raawn/EPSMPLauncher-Manifest/main/mods/<file>.jar`
   - `sha256` to the jar's SHA-256 hash (e.g. `sha256sum <file>.jar` or `Get-FileHash <file>.jar -Algorithm SHA256`)
4. Commit and push. No launcher rebuild or release is required.

See [manifest.json](manifest.json) for the current schema, and
[EPSMP-Launcher/docs/modmanifest.md](https://github.com/raawn/EPSMP-Launcher/blob/main/docs/modmanifest.md)
for how the launcher consumes this file.
