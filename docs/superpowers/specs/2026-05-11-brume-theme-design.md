# Brume Theme Palette — Design Spec

## Overview

Brume (French: mist/fog) is a color palette designed for developers, inspired by frost, mist, and ice. Every color in the spectrum is shifted toward blue-grey to create a frosted, diffused quality — as if viewing the full rainbow through misted glass.

The palette follows the model of Dracula and Catppuccin: a source-of-truth color definition that others can port to any platform.

## Variants (4)

| Name   | Vibe                         | Base BG    |
|--------|------------------------------|------------|
| Fog    | Morning fog, soft light      | ~92% white |
| Haze   | Overcast sky, muted midtone  | ~40% grey  |
| Mist   | Evening mist, vivid accents  | ~12% dark  |
| Void   | Deep night, glowing accents  | ~5% black  |

## Color Roles

### Neutrals (5 per variant)
- **Base** — primary background
- **Surface** — raised elements (cards, sidebars)
- **Overlay** — overlays, modals
- **Mantle** — subtle borders, dividers
- **Crust** — deepest accent surface

### Text (3 per variant)
- **Text** — primary text
- **Subtext1** — secondary text
- **Subtext0** — tertiary/hint text

### Frost Spectrum (14 per variant)
Each color is frost-tinted: shifted ~10-15% toward blue-grey and slightly desaturated.

| Color     | Description                    |
|-----------|--------------------------------|
| Rose      | Soft blush, like frost on petals |
| Flamingo  | Warm rose-coral, muted         |
| Red       | Cold crimson, blue undertone   |
| Maroon    | Deep frost-bitten berry        |
| Orange    | Cold amber, like frozen sap    |
| Yellow    | Pale wheat through fog         |
| Green     | Glacial sage, muted forest     |
| Teal      | Frozen pond surface            |
| Sky       | Winter sky, pale cyan          |
| Blue      | Deep frost blue                |
| Violet    | Twilight frost, cool indigo    |
| Mauve     | Heather in winter mist         |
| Pink      | Frost-tinted pink, cool blush  |
| Silver    | Ice crystal sparkle            |

## Exact Color Values

### Mist (Dark) — Primary Variant

| Role     | Hex       |
|----------|-----------|
| Base     | `#12131f` |
| Surface  | `#1a1c2e` |
| Overlay  | `#22253a` |
| Mantle   | `#2c2f48` |
| Crust    | `#363a56` |
| Text     | `#d5dce8` |
| Subtext1 | `#b0b8cc` |
| Subtext0 | `#8a92ab` |
| Rose     | `#f0a0b4` |
| Flamingo | `#e8909c` |
| Red      | `#e87d8a` |
| Maroon   | `#c86078` |
| Orange   | `#f0b080` |
| Yellow   | `#e8d590` |
| Green    | `#90d8b0` |
| Teal     | `#78d0d0` |
| Sky      | `#88c8f0` |
| Blue     | `#7090e8` |
| Violet   | `#a898e8` |
| Mauve    | `#d0a0e8` |
| Pink     | `#e8b8d0` |
| Silver   | `#c0c8e0` |

### Fog (Light)

| Role     | Hex       |
|----------|-----------|
| Base     | `#ebeef6` |
| Surface  | `#dfe2ed` |
| Overlay  | `#d0d4e3` |
| Mantle   | `#bcc2d6` |
| Crust    | `#a8afc6` |
| Text     | `#2c3050` |
| Subtext1 | `#434868` |
| Subtext0 | `#5c6180` |
| Rose     | `#c45878` |
| Flamingo | `#c06870` |
| Red      | `#b84858` |
| Maroon   | `#a03848` |
| Orange   | `#c07838` |
| Yellow   | `#b8a040` |
| Green    | `#3c9868` |
| Teal     | `#288888` |
| Sky      | `#3888c0` |
| Blue     | `#4060c0` |
| Violet   | `#6858b0` |
| Mauve    | `#9860b8` |
| Pink     | `#b86898` |
| Silver   | `#6a7090` |

### Haze (Soft Dark)

| Role     | Hex       |
|----------|-----------|
| Base     | `#2a2d3e` |
| Surface  | `#343750` |
| Overlay  | `#3e4260` |
| Mantle   | `#4a4e6e` |
| Crust    | `#585c7e` |
| Text     | `#d0d6e4` |
| Subtext1 | `#a8b0c4` |
| Subtext0 | `#8088a4` |
| Rose     | `#d88898` |
| Flamingo | `#d07888` |
| Red      | `#d06878` |
| Maroon   | `#b85068` |
| Orange   | `#d89860` |
| Yellow   | `#d0c070` |
| Green    | `#68c088` |
| Teal     | `#58b8b8` |
| Sky      | `#68b0d8` |
| Blue     | `#5878d0` |
| Violet   | `#9080d0` |
| Mauve    | `#b888d0` |
| Pink     | `#d098b8` |
| Silver   | `#a8b0c4` |

### Void (Deep Dark)

| Role     | Hex       |
|----------|-----------|
| Base     | `#08090f` |
| Surface  | `#10111c` |
| Overlay  | `#181a28` |
| Mantle   | `#202338` |
| Crust    | `#2a2d44` |
| Text     | `#c8d0e0` |
| Subtext1 | `#a0a8c0` |
| Subtext0 | `#7880a0` |
| Rose     | `#f8a8bc` |
| Flamingo | `#f098a8` |
| Red      | `#f08898` |
| Maroon   | `#d86880` |
| Orange   | `#f8b888` |
| Yellow   | `#f0d898` |
| Green    | `#98e0b8` |
| Teal     | `#80d8d8` |
| Sky      | `#90d0f8` |
| Blue     | `#7898f0` |
| Violet   | `#b0a0f0` |
| Mauve    | `#d8a8f0` |
| Pink     | `#f0c0d8` |
| Silver   | `#c8d0e4` |

## Repo Structure

```
brume/
├── palette/
│   └── colors.json          # Source of truth: all 4 variants
├── website/
│   ├── index.html           # GitHub Pages showcase site
│   └── style.css            # Site styles using Brume palette
├── ports/
│   └── css/
│       ├── fog.css          # CSS custom properties
│       ├── haze.css
│       ├── mist.css
│       └── void.css
├── LICENSE (MIT)
└── README.md
```

## Website

Single-page site deployed to GitHub Pages (`vkeerthivikram.github.io/brume`):

- Hero section with palette name + description
- Interactive swatches for all 4 variants
- Click-to-copy hex values
- CSS variable export section
- "Ports" section (placeholder for community ports)
- Responsive, dark-mode default (Mist variant)

## GitHub Repository

- Hosted at `github.com/vkeerthivikram/brume`
- Deployed via GitHub Pages from `main` branch / `website/` directory

## Design Principles

1. **Frost-tinted** — Every color has a blue-grey shift. No pure warm tones.
2. **Consistent across variants** — Same color name = same relative position in each variant.
3. **Accessible** — Text colors maintain WCAG AA contrast against their base.
4. **Distinctive** — The blue-grey tint makes Brume immediately recognizable vs other palettes.
5. **Community-first** — JSON source of truth makes it easy to port to any platform.
