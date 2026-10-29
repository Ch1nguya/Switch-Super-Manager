# Changelog

## Switch-Super-Manager 0.6.5

- **Export of the library** (Settings, Database & tools): a **PDF** with the covers (a grid or a detailed list, A4 or Letter, for the games shown in the Library or the whole library, optionally split in several files) or a **CSV** spreadsheet that opens in Excel. File paths are left out unless you ask for them.
- **Unrecognised files** (Settings, Database & tools): the list of files the scans could not add to the library (no Title ID found, or a read error), with "Open the folder", "Add to the blacklist" and "Remove from this list".
- **Scan library is safer:** ticking it now selects "Import without renaming" and "Keep in place", so no file is moved or renamed by mistake. When nothing is moved or renamed, another copy of a known game is recorded as a duplicate without any question.

## Switch-Super-Manager 0.6.4

- **New-version notice.** At start-up SSM looks at the latest release on GitHub and, if a newer one exists, offers to open its page in your browser. It never downloads or installs anything. You can turn it off in the settings, and the About tab has a "Check for updates" button.
- **Library statistics** (link at the top right): key figures, pie charts by file format, content type and region, the state of each library folder with its free disk space (the last known state is kept when a disk is unplugged), and the 10 largest games.
- **Filter and sort by location** in the Library when you have several library folders.
- **Console tab:** a pie chart view of the SD card and the internal memory, next to the block view.
- **Console tab:** check boxes to tick several games before uninstalling them (no Ctrl or Shift needed), with "Check all" and "Uncheck all".
- The drop-down lists of the filters open at the width of their longest entry, so long names are readable in a small window.

## Switch-Super-Manager 0.6.2

- Start-up assistant on the first launch: language, `prod.keys` (it can copy the file for you), library folder, import mode (keep, move, rename) and the console IP. When it ends, SSM scans your library folder and adds your games.
- Hover effect and hand cursor on the assistant's buttons, with the colours of the active theme.

## Switch-Super-Manager 0.6.1

- After the welcome window, SSM offers to scan the library folder you chose (import in place: nothing is moved or renamed), so the library no longer stays empty.
- Uninstall several games at once from the Console tab (Ctrl or Shift to select, one confirmation).
- The import button reads "Scan and add to library" when "Scan library" is on, and fades slowly while the library is empty.
- Files list of the details panel fits long names on every screen size.
- The message shown when `prod.keys` is missing says where to put the file.

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
- Welcome window on the first launch (choose the library folder or go to Import).
- Interface in 9 languages: English, French, Spanish, German, Italian, Brazilian Portuguese, Japanese, Simplified Chinese and Korean (the new translations are machine-made and still to be reviewed: corrections are welcome).
- External user themes (`themes/<name>/theme.json`); the two built-in themes stay immutable.
- Journal tab (filter, copy, save) and `logs/ssm.log`.
- About tab (version, links, licenses and credits, diagnostics).
- New splash screen, optional cheats panel, icons on all buttons, dark overlay behind dialogs, many fixes.

## Switch-Super-Installer 1.0.1

- Fixes a crash on firmware 23.x: SSI is now built with the latest devkitA64 toolchain (libnx 4.12.0).
- The texts added for SSM (remote management, save backups, uninstall, network status) are translated in 8 more languages.
- The Docker build script is pinned to the toolchain image and no longer stops at compiler warnings.

## Switch-Super-Installer 1.0.0

- Built on TinWoo (MrDude), itself based on Awoo Installer (GPL v3), see the credits in the repository.
- Install from an SSM library over the LAN, with covers (20% bigger during transfers) and multiple selection.
- Console inventory sent to SSM, on request too (`POST /inventory`).
- HTTP server on port 2003: cheats, covers, options, remote sessions, save backups, uninstall.
- Optional remote management, keep the console awake while charging.
- Themes: Default, Dreamcast Grey and your own (`themes/<name>/theme.json`, see [docs/ssi-themes.md](docs/ssi-themes.md)).
- Latest sigpatches fetched automatically; longer timeouts for the GitHub requests.
- Every text follows the chosen language; the Ukrainian translation file is repaired.
