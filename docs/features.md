# Features

- **Library**: TitleDB metadata, covers, required firmware (read from CNMT), installed detection from the console inventory.
  Group a title with a game, set the region of a file, choose or remove a custom cover.
- **Metadata review**: compares the library with the current TitleDB and proposes changes you accept one by one. Names, covers and regions you set by hand are never touched.
- **Import**: sort dumps into library folders; free space of each folder shown. Duplicates are compared by size and SHA-256 before you decide, and nothing is moved before the decision.
- **Send**: queue, space check against the chosen storage (SD/NAND), live progress with a storage map, history.
- **Console tab**: storage usage, installed titles, refresh on demand, update from library, remote uninstall, save backups, captures gallery.
- **Cheats**: pushed to the console via SSI.
- **Remote management** (SSI option): lets SSM install, uninstall and back up saves without on-console confirmation during a session (sessions expire after 10 minutes).
- **Keep awake**: SSM prevents PC sleep during transfers; SSI can keep the console awake while charging.
- **Themes**: SSM, see [../themes/README.md](../themes/README.md); SSI, see [ssi-themes.md](ssi-themes.md).
- **Journal**: everything SSM does, with filters, in the settings and in `logs/ssm.log`.
