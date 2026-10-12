# Releasing

1. Build SSM (`python build.py`) and SSI (Docker `devkitpro/devkita64`).
2. Make sure the output contains **no** `prod.keys`, `title.keys`, config with IPs, or personal paths.
3. Zip into `release/` and write `SHA256SUMS`:
   `Switch-Super-Manager-vX.Y.Z-win64.zip`, `Switch-Super-Installer-vX.Y.Z.nro`.
4. Tag `vX.Y.Z`, create a GitHub Release, attach the files and paste the matching CHANGELOG section.
5. `release/` is git-ignored: binaries live only in Releases.

Commits in this repo use the noreply identity configured locally.
