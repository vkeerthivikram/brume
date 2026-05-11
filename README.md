# Brume

A frost-tinted color palette — every color shifted through icy mist.

Brume (French: mist) is an original color palette inspired by the beauty of frozen landscapes. Blue-tinted darks, icy cyan, vivid frost accents, and an icy glass aesthetic. Every color looks like it's viewed through frosted glass.

## Variants

| Variant | Description |
|---------|-------------|
| **Snow** | Purest white, barely blue |
| **Fog** | Morning fog, soft light |
| **Haze** | Overcast sky, muted midtone |
| **Dusk** | Twilight blue, between haze and mist |
| **Mist** | Evening mist, vivid accents |
| **Void** | Deep night, glowing accents |

## Colors

Each variant includes 27 colors:

**Neutrals:** Base, Surface, Overlay, Mantle, Crust

**Text:** Text, Subtext1, Subtext0

**Frost Spectrum (19):** Ice, Frost, Blue, Deep Blue, Sky, Teal, Mint, Green, Yellow, Orange, Peach, Red, Maroon, Rose, Pink, Flamingo, Purple, Lavender, Mauve

## Icy Glass Effect

Brume is designed for frosted glass UIs. Use these CSS properties for the signature icy look:

```css
.glass-panel {
  background: rgba(30, 50, 70, 0.35);
  backdrop-filter: blur(14px);
  -webkit-backdrop-filter: blur(14px);
  border: 1px solid rgba(126, 200, 232, 0.12);
  border-radius: 14px;
}
```

## Usage

### CSS

```html
<link rel="stylesheet" href="ports/css/brume-mist.css">
```

```css
.my-element {
  background: var(--brume-surface);
  color: var(--brume-text);
  border: 1px solid var(--brume-mantle);
}
```

Available variants: `brume-snow.css`, `brume-fog.css`, `brume-haze.css`, `brume-dusk.css`, `brume-mist.css`, `brume-void.css`

### JSON

The source of truth is [`palette/colors.json`](palette/colors.json). Use it to port Brume to any platform.

```js
import palette from './palette/colors.json';

const mist = palette.variants.mist.colors;
console.log(mist.ice); // #8ad0ea
```

## Ports

Want to port Brume to your favorite editor/terminal/app? Fork and PR!

- [CSS](ports/css/) — CSS custom properties

## Website

View the interactive palette at [vkeerthivikram.github.io/brume](https://vkeerthivikram.github.io/brume)

## License

MIT
