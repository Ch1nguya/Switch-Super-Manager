# Changelog

## Switch-Super-Manager 0.6.0

**Console**
- Console tab loads asynchronously with a cache; sub-tabs (storage, installed games, save backups, captures, history).
- Refresh button (asks SSI for a fresh inventory) and the time of the last update next to it.
- Update console titles from the library; remote uninstall (one result window at the end); save backups; captures backup and gallery.
- Cheats delivery over SSI's HTTP server.

**Sending**
- Send queue (the whole bar opens the list), transfer history, free-space check, progress bar and detail window with a storage map.
- Choice of install location (SD / NAND / ask at each transfer).
- Remote management option in SSI: installs, uninstalls and save backups without a question on the console.
- Keep-awake option (PC during transfers, console while charging).

**Library**
- Import: free space of the library folders; the file is moved, copied or renamed only after the duplicate decision ("Do not import" leaves it untouched).
- Duplicate window: size comparison, SHA-256 content check, regions of both files, "Replace the library file" option.
- Region of a file can be set by hand (kept by rescans and imports).
- Group a title (a tool, a demo, another edition) with a game, and ungroup.
- Choose or remove a custom cover from the details menu.
- Library metadata review against the current TitleDB: a list of proposed changes you tick or untick, offered after a TitleDB update and from the database settings. Names, covers and regions set by hand are never proposed.
- A rescan stays in the Library tab and refreshes the card of the game.

**Interface**
- External user themes (`themes/<name>/theme.json`); the two built-in themes stay immutable.
- Journal tab (filter, copy, save) and `logs/ssm.log`.
- About tab (version, links, licenses and credits, diagnostics).
- New splash screen, optional cheats panel, icons on all buttons, dark overlay behind dialogs, many fixes.

## Switch-Super-Installer 1.0.0

- Fork of Awoo Installer (GPL v3), see the credits in the repository.
- Install from an SSM library over the LAN, with covers (20% bigger during transfers) and multiple selection.
- Console inventory sent to SSM, on request too (`POST /inventory`).
- HTTP server on port 2003: cheats, covers, options, remote sessions, save backups, uninstall.
- Optional remote management, keep the console awake while charging.
- Themes: Default, Dreamcast Grey and your own (`themes/<name>/theme.json`, see [docs/ssi-themes.md](docs/ssi-themes.md)).
- Latest sigpatches fetched automatically; longer timeouts for the GitHub requests.
- Texts follow the chosen language; no Russian translation is shipped.
