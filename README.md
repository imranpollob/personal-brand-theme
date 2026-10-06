<img src="logo.png" alt="Imran Pollob logo" width="72">

# Personal Brand Theme

A small, portable design-token package — one teal brand scale, Outfit and Plus Jakarta Sans typography, shared light/dark neutrals, and a cohesive set of UI rules — meant to be dropped into any project so they all look like one unified product.

**[Explore Brand Style Showcase →](https://imranpollob.github.io/personal-brand-theme/)**

## What's in here

| File                       | Use it when…                                                                                                                                                                                 |
| -------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`brand.css`](brand.css)   | The project is a website or web app that reads CSS custom properties. This is the source of truth.                                                                                           |
| [`brand.json`](brand.json) | The project consumes JSON tokens — React Native, a Figma tokens plugin, a Tailwind/JS config, email templates, etc. Same values, kept in sync.                                               |
| [`index.html`](index.html) | The official **Brand Style Showcase** demonstrating the signature style (palette swatches with click-to-copy, typography specimen, UI component system, data table, and integration guides). |
| [`logo.png`](logo.png)     | The signature brand mark.                                                                                                                                                                    |
| [`launcher.js`](launcher.js), [`launcher.css`](launcher.css), [`tools.json`](tools.json) | The **tools launcher** — a waffle button that opens a grid of all my tools. See below. |

## Usage

```html
<!-- 1. Include Google Fonts in <head> -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Outfit:wght@400;500;600;700;800&family=Plus+Jakarta+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">

<!-- 2. Link the personal brand theme -->
<link rel="stylesheet" href="brand.css">

<!-- 3. Build with brand tokens -->
<button class="primary-action">Get started</button>
<style>
  .primary-action {
    background: var(--color-primary);
    color: #fff;
    border-radius: var(--radius);
    font-family: var(--font-family);
    font-size: var(--font-size-base);
  }
</style>
```

To switch to dark mode, set `data-theme="dark"` on `<html>`:

```html
<html data-theme="dark">
```

Toggle it at runtime with JS:

```js
document.documentElement.setAttribute('data-theme', 'dark');   // dark
document.documentElement.removeAttribute('data-theme');        // light
```

## Tools launcher

Add the all-tools menu to any site:

```html
<link rel="stylesheet" href="https://imranpollob.github.io/personal-brand-theme/launcher.css">
<script src="https://imranpollob.github.io/personal-brand-theme/launcher.js" defer></script>

<!-- optional: place the button in your header (otherwise it floats top-left) -->
<span data-brand-launcher></span>
```

The tool list lives in [`tools.json`](tools.json) — edit it once and every site updates. Each entry has `title`, `url`, `type` (`online` / `install`), `priority`, and the tile styling fields `hue` (0–360) and `glyph` (emoji). Starred tools (saved in `localStorage`) are listed first; stars are per-origin, so they don't carry across different domains.

## Tokens

**Brand scale** — `--brand-50` through `--brand-950`, an 11-step teal ramp used to derive everything else.

**Semantic** (swap value per theme):

| Token                   | Light     | Dark      |
| ----------------------- | --------- | --------- |
| `--color-primary`       | `#0d9488` | `#14b8a6` |
| `--color-primary-hover` | `#0f766e` | `#2dd4bf` |
| `--color-background`    | `#ecfdfb` | `#071311` |
| `--color-surface`       | `#f8fafc` | `#0d1f1c` |
| `--color-text`          | `#0f172a` | `#f0fdfa` |
| `--color-text-muted`    | `#64748b` | `#94a3b8` |
| `--color-border`        | `#cbd5e1` | `#1f3a35` |
| `--color-success`       | `#16a34a` | `#4ade80` |
| `--color-warning`       | `#f59e0b` | `#fbbf24` |
| `--color-error`         | `#dc2626` | `#f87171` |
| `--color-info`          | `#0284c7` | `#38bdf8` |

**Typography & Scale**:
- `--font-heading`: `'Outfit', system-ui, -apple-system, sans-serif`
- `--font-family`: `'Plus Jakarta Sans', system-ui, -apple-system, sans-serif`
- `--font-mono`: `'SFMono-Regular', Consolas, 'JetBrains Mono', monospace`
- `--base-font-size`: `16px`
- `--font-size-nav`: `0.875rem` (14px)
- Full size ramp from `--font-size-xs` (0.75rem / 12px) to `--font-size-4xl` (2.75rem / 44px)

**Shared UI**:
- `--radius`: `8px`
- `--spacing-unit`: `4px`

## The rules

Every project that pulls from this theme follows the same design principles:

1. **Teal is the signature color**: `#0d9488` is the primary interactive accent in light mode; `#14b8a6` in dark mode.
2. **Modern typography pairing**: Outfit for bold, distinctive headings; Plus Jakarta Sans for crisp, modern body interfaces.
3. **16px base font size**: The standard web baseline calibrated for comfortable, balanced reading across all screen sizes.
4. **Shared neutral tokens**: Surfaces, borders, and text values come strictly from the tokens — no rogue grays.
5. **8px default corner radius**: Subtle, modern curvature across buttons, cards, and inputs.
6. **4px grid unit**: All padding, margins, and gaps are multiples of 4px.
