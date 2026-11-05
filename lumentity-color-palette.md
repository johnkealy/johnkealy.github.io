# Lumentity Color Palette — Reference & Agent Instructions

**Version:** 1.0 · November 3, 2026
**Scope:** All Lumentity marketing site pages (homepage, about, services + 4 subpages, work, FAQ, contact) and the Drupal theme build.
**Source of truth for tokens:** `HANDOFF-v4.md` §3. This document adds usage rules, verified contrast ratios, and instructions for AI agents generating or editing page code.

---

## 1. Tokens

| Token | Hex | Role |
|---|---|---|
| `--brand` | `#003366` | Primary. Headings, buttons, dark bands, logo cardinal arrows, links. The navy. |
| `--brand-light` | `#1a5490` | Hover states, kickers, in-body links. The *only* hover color for brand elements. |
| `--gold` | `#FFC107` | Accent. Eyebrow/kicker text on dark bands, primary CTA buttons, hero `<em>` highlights, logo diagonal arrowheads, icon mark. |
| `--ink` | `#1f2937` | Body text. |
| `--muted` | `#64748b` | Secondary/caption text. |
| `--bg` | `#f8fafc` | Page background. |
| `--card` | `#ffffff` | Cards, header, bands. |
| `--border` | `#e2e8f0` | Borders, dividers. |
| `--hero-dark` | `#0b2545` | Dark end of the hero gradient (`#003366 → #0b2545`); footer navy; icon background. |

Radius: `14px` for cards; `999px` (pill) for buttons. Typography: Inter in the drafts; brand direction is a Montserrat/Helvetica/Futura-family sans — swap at theme level, never per-page.

## 2. Verified contrast (WCAG 2.1, computed Nov 3, 2026)

| Pairing | Ratio | AA (4.5:1) |
|---|---|---|
| Ink on bg / card | 14.03 / 14.68 : 1 | PASS |
| Brand on white / bg | 12.61 / 12.05 : 1 | PASS |
| White on brand (buttons) | 12.61 : 1 | PASS |
| Gold on hero-dark | 9.44 : 1 | PASS |
| Ink on gold (gold-button text) | 9.01 : 1 | PASS |
| Gold on brand (kickers on bands) | 7.74 : 1 | PASS |
| Brand-light on white / bg | 7.74 / 7.39 : 1 | PASS |
| White on brand-light (hover) | 7.74 : 1 | PASS |
| Muted on white | 4.76 : 1 | PASS (narrow) |
| Muted on bg | 4.55 : 1 | PASS (narrow — see rule 4) |

## 3. Usage rules (do not regress)

1. **Navy and gold only as accent system.** Every page is built from these two voices: navy says "structure and trust" (headings, bands, buttons), gold says "look here" (CTAs, kickers on dark, emphasis). Do not introduce a third hue. No reds, greens, oranges for UI meaning.
2. **Gold never carries body text.** Gold is for eyebrows, kickers, button fills, and `<em>` highlights on dark backgrounds — always uppercase/small in its accent role. Gold buttons use **ink text** (`#1f2937` on `#FFC107`, 9.01:1), not white.
3. **Dark-band text is white or gold only.** On `--brand`/`--hero-dark` bands, body text is `#ffffff`; emphasis is `--gold`. Never place `--ink` or `--muted` on dark bands.
4. **`--muted` passes AA with little margin (4.55:1 on `--bg`).** Use it for secondary text at body size or larger only. Do not use muted below ~14px, and do not place muted text on tinted or image backgrounds — white/cards only.
5. **Links:** in-body links are `--brand-light` (7.39:1 on bg), hover to `--brand`. Never gold for inline links (fails against white).
6. **Alternating bands:** section bands alternate `--bg` / `--card` (white). Dark bands are reserved for heroes, the closing CTA band, and the footer — no more than one dark band per page besides hero/footer/CTA.
7. **Gradients:** the only gradient is the hero: `--brand → --hero-dark` (135°). Do not add gradients elsewhere; do not darken buttons with gradients.
8. **Icon mark:** gold arrows on `--hero-dark` with `rx 22` rounded square (see `icon.svg`). Do not recolor the icon per-context; it is fixed.

## 4. Instructions for AI agents

If you are an agent generating, editing, or reviewing Lumentity page code:

- **Use tokens, never raw hex**, except where a token does not exist (e.g., the gradient's two stops are the tokens themselves). Any new hex value is a design change requiring John's approval — do not invent colors, shades, or transparencies of existing colors.
- **Before generating text on a colored surface, check §2.** If a pairing is not listed, compute the WCAG ratio before using it; if it is below 4.5:1 for normal text or 3:1 for large text, it is wrong.
- **Do not "improve" contrast by changing colors.** The palette is brand-approved. If a combination fails, change the *combination* (e.g., move text to a card), not the color.
- **Buttons:** primary = `--brand` fill, white text; on dark bands primary = `--gold` fill, ink text. Outline buttons use 1px current-color border and inherit their context's text color. No other button styles.
- **States:** hover = `--brand-light` (navy elements) or slight darken of gold via `#e6ad06`; focus = 2px `--gold` outline with 2px offset on dark, `--brand` on light. Never remove focus outlines.
- **Dark mode does not exist.** Do not generate dark-mode variants or `prefers-color-scheme` blocks; the site is light-only by decision.
- **When in doubt, match an existing page.** Every pattern in this palette has a worked example in the v4 HTML package. Copy the existing implementation; do not redesign.
