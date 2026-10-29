# Features

- **Library**: TitleDB metadata, covers, required firmware (read from CNMT), installed detection from the console inventory.
  Group a title with a game, set the region of a file, choose or remove a custom cover.
- **Statistics**: key figures, pie charts by format, type and region, the state of each library folder and its free space (the last known state is kept for unplugged disks), the largest games. Filter and sort the library by location.
- **Export**: the library as a PDF with covers (grid or detailed list, A4 or Letter, split in several files if you want) or as a CSV spreadsheet. File paths are left out unless you ask.
- **Unrecognised files**: the list of files the scans could not add (no Title ID, read error), with shortcuts to open the folder or blacklist them.
- **Metadata review**: compares the library with the current TitleDB and proposes changes you accept one by one. Names, covers and regions you set by hand are never touched.
- **Import**: sort dumps into library folders; free space of each folder shown. Duplicates are compared by size and SHA-256 before you decide, and nothing is moved before the decision.
- **Send**: queue, space check against the chosen storage (SD/NAND), live progress with a storage map, history.
- **Console tab**: storage usage (blocks or pie chart), installed titles (tick several games to uninstall them), refresh on demand, update from library, remote uninstall, save backups, captures gallery.
- **Cheats**: pushed to the console via SSI.
- **Remote management** (SSI option): lets SSM install, uninstall and back up saves without on-console confirmation during a session (sessions expire after 10 minutes).
- **Keep awake**: SSM prevents PC sleep during transfers; SSI can keep the console awake while charging.
- **Themes**: SSM, see [../themes/README.md](../themes/README.md); SSI, see [ssi-themes.md](ssi-themes.md).
- **Journal**: everything SSM does, with filters, in the settings and in `logs/ssm.log`.
