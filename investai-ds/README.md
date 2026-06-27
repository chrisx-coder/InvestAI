# InvestAI — Design System

A lightweight, light-theme design system for the **InvestAI** website and product surfaces.
Self-contained: plain CSS custom properties + utility classes, plus the logo asset set.
No build step, no dependencies (fonts load from Google Fonts).

> **Built to compound. Designed to stay in your control.**

---

## Quick start

```html
<link rel="stylesheet" href="/investai-ds/investai.css">
<!-- (this imports tokens.css + components.css) -->

<body class="iv-body">
  <header class="iv-container">
    <nav class="iv-nav">
      <a class="iv-brand" href="/">
        <img src="/investai-ds/logo/investai-mark.svg" alt="InvestAI">
        <span class="iv-brand-name">InvestAI</span>
      </a>
      <ul class="iv-nav-links">
        <li><a class="iv-nav-link" href="#">Product</a></li>
        <li><a class="iv-nav-link" href="#">Pricing</a></li>
      </ul>
      <a class="iv-btn iv-btn-primary" href="#">Get started</a>
    </nav>
  </header>
</body>
```

Favicon / app icons:

```html
<link rel="icon" href="/investai-ds/logo/favicon.ico" sizes="any">
<link rel="icon" type="image/svg+xml" href="/investai-ds/logo/investai-icon.svg">
<link rel="apple-touch-icon" href="/investai-ds/logo/icon-180.png">
```

---

## Files

```
investai-ds/
├── investai.css        ← link THIS (imports the two below)
├── tokens.css          ← CSS variables: color, type, spacing, radius, shadow, motion
├── components.css      ← .iv-* component classes
├── README.md
└── logo/
    ├── investai-mark.svg          colored mark (light backgrounds)
    ├── investai-mark-white.svg    white mark (dark backgrounds)
    ├── investai-icon.svg          app-icon tile (navy + white mark)
    ├── investai-wordmark.svg      horizontal lockup, dark text
    ├── investai-wordmark-white.svg horizontal lockup, white text
    ├── favicon.ico                16/32/48 multi-size
    ├── icon-16/32/48/180/192/512.png
    └── investai-mark-512/256.png, investai-mark-white-512.png
```

---

## Foundations

### Color
Cosmic spectrum — **blue → orchid → teal** over deep navy ink. Use tokens, never raw hex.

| Token | Value | Use |
|---|---|---|
| `--primary` / `--c-blue` | `#477BD1` | primary actions, links |
| `--c-orchid` | `#C44EB0` | magenta accent |
| `--c-teal` | `#46B298` | mint accent |
| `--c-navy` | `#0D1333` | headings, dark surfaces |
| `--success` | `#1F9E6B` | gains / positive |
| `--danger` | `#E25247` | losses / negative |
| `--grad-spectrum` | magenta→blue→teal | numerals, rules, gradient text |
| `--grad-aurora` | blue→violet→orchid | the **one** hero CTA only |
| `--grad-ink` | indigo→navy | dark sections & cards |

Two-tone page rhythm: alternate `--surface-page` (pale) and `--surface-card` (white), punctuated by the occasional full `--grad-ink` band.

### Type
- **Space Grotesk** — display / headings / brand (`--font-display`), tight tracking `-0.02em`.
- **Figtree** — UI + body (`--font-body`).
- **Space Mono** — numbers, data, eyebrows, codes (`--font-mono`). Use `font-variant-numeric: tabular-nums` for figures.

Eyebrows are UPPERCASE mono with wide `0.16em` tracking and a 28×2px spectrum rule (built into `.iv-eyebrow`).

### Shape & elevation
- Cards `16px`, inputs `12px`, **buttons always pills** (`999px`).
- Shadows are **cool indigo-tinted**, never neutral grey (`--shadow-sm/md/lg`). `--shadow-glow` for emphasis.
- Hover lift on cards = `-4px` + deeper shadow. Buttons translate `+1px` on press. Calm easing, no bounce.

---

## Components (class reference)

- **Buttons** — `.iv-btn` + `.iv-btn-primary` / `.iv-btn-secondary` / `.iv-btn-ghost` / `.iv-btn-aurora` (hero only). Sizes `.iv-btn-lg` / `.iv-btn-sm`.
- **Cards** — `.iv-card` (+ `.iv-card-hover`, `.iv-card-accent` top bar, `.iv-card-dark`).
- **Stats** — `.iv-stat-label`, `.iv-stat-value`, `.iv-delta.up` / `.iv-delta.down` (auto ▲/▼).
- **Badges** — `.iv-badge` + `.iv-badge-blue/orchid/teal/success`, add `.iv-badge-dot`.
- **Forms** — `.iv-field`, `.iv-label`, `.iv-input`, `.iv-select`.
- **Nav** — `.iv-nav`, `.iv-nav-links`, `.iv-nav-link`, `.iv-brand`, `.iv-brand-name`.
- **Layout** — `.iv-container` (1200px), `.iv-section` (96px block padding).
- **Text** — `.iv-h1/h2/h3`, `.iv-lead`, `.iv-eyebrow`, `.iv-text-gradient`, `.iv-mono`.

---

## Voice & tone
Operator-grade, declarative, confident. Short parallel fragments, em-dashes for emphasis.
Numbers as proof, never vague. No buzzwords, no hype, **no emoji**.

✅ *"Your capital, working while you sleep — fully transparent, fully yours."*
❌ *"Leverage synergistic AI to optimize your portfolio."*

---

## Dark mode
Add `data-theme="dark"` to any wrapper to flip the neutral tokens. Swap to `investai-mark-white.svg`
and `investai-wordmark-white.svg` on dark surfaces.
