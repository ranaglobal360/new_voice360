# Voice 360 — Design system: Colour & Typography

The colour and typography foundations for every Voice 360 surface.
Last updated 11 August 2026.

---

## What to read first

| Order | File | Who it's for |
|---|---|---|
| 1 | `01-colour-system.html` | Everyone. The full Material 3 colour system, rendered live — tonal palettes, light/dark schemes, contrast audit. Self-contained; double-click to open. |
| 2 | `tokens/colour.css` + `tokens/colour.json` | Frontend. Copy-paste ready tokens. |
| 3 | `tokens/typography.css` + `tokens/typography.json` | Frontend. The 11-step mobile scale + desktop scale. |

## Colour — two systems, one migration

**Hand-picked palette (legacy, still valid).** Voice Green `#049567` primary plus five
domain secondaries — Civic Blue, Signal Amber, Alert Red, Manage Violet, Talk Teal.
Each ships as a triplet: tint background, hairline border, text colour. Six neutrals do
all structural work; text is never a hue.

**Material 3 (new work references this).** Generated from seed `#049567`:
seven tonal palettes (M3's six + a custom Warning at hue 100°), full light and dark
schemes, fixed roles, and a numeric 50–900 ramp with 500 pinned to the exact seed.
Every checked contrast pair passes its floor — the audit table is in
`01-colour-system.html`.

Contrast rules that bite:
- Never mid-tone hue (`#049567`, `#e0a53c`) as text on its own tint — use the 700.
- White on primary-500 is 3.8:1 — filled buttons with body-size white labels use 600 `#007c54`.

## Typography — 11 steps, 3 weights

Manrope only. 400 long-form body · 600 interface copy · 800 structural. Never 300/500/700.
Rebuilt from an audit of 5,185 text declarations in the built screens (27 sizes → 11 steps;
2,378 declarations migrated). Steps: Display 34, Headline 22, Title L 18 / M 15 / S 13,
Label 12/800, Body 13/600, Body S 12/600, Meta 11, Caps 10, Pill 10.
Tracking permits five values only: -1.4, -0.4, 0, +0.8, +1.1.
Floor 10px (caps/pills only); body never below 11px.

## `source/` — editable original

`Voice 360 Colour - Material 3.dc.html` + `support.js` must stay in the same flat
folder. Edit the seed/variant/contrast props and re-export if the brand hue ever moves.
The typography spec lives in the Framework site (uploaded once, separately) — the token
files here are the extract of record for engineering.

## Suggested repo placement

```
design/
  design-system/
    README.md
    01-colour-system.html
    tokens/
      colour.css
      colour.json
      typography.css
      typography.json
    source/
```
