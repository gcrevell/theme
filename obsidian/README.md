# Satellite Nebula — Obsidian theme

A dark Obsidian theme generated from [`../color-palette.json`](../color-palette.json)
(the "Satellite Nebula" palette extracted from `theme-satellite-2.19.0.vsix`).

Dark violet ground, `#AE50FE` violet as the brand accent, `#FF580C` coral kept as a
warm counterpoint, and the palette's neon spread (cyan, teal, mint, lavender, amber,
rose, …) used for heading levels, callouts, tags and code syntax.

## Files

| File | Purpose |
| --- | --- |
| `manifest.json` | Theme metadata Obsidian reads to list the theme |
| `theme.css` | The theme itself |

## Install

Copy this folder into your vault's themes directory, keeping the folder name equal to
the `name` in `manifest.json`:

```sh
# from the repo root
mkdir -p "/path/to/vault/.obsidian/themes/Satellite Nebula"
cp obsidian/manifest.json obsidian/theme.css "/path/to/vault/.obsidian/themes/Satellite Nebula/"
```

Then in Obsidian: **Settings → Appearance → Themes → Satellite Nebula**, and set
**Base color scheme** to **Dark**.

For live editing while you tweak `theme.css`, symlink instead of copying:

```sh
ln -s "$(pwd)/obsidian" "/path/to/vault/.obsidian/themes/Satellite Nebula"
```

Obsidian picks up CSS changes on save; use **Ctrl/Cmd+P → Reload app without saving**
if a change doesn't appear.

## Structure of `theme.css`

1. **Raw palette** — every hex from `color-palette.json` as `--sn-*` variables.
2. **Accent hooks** — `--accent-h/s/l` (272° 99% 65%, i.e. `#AE50FE`) plus Obsidian's
   named `--color-red/orange/yellow/green/cyan/blue/purple/pink` so features that
   derive their own shades stay on-palette.
3. **Dark mode** — the `--color-base-00…100` scale and all semantic variables.
4. **Callouts** — state and syntax hues mapped onto the twelve callout types.
5. **Editor & reading view**, **code blocks**, **chrome**, **tags**, **graph/canvas**,
   **misc polish**.

Because steps 1–3 are all variables, most recoloring means editing a single `--sn-*`
value rather than hunting selectors.

## Light mode

The source palette is dark-only. In light mode this theme keeps Obsidian's default
light base scale and only carries over the accent plus darkened heading hues, so it
stays legible. The palette's notes mention a light counterpart ("Satellite Daybreak")
in the original VSIX — extracting that would be the way to get a real light variant.
