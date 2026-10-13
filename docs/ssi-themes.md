# SSI themes

Switch Super Installer ships two themes, **Default** (dark teal) and **Dreamcast Grey** (dark charcoal and orange, in the
spirit of the theme of the same name in Switch Super Manager). You can add your own: they appear in the list of the options.

## Choosing a theme

Options > **Theme**. Pick a theme in the list. It is used the next time SSI starts.

## Adding a theme

Create a folder in `sdmc:/switch/Switch-Super-Installer/themes/`, named as you like, with a `theme.json` inside:

```
switch/Switch-Super-Installer/themes/
  forest/
    theme.json
    background.png      (optional)
    icons/              (optional)
```

```json
{
  "name": "Forest",
  "base": "default",
  "background": "background.png",
  "logo": "logo.png",
  "iconSet": "light",
  "colors": {
    "bg": "#0F2A1C",
    "text": "#E4F5EA"
  }
}
```

- `name`: label shown in the list (the folder name when missing).
- `base`: `default` or `dreamcast`. What the file does not set (colours, background, logo) comes from this theme.
- `background`: optional picture of the theme folder, drawn behind the pages. A `background.png` placed directly in the
  SSI folder still wins over it.
- `logo`: optional picture of the theme folder, 480x93 pixels like the original, drawn in the title bar.
- `iconSet`: `light` (default, white icons) or `dark` (dark icons, for a theme with a light background).
- `icons/`: optional. Files with the names of the built-in icons (`folder.png`, `micro-sd.png`...) replace them one by one.
- `colors`: any of the keys below, as `#RRGGBB` or `#RRGGBBAA`. A wrong value is ignored.

| Key | Used for |
|---|---|
| `bg` | page background |
| `topbar` | bar with the logo |
| `bar` | information bar and bottom bar |
| `barText` | text drawn on the bars |
| `text` | menu and list text, drawn on the background |
| `focus` | highlight of the selected line |
| `scroll`, `scrollSoft` | scroll bars (main menu, lists) |
| `menuClear` | background of the menus (keep it transparent) |
| `ok` | "already installed" text |
| `installBg`, `installTop`, `installInfo` | background, logo bar and information bar of the install screen |
| `installBar`, `installBarFill` | progress bar (track and fill) |

A theme that cannot be read is simply not offered. An example is in [`ssi-themes/examples/forest`](../ssi-themes/examples/forest/theme.json).
