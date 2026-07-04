<div align="center">
  <img src="lore-wordmark-light.svg#gh-light-mode-only" alt="Lore" height="56">
  <img src="lore-wordmark-dark.svg#gh-dark-mode-only" alt="Lore" height="56">
  <p><em>Brand assets & usage guidelines</em></p>
</div>

---

# Lore Branding

Official logos, colors, and typography for **Lore** — an engineering team's decision memory. This repo is the single source of truth; always pull assets from here rather than copying them out of a slide deck or screenshot.

## The mark

Three concentric arcs radiating from a single point — an **echo of recalled knowledge**. The open rings read as a signal rippling outward (memory surfacing), and the solid center dot is the decision at its origin.

---

## Assets

| File | Size (viewBox) | Use it for | Background |
|------|----------------|------------|------------|
| [`lore-mark.svg`](lore-mark.svg) | 48×48 | The icon on its own — app tiles, avatars, spots where "Lore" is already written | **Light** |
| [`lore-mark-dark.svg`](lore-mark-dark.svg) | 48×48 | Same, on dark UI | **Dark** |
| [`lore-wordmark-light.svg`](lore-wordmark-light.svg) | 150×56 | The primary logo (mark + "Lore") — headers, READMEs, docs, landing pages | **Light** |
| [`lore-wordmark-dark.svg`](lore-wordmark-dark.svg) | 150×56 | Primary logo on dark UI | **Dark** |
| [`favicon.svg`](favicon.svg) | 48×48 | Browser tab / PWA icon. Same mark with a slightly heavier stroke so it survives at 16px | **Transparent** |

**Pick by two questions:** (1) do you need the word "Lore" beside the icon? → wordmark, else mark. (2) Is the background dark? → `-dark`, else `-light`.

All files are **SVG** — infinitely scalable, tiny, and the accent color lives in the file. Prefer SVG everywhere it's supported. See [Raster exports](#raster-exports) if you need PNG/ICO.

---

## Color

| Token | Hex | Where it's used |
|-------|-----|-----------------|
| **Lore Amber** | `#fc9117` | The mark's arcs — the one brand color. Also fine for links/accents. |
| **Ink** | `#1c1c1c` | Center dot & wordmark text on **light** backgrounds |
| **Cream** | `#faf9f7` | Center dot on **dark** backgrounds |
| **Cream Text** | `#f6f3ed` | Wordmark text on **dark** backgrounds |

> **Amber is fixed.** `#fc9117` is the whole identity — don't recolor the arcs. Only the neutral (ink vs. cream) flips with the background.

---

## Typography

The wordmark is set in **Geist** (semibold), falling back to **Inter**, then the system UI stack:

```
font-family: Geist, Inter, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
font-weight: 600;
letter-spacing: -0.8;   /* tightened */
```

The wordmark SVGs embed this stack, so they render correctly without the font installed. For surrounding product/marketing text, use the same family for consistency.

---

## Usage

### Markdown / GitHub
Use the two-image trick so the logo adapts to the reader's theme:

```markdown
<img src="https://raw.githubusercontent.com/lorehasit/lore-branding/main/lore-wordmark-light.svg#gh-light-mode-only" alt="Lore" height="40">
<img src="https://raw.githubusercontent.com/lorehasit/lore-branding/main/lore-wordmark-dark.svg#gh-dark-mode-only" alt="Lore" height="40">
```

### HTML
```html
<img src="lore-mark.svg" alt="Lore" width="32" height="32">
```

### Favicon
```html
<link rel="icon" type="image/svg+xml" href="favicon.svg">
```

### Clear space & minimum size
- **Clear space:** keep padding equal to at least the radius of the outermost ring (≈ ¼ of the mark's height) clear of text and other logos on all sides.
- **Minimum size:** mark no smaller than **16px**; wordmark no smaller than **90px** wide (below that, "Lore" starts to crowd the mark).

---

## Do / Don't

**Do**
- Use the SVGs as-is, at any scale.
- Choose the `-dark` variant on dark backgrounds so the center dot and text stay legible.
- Give the logo room to breathe (see clear space).

**Don't**
- Recolor the amber arcs, add gradients, shadows, or outlines.
- Stretch, squash, rotate, or rearrange the mark and wordmark.
- Place the light logo on a busy or low-contrast background.
- Re-typeset "Lore" in a different font — use the wordmark file.

---

## Raster exports

Need a PNG (e.g. social preview) or `.ico`? Convert on demand — don't commit one-off sizes.

```bash
# PNG at 2x (requires: npm i -g @resvg/resvg-js-cli  — or use Inkscape/rsvg-convert)
resvg lore-mark.svg lore-mark@2x.png --width 96 --height 96

# Favicon .ico from the SVG (ImageMagick)
magick -background none favicon.svg -define icon:auto-resize=16,32,48 favicon.ico
```

---

## License

These marks identify Lore. You may use them **unaltered** to link to or reference Lore. You may **not** use them to imply endorsement, or modify them, without permission. See [`LICENSE`](LICENSE) if present, otherwise contact the maintainers.
