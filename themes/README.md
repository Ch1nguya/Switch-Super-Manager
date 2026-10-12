# Themes

SSM loads user themes from a `themes` folder next to the application (Settings > Appearance > open themes folder).
Each theme is a sub-folder containing a `theme.json`:

```
themes/
  my-theme/
    theme.json
```

The two built-in themes (**Cyber Neon**, **Dreamcast Grey**) are immutable and always available as a fallback.
A broken user theme is ignored and reported in the settings; it never prevents the app from starting.

## Format

```json
{
  "format": 1,
  "name": "My theme",
  "author": "you",
  "extends": "cyber-neon",
  "palette": { "bg": "#101820", "accent": "#ffb000" }
}
```

- `extends`: built-in theme providing every role you leave out (`cyber-neon` or `dreamcast-grey`).
- `palette`: role -> `#rrggbb`. Only list what you change.
- Schema: [theme.schema.json](theme.schema.json). Examples: [examples/](examples/).

## Roles

| Role | Used for |
|---|---|
| `accent` | main accent (selected tab, focus, buttons) |
| `accent2` | second accent (section titles, highlights) |
| `accent_deep` | darker accent (pressed buttons) |
| `accent_soft` | lighter accent (icons, links) |
| `bg` | window background |
| `border` | frames around panels |
| `btn_bg` | button background |
| `btn_hover_bg` | button background when hovered |
| `frame_strong` | strong frame (cheats panel) |
| `input` | text fields and combo boxes |
| `input_hover` | text field background when hovered |
| `line` | separators and thin outlines |
| `line_hover` | outlines of hovered widgets |
| `logo_plate` | plate behind pictures drawn for dark backgrounds |
| `panel2` | cards and panels |
| `panel3` | table headers, hovered rows, alternate rows |
| `scroll_edge` | scroll bar handle outline |
| `scroll_handle` | scroll bar handle |
| `surface` | raised surfaces |
| `text` | main text |
| `text_dim` | secondary text |
| `text_mute` | disabled and placeholder text |
| `toggle_line` | switch outline |
| `toggle_off` | switch background when off |
| `toggle_thumb` | switch knob when off |
| `warn` | warnings and caution icons |

Restart is not needed: pick the theme in the settings and apply.
