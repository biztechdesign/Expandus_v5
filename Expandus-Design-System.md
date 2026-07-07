# Expandus Design System — v1

**Expandus Business Coaching** · franchise partner of ActionCOACH India
Brand line: *The Red Dot Theory™* — "Real coaches, real people, real results."

> Positioning: **premium authority with warmth.** Confident, grounded, results-focused — never hype-y.

This document is the single source of truth for the Expandus design system: brand voice, design tokens (color, type, spacing, radius, shadow), components, and usage rules. All values below reflect the current production tokens.

---

## 1. Brand foundations

### Voice & tone
Direct · Experienced · Empowering · Results-focused · Human.

- **Person** — address the reader as **"you / your"**; refer to the brand as **"we"**. Partnership framing, not prescription.
- **Casing** — **Sentence / title case** for headings, body, and CTAs. Never all-caps body copy. Tracked-out uppercase is reserved for **eyebrows and small labels only** (not buttons).
- **Specificity** — always cite real numbers: "1,000+ business owners", "3–4 decades of experience", "Senior Partner of the Year 2023". Avoid "many clients".
- **Lead with the outcome,** then the method.
- **CTAs are actions** — "Book a Consultation", "Start Your Growth Journey", "Talk to a Coach Today". Not descriptions.
- **No emoji.** Not part of the brand voice.

**Preferred phrasings:** "real coaches, real results" · "empowering business owners" · "scale your business" · "trusted partner" · "transformative results".

---

## 2. Color

Re-based on the official logo: **purple wordmark + coral accent**, anchored by a deep plum for dark sections.

### Brand palette
| Token | Hex | Role |
|---|---|---|
| `--color-purple` | `#643695` | **Primary** — brand identity & actions (buttons, links, focus) |
| `--color-purple-hover` | `#50276F` | Primary pressed / hover |
| `--color-purple-tint` | `#F1ECF8` | Faint purple wash (icon tiles, chips) |
| `--color-coral` | `#F04F53` | **Accent** — energy (eyebrows, numerals, Red Dot moments) |
| `--color-coral-hover` | `#D83A3E` | Darker coral |
| `--color-coral-tint` | `#FEEDED` | Faint coral wash |
| `--color-plum` | `#221331` | Deep dark anchor — nav, footer, hero |
| `--color-plum-soft` | `#34204A` | Raised surface on plum |

### Neutral ramp
| Token | Hex |
|---|---|
| `--color-gray-50` | `#F7F7F7` |
| `--color-gray-100` | `#EEEEEE` |
| `--color-gray-200` | `#E0E0E0` |
| `--color-gray-300` | `#DDDDDD` |
| `--color-gray-500` | `#888888` |
| `--color-gray-600` | `#666666` |
| `--color-gray-900` | `#222222` |

### Semantic aliases
| Token | Value | Use |
|---|---|---|
| `--color-primary` | purple | Brand & actions |
| `--color-accent` | coral | Accents |
| `--text-heading` | plum | All headings |
| `--text-body` | `#444444` | Body copy |
| `--text-muted-aa` | `#666666` | AA-safe muted (<18px) |
| `--surface-page` | white | Default page bg |
| `--surface-section` | `#F7F7F7` | Alternating section bg |
| `--surface-dark` | plum | Dark sections |
| `--overlay-scrim` | `rgba(0,0,0,0.55)` | Text-over-image scrim |
| `--border-default` | `#E0E0E0` | Card / input borders |
| `--focus-ring` | `0 0 0 3px rgba(100,54,149,0.18)` | Input focus ring |

**Status:** success `#28A745` · warning `#FFC107` · error `#DC3545`.

**Rule:** max ~3 color families per page. Purple for identity/actions, coral for accents, plum for dark surfaces.

---

## 3. Typography

**Headings:** Montserrat · **Body / UI:** Gordita Regular *(self-hosted via `fonts/Gordita-Regular.ttf` + `local('Gordita')`; Mulish is the offline fallback — always load Gordita first)*.

> **Decision (June 2026):** Gordita is the required body font — Mulish is fallback only. All body copy, buttons, labels, captions, and form elements use `--font-body` which resolves to Gordita.

- `--font-display` → `'Montserrat', …` (headings, hero titles, section/card headings)
- `--font-body` → `'Gordita', 'Mulish', …` (paragraphs, leads, buttons, forms, captions, pills)

Gordita loads via CDN + self-hosted `fonts/Gordita-Regular.ttf` + `local()`, falling back to Mulish.

### Responsive role scale (px / line-height)

| Role | Desktop | Tablet (≤1024) | Mobile (≤640) | Token |
|---|---|---|---|---|
| H1 | 56 / 64 | 48 / 56 | 40 / 48 | `--text-h1` |
| H2 | 48 / 56 | 40 / 48 | 32 / 40 | `--text-h2` |
| H3 | 40 / 48 | 32 / 40 | 24 / 32 | `--text-h3` |
| H4 | 32 / 40 | 24 / 32 | 20 / 28 | `--text-h4` |
| H5 | 24 / 32 | 20 / 28 | 18 / 26 | `--text-h5` |
| H6 | 16 / 24 | 16 / 24 | 16 / 24 | `--text-h6` |
| Body large | 16 / 24 | 16 / 24 | 15 / 24 | `--text-body-lg` |
| Body regular | 14 / 22 | 14 / 22 | 14 / 22 | `--text-body` |
| Body small | 13 / 20 | 13 / 20 | 13 / 20 | `--text-body-sm` |
| Button / CTA | 14 / 20 | 14 / 20 | 14 / 20 | `--text-button` |
| Caption / eyebrow | 13 / 20 | 13 / 20 | 13 / 20 | `--text-caption` |

Headings 600–700 weight with tight tracking (−0.01 to −0.02em). `tokens/base-typography.css` applies these to real `h1`–`h6`/`p` elements globally, with `text-wrap: balance/pretty` and `overflow-x: hidden` to prevent broken wraps and horizontal scroll.

### Weights
`--weight-regular: 400` · `--weight-medium: 500` · `--weight-semibold: 600` · `--weight-bold: 700`

---

## 4. CTA / Button typography rule

- **Size:** same as Body Regular — `--text-button` = **14px / 20px** at every breakpoint.
- **Weight:** **Bold / 700** (`--weight-cta`).
- **Font:** Gordita (`--font-body`).
- **No `text-transform: uppercase`** — natural title/sentence case exactly as written.
- **No wide letter-spacing.**
- **Border radius: 4px** — buttons are square, not rounded. `--radius-cta` is overridden to `4px` for all button elements.
- Applies to all primary, secondary, outline, and link-style CTAs. Adjust padding for tap targets, never font size.

---

## 5. Pills & badges

One unified pill component. Subtle, compact, premium.

| Property | Desktop | Tablet | Mobile | Token |
|---|---|---|---|---|
| Font size | 13px | 13px | 12px | `--text-pill` |
| Line-height | 18px | 18px | 16px | `--lh-pill` |
| Padding | 6px 12px | 5px 10px | 5px 10px | `--pad-pill` |
| Radius | 999px | — | — | `--radius-pill` |
| Weight | 600 | — | — | `--weight-pill` |
| Icon/dot gap | 6px | — | — | `--gap-pill` |

No uppercase, normal letter-spacing, natural case.

### Approved variants
| Variant | Use |
|---|---|
| `default` | General labels, section badges — subtle gray, dark text, thin border |
| `accent` | Red Dot / Chasm / Founder Dependency brand moments — coral tint |
| `success` | Positive stage/status (e.g. Investible) — green tint |
| `dark` | On dark plum sections — semi-transparent white, white text |
| `light` | On white / `#F7F7F7` surfaces — white bg, dark text, soft border |

Legacy aliases `primary` · `neutral` · `outline` retained for back-compat. Optional `dot` prop renders a 6px color-matched dot.

---

## 6. Spacing & layout

**8px base grid.**

| Token | Value | | Token | Value |
|---|---|---|---|---|
| `--space-xs` | 4px | | `--space-2xl` | 48px |
| `--space-sm` | 8px | | `--space-3xl` | 64px |
| `--space-md` | 16px | | `--space-4xl` | 80px |
| `--space-lg` | 24px | | `--space-5xl` | 100px |
| `--space-xl` | 32px | | | |

**Layout:** container max **1200px** (narrow 860, wide 1400) · sticky plum header **72px** · section padding ~80px (100px hero). Alternate white / light-gray sections — never 3+ same-bg in a row.

---

## 7. Corner radius

| Token | Value | Use |
|---|---|---|
| `--radius-sm` | **8px** | Icon buttons, small tags, compact UI |
| `--radius-md` | **12px** | CTAs, buttons, form fields, small cards |
| `--radius-lg` | **16px** | Main / feature / service / event cards |
| `--radius-xl` | **24px** | Hero visuals, large panels, premium sections |
| `--radius-pill` | **999px** | Pills, badges, tags only |

**Semantic aliases:** `--radius-card` → lg (16px) · `--radius-cta` → md (12px) · `--radius-form` → md (12px) · `--radius-icon` → sm (8px).

All CTAs share one radius (12px). All content cards share one radius (16px). No mixed values.

---

## 8. Elevation (shadows)

Brand-tinted soft shadows with a plum undertone — `rgba(16,10,35,…)`. No heavy or colored-glow shadows.

| Token | Value | Use |
|---|---|---|
| `--shadow-soft` | `0 8px 24px rgba(16,10,35,0.08)` | **Card default** |
| `--shadow-hover` | `0 12px 32px rgba(16,10,35,0.12)` | **Card hover lift** |
| `--shadow-dark-section` | `0 12px 32px rgba(0,0,0,0.18)` | On dark / plum backgrounds |
| `--shadow-pop` | `0 8px 24px rgba(16,10,35,0.12)` | Dropdowns / popovers |
| `--shadow-xl` | `0 12px 32px rgba(0,0,0,0.18)` | Modals |

**Rules:** cards rest at `--shadow-soft`, lift to `--shadow-hover` on hover. Dark sections use `--shadow-dark-section` or a subtle border. CTAs use no shadow or a very subtle one — never heavy button shadows.

---

## 9. Motion & interaction

- **Transitions** ~0.15–0.3s ease (`--transition-fast/normal/slow`).
- **Hover** — color shift / shadow lift. **Press** — `scale(0.98)`. No bounces, infinite loops, or parallax.
- **Focus** — visible 3px purple outline (offset 2px); inputs get purple border + `--focus-ring`.
- **Disabled** — opacity 0.45, `not-allowed`.
- Mobile: full-width buttons, min 44px tap targets.

---

## 10. Iconography

- **System:** flat line icons, ~1.75px stroke, consistent weight — never mix line + filled.
- **Implementation:** Lucide via CDN as a stand-in for Expandus's custom service icons.
- Plum on light surfaces, coral for accents, white on dark.
- Service icons sit in a 56–64px purple-tint rounded tile above the card title.
- **No emoji** as icons.

---

## 11. Components

React primitives, each with `.jsx` + `.d.ts`. Imported from the compiled bundle:

```js
const { Button, IconButton, Avatar, Card, Eyebrow, Badge, Checkbox, Input, Select }
  = window.ExpandusDesignSystem_1b82a0;
```

| Group | Components |
|---|---|
| `buttons/` | **Button** (primary / secondary / outline / text), **IconButton** |
| `forms/` | **Input**, **Select**, **Checkbox** |
| `feedback/` | **Badge** (5 pill variants + `dot`) |
| `content/` | **Card**, **Eyebrow**, **Avatar** |

---

## 12. File index

**Root** — `styles.css` (global entry; consumers link this), `readme.md`, `SKILL.md`.

**`tokens/`** — `fonts.css` · `colors.css` · `typography.css` · `spacing.css` · `effects.css` · `base-typography.css`.

**`fonts/`** — `Gordita-Regular.ttf` (self-hosted body face).

**`assets/`** — `expandus-logo.svg` (light bg) · `expandus-logo-footer.svg` (dark bg) · client logos.

**`components/`** — React primitives (see §11).

**`guidelines/`** — specimen cards for the Design System tab (Colors, Type, Spacing, Brand).

**`ui_kits/website/`** — interactive marketing-homepage recreation.

---

## 13. Usage

In any consumer HTML: link `styles.css`, load React + Babel + the generated `_ds_bundle.js`, then destructure components from `window.ExpandusDesignSystem_1b82a0`. **Always reference styling through CSS custom properties** (`var(--color-primary)`, `var(--space-lg)`, `var(--radius-card)`, …) — never hardcode hex or px from the scale.

---

*Expandus Design System v1 · Generated June 22, 2026*
