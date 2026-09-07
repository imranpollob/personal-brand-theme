<img src="logo.png" alt="Imran Pollob logo" width="72">

# Personal Brand Theme

A small, portable design-token package — one teal brand scale, shared light/dark neutrals, and a handful of UI rules — meant to be dropped into any of my projects so they all look like one product.

**[Open the live preview →](preview.html)** (open locally in a browser; use the switch in the nav to check dark mode)

## What's in here

| File                           | Use it when…                                                                                                                                                                                                                     |
| ------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`brand.css`](brand.css)       | The project is a website or anything else that reads CSS custom properties. This is the source of truth.                                                                                                                         |
| [`brand.json`](brand.json)     | The project can't consume CSS directly — React Native, a Figma tokens plugin, a Tailwind/JS config, email templates, etc. Same values, kept in sync by hand.                                                                     |
| [`preview.html`](preview.html) | Interactive Brand Theme Studio & showcase (buttons, forms, alerts, cards, pricing, table…) with live palette switcher, font and pairing comparator, font-size scaler, and 1-click theme export for `brand.css` and `brand.json`. |
| [`logo.png`](logo.png)         | The mark used in the preview's nav.                                                                                                                                                                                              |

## Usage

```html
<link rel="stylesheet" href="brand.css">

<button class="primary-action">Get started</button>
<style>
  .primary-action {
    background: var(--color-primary);
    color: #fff;
    border-radius: var(--radius);
    font-family: var(--font-family);
  }
</style>
```

To switch to dark mode, set an attribute anywhere above the elements you want themed — usually `<html>`:

```html
<html data-theme="dark">
```

Toggle it at runtime with JS:

```js
document.documentElement.setAttribute('data-theme', 'dark');   // dark
document.documentElement.removeAttribute('data-theme');        // light
```

## Tokens

**Brand scale** — `--brand-50` through `--brand-950`, a teal ramp used to derive everything else.

**Semantic** (swap value per theme):

| Token                   | Light         | Dark          |
| ----------------------- | ------------- | ------------- |
| `--color-primary`       | `--brand-600` | `--brand-500` |
| `--color-primary-hover` | `--brand-700` | `--brand-400` |
| `--color-background`    | `--brand-50`  | `#071311`     |
| `--color-surface`       | `#f8fafc`     | `#0d1f1c`     |
| `--color-text`          | `#0f172a`     | `#f0fdfa`     |
| `--color-text-muted`    | `#64748b`     | `#94a3b8`     |
| `--color-border`        | `#cbd5e1`     | `#1f3a35`     |
| `--color-success`       | `#16a34a`     | `#4ade80`     |
| `--color-warning`       | `#f59e0b`     | `#fbbf24`     |
| `--color-error`         | `#dc2626`     | `#f87171`     |
| `--color-info`          | `#0284c7`     | `#38bdf8`     |

**Typography & Scale** — `--font-family`, `--font-heading`, `--font-mono`, `--base-font-size` (16px), and the full size ramp from `--font-size-xs` (0.75rem / 12px) to `--font-size-4xl` (2.75rem / 44px), with standardized weights and line heights.

**Shared UI** — `--radius` (8px), `--spacing-unit` (4px).

## The rules

Every project that pulls from this theme follows the same handful of rules:

1. Teal is the primary interaction color.
2. Light/dark neutrals come from the shared tokens above — no one-off grays.
3. One font family everywhere: Inter.
4. 8px is the default border radius.
5. 4px is the spacing base — space things in multiples of it.
