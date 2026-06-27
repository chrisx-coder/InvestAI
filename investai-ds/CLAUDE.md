# CLAUDE.md — InvestAI design system (agent instructions)

You are building the **InvestAI** website / product UI. A complete design system lives in
`investai-ds/`. Follow it exactly — do not invent colors, fonts, spacing, or shadows.

## How to use it
1. Link `investai-ds/investai.css` once in `<head>`. It imports `tokens.css` + `components.css`.
2. Put `class="iv-body"` on `<body>`.
3. Build with the `.iv-*` classes and the CSS variables — see `README.md` for the full reference.

## Hard rules
- **Use tokens, never raw hex.** `var(--primary)`, `var(--c-navy)`, `var(--surface-card)`, etc.
- **Buttons are always pills.** Use `.iv-btn` + a variant. `.iv-btn-aurora` is reserved for the single
  primary hero CTA per page — nothing else.
- **Shadows are indigo-tinted** (`--shadow-*`). Never add neutral-grey `box-shadow`.
- **Fonts:** Space Grotesk = headings/brand, Figtree = body, Space Mono = all numbers & eyebrows.
  Apply `font-variant-numeric: tabular-nums` to any column of figures.
- **Finance color semantics:** gains use `--success`, losses use `--danger`. `.iv-delta.up/.down`
  renders the arrow automatically.
- **No emoji.** Use the spectrum-dot bullets / inline stroke SVG icons (~2px stroke, rounded caps).
- **Gradients sparingly:** `--grad-spectrum` for numerals/rules/gradient text, `--grad-ink` for dark
  bands/cards, `--grad-aurora` only for the hero CTA.

## Logo usage
- Light backgrounds: `logo/investai-mark.svg` or `logo/investai-wordmark.svg`.
- Dark backgrounds: `logo/investai-mark-white.svg` or `logo/investai-wordmark-white.svg`.
- Favicon: `logo/favicon.ico` + `logo/investai-icon.svg`; Apple touch: `logo/icon-180.png`.
- Never recolor, stretch, rotate, or add effects to the mark.

## Layout rhythm
- `.iv-container` caps content at 1200px. `.iv-section` gives 96px vertical padding.
- Alternate pale (`--surface-page`) and white (`--surface-card`) sections; drop an occasional
  full `--grad-ink` band for emphasis. White cards on light, `.iv-card-dark` on ink.

## Voice
Operator-grade, declarative, confident. Short fragments, em-dashes, real numbers. No buzzwords,
no hype, no emoji. See README "Voice & tone".

## When something isn't covered
Extend in the system's spirit: reuse the tokens, match the radius/shadow/spacing scale, keep the
spectrum palette. Prefer adding a token over hard-coding a value.
