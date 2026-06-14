---
name: Family Dentists, PLLC
description: Gentle, modern family dentistry in Port Huron — Blue Water teal calm, cool mist neutrals, one quiet ink accent.
colors:
  brand-900: "#14333A"
  brand-800: "#1C454D"
  brand-700: "#2A5D66"
  brand-600: "#387079"
  brand-400: "#8FB4BA"
  brand-200: "#CBDFE1"
  brand-50: "#E8F1F2"
  cream: "#EAEFEC"
  paper: "#F6F8F7"
  ivory: "#FCFDFC"
  accent: "#47585C"
  accent-soft: "#D6E3E4"
  ink: "#1C231F"
  ink-mid: "#556159"
  ink-soft: "#616B65"
  line: "#DDE4E1"
  line-soft: "#E8EDEB"
typography:
  display:
    fontFamily: "Libre Caslon Display, Libre Caslon Text, Georgia, serif"
    fontSize: "clamp(2.6rem, 11vw, 4.8rem)"
    fontWeight: 400
    lineHeight: 1.02
    letterSpacing: "-0.02em"
  headline:
    fontFamily: "Libre Caslon Display, Libre Caslon Text, Georgia, serif"
    fontSize: "clamp(2rem, 6vw, 3rem)"
    fontWeight: 400
    lineHeight: 1.08
    letterSpacing: "-0.02em"
  title:
    fontFamily: "Libre Caslon Text, Georgia, serif"
    fontSize: "1.15rem"
    fontWeight: 400
    lineHeight: 1.2
    letterSpacing: "-0.01em"
  body:
    fontFamily: "Work Sans, system-ui, -apple-system, sans-serif"
    fontSize: "1rem"
    fontWeight: 400
    lineHeight: 1.65
  label:
    fontFamily: "Work Sans, system-ui, -apple-system, sans-serif"
    fontSize: "0.65rem"
    fontWeight: 600
    letterSpacing: "0.14em"
rounded:
  sm: "9px"
  md: "16px"
  lg: "25px"
  pill: "999px"
spacing:
  section: "96px"
  section-tight: "72px"
  card: "26px 22px"
  button: "16px 26px"
components:
  button-primary:
    backgroundColor: "{colors.brand-900}"
    textColor: "{colors.ivory}"
    rounded: "{rounded.pill}"
    padding: "{spacing.button}"
  button-primary-hover:
    backgroundColor: "{colors.brand-800}"
  button-ghost:
    backgroundColor: "transparent"
    textColor: "{colors.brand-900}"
    rounded: "{rounded.pill}"
    padding: "{spacing.button}"
  button-ghost-hover:
    backgroundColor: "{colors.brand-50}"
  card-service:
    backgroundColor: "{colors.paper}"
    rounded: "{rounded.md}"
    padding: "{spacing.card}"
---

# Design System: Family Dentists, PLLC

> **Doc status:** Regenerated from the shipped `index.html` (`/impeccable document`), then updated for the v1.2.0 **Blue Water teal** palette. This file reflects what the code actually renders. The brand color moved sage-green → indigo → its settled deep-teal direction over successive releases; because the **token names are hue-agnostic roles** (`--brand-*`, `--accent`), each palette change was a values-only edit in `:root`.

## 1. Overview

**Creative North Star: "The Calm Blue Water Practice"**

The interface translates a quiet, modern practice lobby into deep Blue Water teal authority over cool mist neutrals, with a full-bleed photographic hero carrying the human warmth. Everything is soft-spoken on purpose — the audience includes anxious patients, and the design persuades by lowering their shoulders, not by raising its voice. A light-weight serif (Libre Caslon Text) carries humanity in the headlines; a humanist sans (Work Sans) does the practical talking.

The system rejects corporate dental-chain aesthetics (bleached-smile stock, discount urgency), sterile hospital whites, and cutesy pediatric clichés. It stays gentle without being childish and modern without being cold.

**Key characteristics:**
- Deep Blue Water teal (`--brand-900`) carries identity and all interactive weight; cool "mist" neutrals (`--brand-50/200/400`) do the structural and tinting work.
- Cool, near-white surfaces (`--paper`, `--cream`, `--ivory`) — never pure white, never warm cream.
- Light-weight serif display type with an italic `em` inflection (in `--brand-700`) as the signature emphasis move.
- Fully rounded pill buttons; generously rounded cards (9 / 16 / 25px effective scale, via `--radius-mul: 0.9`).
- Whisper-quiet elevation: teal-tinted shadows `rgba(20,51,58,…)` that only assert on hover/float.
- A full-bleed hero photo with a subtle scroll parallax and a soft-light ambient canvas glow, both gated by `prefers-reduced-motion`.

## 2. Colors

A single-theme **Blue Water teal + mist** palette, Restrained-leaning-Committed: deep teal carries identity and every interactive surface; the accent is a quiet slate, used sparingly.

### Brand (Blue Water teal ramp)
- **Brand 900** (`#14333A`): the brand's voice — primary buttons, brand mark, headline ink on light sections, and the dark contact/footer band. Reads almost-black but stays a deep blue-green teal — a nod to the Blue Water Area / Lake Huron, and deliberately not "insurance-brochure blue."
- **Brand 800** (`#1C454D`): hover state for primary actions; secondary dark surface (map backdrop).
- **Brand 700** (`#2A5D66`): italic `em` accents inside headlines, hero eyebrow, service icons, focus ring.
- **Brand 600** (`#387079`): section-label (Plus-Kicker) text — tuned to clear WCAG AA 4.5:1 on every light surface, including the cream Doctors section.
- **Brand 400 / 200 / 50** (`#8FB4BA` / `#CBDFE1` / `#E8F1F2`): ghost-button borders, selection highlight, icon chips, hover fills, in descending presence.

### Accent
- **Accent** (`#47585C`): a quiet slate ink — used as a restrained secondary ink, not a button color and not at layout scale.
- **Accent Soft** (`#D6E3E4`): the cool chip behind small emphasis (emergency label text, mobile emergency button fill).

### Neutral
- **Paper** (`#F6F8F7`): body background and card surface.
- **Cream** (`#EAEFEC`): alternating section background (doctors) — one perceptible step deeper than paper.
- **Ivory** (`#FCFDFC`): surfaces and text on the dark teal bands.
- **Ink / Ink-Mid / Ink-Soft** (`#1C231F` / `#556159` / `#616B65`): heading, prose, and fine-print text. (`--ink-soft` was darkened from `#8A938C` to clear WCAG AA 4.5:1 on every light surface, including cream.)
- **Line / Line-Soft** (`#DDE4E1` / `#E8EDEB`): hairline borders and dividers; never darker than this.

### Named rules
- **The Never-Clinical Rule.** No pure white (`#FFFFFF`) backgrounds and no cold blue-grays for structure; the teal ramp itself supplies the cool, and neutrals stay just off-white.
- **The Single-Theme Rule.** This site ships one theme. There is no dark mode; the dark teal bands (contact, footer, hero overlay) are compositional, not a theme toggle.
- **The Status-Green Exception.** The one non-palette hue is the "Now welcoming new patients" pulse dot (`#52A77C`) — a semantic availability indicator, deliberately not a brand color.

## 3. Typography

**Two optical cuts of one serif, plus a humanist sans:**
- `--font-display` — **Libre Caslon Display** (Caslon Text → Georgia fallback): the high-contrast headline cut, used only on the fluid `clamp()` display headings (hero h1, section titles, CTA). This is the honest replacement for the old dead `font-variation-settings: "opsz" 144` — Caslon Text is not a variable font, so a real display cut carries the large-size refinement instead.
- `--font-serif` — **Libre Caslon Text**: every fixed-size serif under ~2rem (card/feature/doctor titles, the pull-quote, contact headings, the wordmark) **and every italic `em`** (the Display cut has no italic, so emphasis routes back to Caslon Text Italic).
- `--font-sans` — **Work Sans** (system-ui fallback), weights 300/400/500/600.

**Character:** a high-contrast serif that feels hand-set and unhurried, paired with a rounded humanist sans that stays invisible. The signature move is the italic `em` inside headlines (`every <em>smile</em>`) in `--brand-700` — emphasis as warmth, not loudness. The Display roman + Text italic sit together deliberately, the way an editorial masthead pairs a display face with a text italic.

> Weights are honest: Caslon (both cuts) is used at **400** everywhere (it ships only 400/700; the earlier `font-weight: 300` declarations were no-ops that silently rendered 400).

> **Loading.** Fonts are **self-hosted** (latin subset) in `assets/fonts/` via inline `@font-face`, `font-display: swap` — no Google Fonts round-trip, no third-party data dependency (relevant for a medical site). Work Sans is a single variable file (`wght 300–600`); Caslon Display and Caslon Text (roman + italic) are static. The two dominant above-the-fold faces (Caslon Display, Work Sans) are `<link rel="preload">`ed. Total ≈ 100 KB across four files.

### Hierarchy
- **Display** (400, `--font-display`, `clamp(2.6rem, 11vw, 4.8rem)`, 1.02): hero headline only.
- **Headline** (400, `--font-display`, `clamp(2rem, 6vw, 3rem)`, 1.08): section titles; each contains one italic `--brand-700` `em` phrase (in `--font-serif`).
- **Title** (400, `--font-serif`, 1.15rem): card / service / doctor / feature headings (the former 1.18rem `.about-point-title` was unified to the 1.15rem Title size).
- **Body** (400, ~1rem, 1.65–1.7): prose; constrained to ≤56ch via `.section-body`.
- **Label** (600, 0.65rem, 0.14em tracking, uppercase): the section kicker, preceded by a `+` glyph in `--brand-400`.

### Named rules
- **The Plus-Kicker.** Section labels are uppercase Work Sans at 0.14em tracking with a leading `+` mark. Applied to **every left-aligned content section** (About, Services, Doctors, Comfort, Contact) as one deliberate wayfinding system; the hero and the centered closing CTA deliberately omit it.
- **The Light Serif Rule.** Caslon never appears bolder than 400 in layout. Hierarchy comes from size and the italic-`em` inflection, never from heavy weights.
- **Aligned figures.** The office-hours times use `font-variant-numeric: tabular-nums` so digits and the AM/PM column line up down the list.
- **Light-on-dark compensation.** Body text on the dark teal bands gets a touch of extra tracking (`letter-spacing: 0.01em` on `.contact .section-body`) plus the looser 1.7 line-height, since light type on dark reads lighter and tighter than it measures.

## 4. Elevation

Depth is whisper-quiet and teal-tinted: shadows use `rgba(20,51,58,…)`, never neutral black, and surfaces are flat at rest with hairline `--line-soft` borders doing the structural work. Shadows assert only in response — hover lifts and genuine floats.

- **Hairline** `--shadow-xs` (`0 1px 2px / 0 2px 6px rgba(20,51,58,0.04)`): resting definition for small floats (badges).
- **Hover Lift** `--shadow-sm` (`0 4px 18px rgba(20,51,58,0.06)`): cards and primary buttons on hover, paired with a small translateY.
- **Float** `--shadow-md` (`0 12px 40px rgba(20,51,58,0.10)`): hero media, the drawer, the mobile call bar.

**The Flat-at-Rest Rule.** Cards rest on borders, not shadows. A shadow is a response to attention (hover) or genuine float (fixed bars), never decoration.

## 5. Components

- **Buttons.** Fully rounded pill (999px), inline-flex with a 16px icon and 10px gap. *Primary:* `--brand-900` bg, ivory text, 16/26 padding; hover `--brand-800`, −2px lift, Hover-Lift shadow. *Ghost:* transparent, `--brand-400` 1px border, `--brand-900` text; hover `--brand-50` fill, `--brand-600` border.
- **Cards / containers.** Used sparingly — only where content is genuinely distinct and the box earns its place: the two **doctor** portrait cards and the single **Urgent Care** callout. 16px standard radius (`--radius`), 25px for hero/large frames (`--radius-lg`); flexes via `--radius-mul`. 1px `--line-soft` at rest → `--brand-200` on hover. Flat-at-Rest. **Not** used for Services or Comfort.
- **Service / feature lists (not cards).** Services and the About points are **editorial row lists**, not card grids: a 44px `--brand-50` icon chip + serif title + `--ink-mid` description per row, hairline-separated, flowing in 1–2 columns (`.service-list.cols-2`, 1-col under 720px). Comfort is a borderless 3-up layout with a top hairline per item. This is the page's default for "a list of things" — cards are the exception, not the reflex. The lone **Urgent Care** callout is the deliberate exception: one tinted, rounded, `--accent-soft`-bordered block for emphasis.
- **Navigation.** Fixed 64px bar over blurred paper (`rgba(251,249,244,0.82)`, 14px backdrop blur); bottom hairline fades in on scroll. Desktop nav links carry a **44px min hit area** (flex-centered, hover underline re-anchored) for touch-capable laptops. Mobile gets a full-screen drawer and a slide-up call bar (`--brand-900` call button + accent-soft emergency button). Brand mark is a `--brand-900` circle with an ivory tooth glyph.
- **Section header (signature).** Plus-Kicker label → light Caslon headline with one italic `--brand-700` phrase → ≤56ch `--ink-mid` body.
- **Containers.** `.wrap` caps content at 1240px and centers it (matches hero / trust); `.wrap-narrow` caps at 760px for prose-led sections.

## 6. Motion

- **Scroll reveals:** `.reveal` elements translate up 14px + fade over .9s on the `--ease` curve `cubic-bezier(.2,.7,.2,1)`, staggered ≤0.24s, via IntersectionObserver. `will-change` is applied only while pending (`.reveal:not(.in)`) and dropped after reveal.
- **Hero parallax:** the full-bleed background translates on scroll (rAF-throttled, passive) — **disabled when `prefers-reduced-motion: reduce`**.
- **Ambient canvas:** slow teal light orbs in soft-light blend over the hero photo; renders at ¼ resolution, pauses off-screen via IntersectionObserver, and is **disabled under reduced motion**.
- **Reduced motion is mandatory.** Every animation has a reduced-motion fallback: reveals render instantly, parallax and the ambient canvas switch off, the status-dot pulse stops, and `scroll-behavior` reverts to `auto`.

## 7. Do's and Don'ts

### Do
- Keep a tap-to-call (`tel:8109878310`) reachable in every fold — it is the only conversion.
- Keep the full-bleed hero text legible **independent of the photo**: white type carries a soft `text-shadow` plus a strengthened bottom-left scrim, so a brighter hero image can't silently break contrast.
- Use the italic `--brand-700` `em` inside every Caslon headline; it is the brand's emphasis voice.
- Tint every shadow teal (`rgba(20,51,58,…)`) and keep neutrals just-off-white and cool.
- Honor `prefers-reduced-motion` for any new animation — no exceptions.
- Treat `--brand-*` / `--accent` as roles: change the values to retheme, never hard-code a hex outside `:root`.

### Don't
- Don't introduce corporate dental-chain aesthetics: bright insurance-brochure blue, bleached-smile stock, discount banners, urgency offers.
- Don't go clinical: no pure white backgrounds, no cold blue-grays for structure, no portal density.
- Don't go cutesy: no cartoon tooth mascots or primary-color confetti.
- Don't set Caslon above weight 400 or below −0.02em letter-spacing in layout.
- Don't add gradient text, side-stripe card borders, glassmorphism beyond the existing nav/badge/mobile-bar blur, or hero-metric stat blocks.
- Don't reintroduce hard-coded warm (terracotta) tints or off-palette hues in CSS/JS — the theme is the cool Blue Water teal ramp; the only sanctioned non-palette hue is the green availability dot.

## 8. Open decisions (for the practice / client)

- **Brand color direction — settled (v1.2.0).** After a side-by-side of indigo / sage / deep-teal, the practice chose **Blue Water teal**: warmer and calmer than the prior indigo, regionally rooted, and clear of both "insurance-brochure blue" and the common sage/wellness reflex. Because tokens are role-based, the swap was a values-only edit in `:root`. (Comparison artifact: `brand-options.html`.)
- **Source-image hygiene.** The 4K source files (`hero-1.png`, `hero-2.png`, `team-sign.jpg`, `team.JPG`) remain in `assets/` but are no longer referenced by the page; the responsive `-1280/-1920/-2560` and `-768/-1160` AVIF/WebP/JPEG derivatives are what ship. Consider moving sources out of the deploy path.
