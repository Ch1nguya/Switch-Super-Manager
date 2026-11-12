# Changelog

## Switch-Super-Manager 0.7.1

- **Offline mode** (Settings, Database & tools): one button downloads the screenshots of every game of the library at once (up to 8 per game), so that the game pages are complete without an internet connection. Only the missing ones are downloaded; the window first tells how many, the space needed and the free space. It runs in the background (you can keep working, even synchronise the database), logs its progress in the journal, can be cancelled at any time and stops by itself when the disk is almost full. A **View journal** button shows up while it runs. Covers and descriptions were already kept offline.
- **Cheats filter:** the cheats you downloaded yourself (from Cheatslips) now count: a game no longer shows as "none" when you have a cheat file for it.
- **Journal page:** the log now fills the height of the window.

## Switch-Super-Manager 0.7.0

- **Switch 2 games, read from NUP archives.** SSM now reads `.nup` files (the open container for decrypted Switch 1 and Switch 2 dumps, see github.com/a55uka/nup) without any key: the name, the icon, the base game, its updates and its DLC come from the archive and from TitleDB, and the file is listed in the library like the others (format "NUP").
- **Switch / Switch 2 filter** in the Library, shown only when it holds games of both consoles. The console of a game is told from its program description (`main.npdm`), as the Eglantine emulator does, so a Switch 2 game in an NSP or an XCI is recognised too (the title ID is only a fallback, for compressed files, updates and DLC). Rescan a game to get it from its file.
- **Sending to a console is turned off for NUP archives** for now (SSI has no Switch 2 version yet): the buttons are off and the queue refuses them, with an explanation.
- **Big copies are followed in the journal:** a line when a copy of more than 256 MB starts, one every 10 percent (or every minute) with the speed and the time left, and one when it ends.
- **The journal stays open during an import:** Settings only offers its Journal page while an import runs, so the log can be read, filtered and copied.

## Switch-Super-Manager 0.6.7

- **"Synchronize with disk" no longer treats an unplugged disk as deleted files.** The entries of a library folder that cannot be reached (external disk off, network share down) are kept, and the report says how many.
- **"Synchronize with disk" cleans the library:** it offers to remove a leftover `[DUP]` from file names that are no longer duplicates (the other copy is gone), and the stale entries of copies that were moved and imported again are proposed for removal instead of staying "unresolved". Real duplicates are never touched, and nothing changes until you apply the report. The report window is wider.
- **Send queue:** the bar at the bottom now has a visible "Send..." button (clicking the bar did the same, but nothing said so).
- **Cheatslips token:** an unrelated save can no longer erase it when the field was empty only because the token could not be read at start-up.
- **Console IP:** a new address typed in the settings is used at once; the address of the last inventory no longer wins over it until you restart.

## Switch-Super-Manager 0.6.6

- **Cheats of your games without an account** (new Cheats tab in the settings, off until you turn it on): SSM downloads the public cheats archive (switch-cheats-db, cheats by their authors) and puts the cheats of the games of your library in its cheats folder. They are listed like the ones from Cheatslips, with their number of cheats and a mark on the build that fits your version. Updated when the archive changes; the cheats of games that leave the library are removed. The cheats you downloaded from Cheatslips are never replaced or removed. The addresses can be changed.
- **Cheats filter** in the Library (for your version, other versions only, none), and a link next to "Statistics" when the cheats archive has changed. "Synchronize with disk" also updates it and says what it did in the log.
- **Statistics:** click a slice of the format or region chart, or a library folder, to show those files in the Library.
- **Moved files:** the "File not found" message now offers "Synchronize with disk" (which finds files moved inside your library folders). A file moved by hand is no longer taken for present.
- **Crash fixed:** SSM could close by itself when the window was maximised or resized (the page of a game and its screenshots were resizing each other without end).
- The window to send files, the tooltips of the screenshots and the messages of the database maintenance are translated in every language.

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
