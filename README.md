# Ore Block — Discord theme

A blocky, Ore UI–inspired theme for **Vencord / Vesktop**: hard corners, 2px ink outlines, bevelled buttons that press down, Monocraft display type, and one vibrant ore accent. Works in Discord's dark **and** light themes.

| Ore | Accent |
|---|---|
| Emerald | `oklch(62% 0.19 150)` |
| Diamond | `oklch(78% 0.14 200)` |
| Amethyst | `oklch(56% 0.21 305)` |

## Install

**Auto-updating (recommended)** — Vencord → Themes → Online Themes, paste one:

```
https://cdn.jsdelivr.net/gh/HenryGotMC/Ore-UI-Discord@main/themes/ore-block-emerald.theme.css
https://cdn.jsdelivr.net/gh/HenryGotMC/Ore-UI-Discord@main/themes/ore-block-diamond.theme.css
https://cdn.jsdelivr.net/gh/HenryGotMC/Ore-UI-Discord@main/themes/ore-block-amethyst.theme.css
```

**Offline** — download a file from [`dist/`](dist) and drop it in Vencord → Themes → Open Themes Folder. Enable only one Ore Block theme at a time.

## Fonts

- **Monocraft** (headers, buttons, labels) loads automatically.
- **Miracode** (messages, names, code) must be installed locally — grab `Miracode.ttf` from [IdreesInc/Miracode releases](https://github.com/IdreesInc/Miracode/releases). Without it, IBM Plex is used.

## Icons

16 pixel-art icons in [`icons/`](icons) replace Discord's user-panel, header, channel and search icons. They're drawn as CSS masks, so they follow the theme colours (hover, muted red, accent). Turn them off with `--ore-icons: off;`.

`mic` `mic-off` `headphones` `headphones-off` `settings` `disconnect` `inbox` `help` `pin` `members` `bell` `threads` `add` `hash` `voice` `search`

To add one: draw a 16×16 single-colour SVG in `icons/`, then add a line to `src/ore-icons.css` mapping a button's `aria-label` to it.

## Options

Add to your theme file after the `@import`:

```css
:root {
  --ore-accent: oklch(70% 0.15 60);  /* any color — hover, depth and text derive from it */
  --ore-display-font: off;           /* Miracode everywhere */
  --ore-square-avatars: off;         /* round avatars */
  --ore-grain: on;                   /* faint surface grain */
  --ore-icons: off;                  /* Discord's own icons */
}
```

## Repo layout

```
src/ore-block.css          core theme — edit this
src/ore-icons.css          icon swaps (aria-label → icons/*.svg)
icons/*.svg                16×16 pixel icons
themes/*.theme.css         tiny loaders (accent + @import core) for Online Themes
dist/*.standalone.theme.css single-file builds for offline use
```

## Contributing

Discord changes class names often. When something looks off, open an issue with a screenshot and the element's classes (right-click → Inspect). Prefer `[role]`/`aria-*` selectors over hashed classes where possible.

Not affiliated with Mojang or Microsoft. Monocraft and Miracode are © Idrees Hassan, SIL OFL 1.1.
