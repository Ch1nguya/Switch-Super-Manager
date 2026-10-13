# Switch-Super-Manager

Desktop manager for your Nintendo Switch game library, with a companion homebrew
(**Switch-Super-Installer**, SSI) to install, back up and manage content on the console over your local network.

> **Status:** v0.6.0. The SSM application source is **closed** until v1.0 (SSI is open source, GPL v3). This repository holds the
> public kit: documentation, theme kit, utilities and links to the binaries (see [Releases](https://github.com/Ch1nguya/Switch-Super-Manager/releases)).

## Features

- Library browser with TitleDB metadata, covers, descriptions, firmware requirements and installed-state detection.
- Import and organise dumps into one or several library folders (free space shown for each).
- Send games, updates and DLC to the console over the LAN (queue, progress, history, space check).
- Console tab: storage map, installed titles, remote uninstall, save backups, screenshot / video gallery.
- Cheats delivery straight to the console.
- Themes: two built-in themes plus user themes (see [themes/](themes/README.md)).
- Keep-awake option so the console does not sleep during transfers.

See [docs/features.md](docs/features.md) for details.

## Getting started

[docs/getting-started.md](docs/getting-started.md)

## Documentation

| Topic | File |
|---|---|
| Getting started | [docs/getting-started.md](docs/getting-started.md) |
| Features | [docs/features.md](docs/features.md) |
| Network and firewall | [docs/network.md](docs/network.md) |
| SSI HTTP API (console, port 2003) | [docs/ssi-api.md](docs/ssi-api.md) |
| SSM HTTP API (PC, port 2002) | [docs/ssm-api.md](docs/ssm-api.md) |
| Console inventory format | [docs/console-inventory.md](docs/console-inventory.md) |
| SSM themes | [themes/README.md](themes/README.md) |
| SSI themes | [docs/ssi-themes.md](docs/ssi-themes.md) |
| FAQ | [docs/faq.md](docs/faq.md) |

## Binaries

Binaries are published only through GitHub Releases, with a `SHA256SUMS` file. See [RELEASING.md](RELEASING.md).
**No keys are ever distributed**: you must supply your own `prod.keys`, dumped from your own console.

## Utilities

Community utilities (Python / Rust) will live in [tools/](tools/README.md).

## Licenses and credits

| Component | License |
|---|---|
| **Switch-Super-Manager** (SSM, PC application) | [PolyForm Noncommercial 1.0.0](LICENSE): free for personal, non-commercial use. Source closed until v1.0. |
| **Switch-Super-Installer** (SSI, Switch homebrew) | GPL v3, open source: [Ch1nguya/Switch-Super-Installer](https://github.com/Ch1nguya/Switch-Super-Installer) |
| This repository (documentation, themes, tools) | [PolyForm Noncommercial 1.0.0](LICENSE), unless a file says otherwise |

SSI is built on TinWoo by MrDude, which merges Tinleaf and [Awoo Installer](https://github.com/Huntereb/Awoo-Installer) by Huntereb,
itself based on [Adubbz's Tinfoil](https://github.com/Adubbz/Tinfoil) (MIT) and using [XorTroll's Plutonium](https://github.com/XorTroll/Plutonium).
Thanks to MrDude, Huntereb, Behemoth, XorTroll, BlaWar, DarkMatterCore and all upstream contributors.

Not affiliated with Nintendo. Use only with games you own; no keys or games are provided.
