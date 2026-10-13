# Releasing

1. Build SSM (`python build.py`) and SSI (`build_docker.ps1`, Docker `devkitpro/devkita64`).
2. Make sure the output contains **no** `prod.keys`, `title.keys`, config with IPs, or personal paths.
3. Zip into `release/` and write `SHA256SUMS`:
   `Switch-Super-Manager-vX.Y.Z-win64.zip`, `Switch-Super-Installer-vX.Y.Z.nro`.
4. Tag `vX.Y.Z`, create a GitHub Release, attach the files and paste the matching CHANGELOG section.
5. `release/` is git-ignored: binaries live only in Releases.

Commits in this repo use the noreply identity configured locally.

## Release text of Switch-Super-Installer

> # Switch-Super-Installer v1.0.0
>
> Companion homebrew for **Switch-Super-Manager (SSM)**. Install and manage content on your Switch over your local network.
>
> ## What's new compared to TinWoo and Awoo
> - Install from an SSM library over LAN, with a game list, covers and multiple selection
> - Console inventory sent to SSM (installed titles, SD/NAND space, MAC), also on request
> - Cheats receiver (HTTP, port 2003)
> - Optional remote management: install, uninstall and save backups from SSM without on-console confirmation (sessions expire after 10 minutes)
> - Option to keep the console awake while charging
> - Free SD/NAND space shown on the install screen
> - Themes (Default, Dreamcast Grey, and your own in `themes/<name>/theme.json`), backgrounds, logo and sounds
> - Latest sigpatches fetched automatically
> - Reproducible Docker build (`build_docker.ps1`)
>
> ## Install
> Copy `Switch-Super-Installer.nro` to `/switch/` on your SD card and launch it from the album (full-memory mode, not applet mode).
>
> ## Source code and license
> Switch-Super-Installer is free software under the **GNU GPL v3**. Source code for this exact release: this repository at tag `v1.0.0`. Build: see `build_docker.ps1`.
>
> It is built on TinWoo by MrDude, which merges Tinleaf and [Awoo Installer](https://github.com/Huntereb/Awoo-Installer) by Huntereb (based on [Adubbz's Tinfoil](https://github.com/Adubbz/Tinfoil), using [XorTroll's Plutonium](https://github.com/XorTroll/Plutonium)). Thanks to MrDude, Huntereb, Behemoth, XorTroll, BlaWar, DarkMatterCore and all upstream contributors.
>
> ## Notes
> - Use only with games you own. No keys or games are provided.
> - Not affiliated with Nintendo.
> - SHA-256 of `Switch-Super-Installer.nro`: see `SHA256SUMS`.
