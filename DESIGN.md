---
name: Family Dentists, PLLC
description: Gentle, modern family dentistry in Port Huron — sage calm, warm paper, one terracotta highlight.
colors:
  sage-deepest: "#22332C"
  sage-deep: "#2F4A3F"
  sage: "#3F6051"
  sage-mid: "#577F6C"
  sage-soft: "#9EB5A5"
  sage-mist: "#D6E0D6"
  sage-wash: "#EEF2EC"
  warm-paper: "#FBF9F4"
  cream: "#F6F2EA"
  ivory: "#FFFDF8"
  terracotta: "#C97B5E"
  terracotta-wash: "#F1DDD3"
  ink: "#1C231F"
  ink-mid: "#556159"
  ink-soft: "#8A938C"
  line: "#E6E1D5"
  line-soft: "#EFEAE0"
typography:
  display:
    fontFamily: "Fraunces, Cormorant Garamond, Georgia, serif"
    fontSize: "clamp(2.4rem, 7vw, 3.9rem)"
    fontWeight: 300
    lineHeight: 1.06
    letterSpacing: "-0.02em"
  headline:
    fontFamily: "Fraunces, Cormorant Garamond, Georgia, serif"
    fontSize: "clamp(2rem, 6vw, 3rem)"
    fontWeight: 300
    lineHeight: 1.08
    letterSpacing: "-0.02em"
  title:
    fontFamily: "Fraunces, Cormorant Garamond, Georgia, serif"
    fontSize: "1.15rem"
    fontWeight: 400
    lineHeight: 1.3
    letterSpacing: "-0.01em"
  body:
    fontFamily: "Figtree, system-ui, -apple-system, sans-serif"
    fontSize: "1rem"
    fontWeight: 400
    lineHeight: 1.65
  label:
    fontFamily: "Figtree, system-ui, -apple-system, sans-serif"
    fontSize: "0.72rem"
    fontWeight: 500
    letterSpacing: "0.2em"
rounded:
  sm: "10px"
  md: "18px"
  lg: "28px"
  pill: "999px"
spacing:
  section: "96px"
  section-tight: "72px"
  card: "26px 22px"
  button: "16px 26px"
components:
  button-primary:
    backgroundColor: "{colors.sage-deepest}"
    textColor: "{colors.ivory}"
    rounded: "{rounded.pill}"
    padding: "{spacing.button}"
  button-primary-hover:
    backgroundColor: "{colors.sage-deep}"
  button-ghost:
    backgroundColor: "transparent"
    textColor: "{colors.sage-deepest}"
    rounded: "{rounded.pill}"
    padding: "{spacing.button}"
  button-ghost-hover:
    backgroundColor: "{colors.sage-wash}"
  card-service:
    backgroundColor: "{colors.warm-paper}"
    rounded: "{rounded.md}"
    padding: "{spacing.card}"
---

# Design System: Family Dentists, PLLC

## 1. Overview

**Creative North Star: "The Sunlit Waiting Room"**

This system translates the feeling of a calm, plant-filled practice lobby into an interface: warm paper light, deep sage authority, and one terracotta highlight like a friendly object in the room. Everything is soft-spoken on purpose — the audience includes anxious patients, and the design persuades by lowering their shoulders, not by raising its voice. The serif (Fraunces at light weights, optical size maxed) carries warmth and humanity; the sans (Figtree) does the practical talking.

The system explicitly rejects corporate dental-chain aesthetics (insurance-brochure blue, bleached-smile stock photos, discount urgency), sterile hospital whites, and cutesy pediatric clichés. It is gentle without being childish, and modern without being cold.

**Key Characteristics:**
- Warm paper surfaces with sage-tinted structure; color temperature never drops to clinical white-gray
- Light-weight serif display type with italic `em` inflections as the signature emphasis move
- Fully rounded pill buttons; generously rounded cards (10/18/28px scale)
- Whisper-quiet elevation: sage-tinted shadows that only assert on hover
- Gentle 14px scroll-reveals with full reduced-motion fallback

## 2. Colors

A sage-and-paper palette in the Restrained-leaning-Committed strategy: deep sage carries identity and all interactive weight; terracotta appears once per view, if at all.

### Primary
- **Deepest Sage** (#22332C): the brand's voice — primary buttons, nav brand mark, headline ink on light sections, and the background of the dark contact/footer band. Reads almost-black but stays warm and green.
- **Deep Sage** (#2F4A3F): hover state for primary actions; secondary dark surface.
- **Sage** (#3F6051): italic `em` accents inside headlines, section-label text, service icons — the mid-tone that links ink to mist.
- **Soft Sage** (#9EB5A5) / **Sage Mist** (#D6E0D6) / **Sage Wash** (#EEF2EC): ghost-button borders, selection highlight, icon chips, and tinted hover fills, in descending order of presence.

### Secondary
- **Warm Terracotta** (#C97B5E): the single warm accent — the emergency-care icon, small moments of warmth. Never a button color, never decoration at scale.
- **Terracotta Wash** (#F1DDD3): the soft chip behind a terracotta icon.

### Neutral
- **Warm Paper** (#FBF9F4): the body background and card surface.
- **Cream** (#F6F2EA): alternating section background (doctors, image placeholders) — one perceptible step deeper than paper.
- **Ivory** (#FFFDF8): text and surfaces on dark sage backgrounds.
- **Ink** (#1C231F) / **Ink Mid** (#556159) / **Ink Soft** (#8A938C): body text hierarchy — headings, prose, and fine print respectively.
- **Line** (#E6E1D5) / **Line Soft** (#EFEAE0): hairline borders on cards and dividers; never darker than this.

### Named Rules
**The One Warm Thing Rule.** Terracotta appears at most once per viewport, always small (an icon, a highlight) and always meaningful (emergency care). If terracotta is carrying layout-scale area, it's wrong.

**The Never-Clinical Rule.** No pure white (#FFFFFF) backgrounds and no cool grays anywhere. Every neutral leans warm; every gray is actually a desaturated sage or warm ink.

## 3. Typography

**Display Font:** Fraunces (with Cormorant Garamond, Georgia fallback) — variable optical size, used at `opsz` 144
**Body Font:** Figtree (with system-ui fallback)

**Character:** A light-weight, high-optical-size serif that feels hand-set and unhurried, paired with a rounded humanist sans that stays invisible. The signature move is the italic `em` inside headlines ("every <em>smile</em>") set one weight up (400) in mid sage — emphasis as warmth, not loudness.

### Hierarchy
- **Display** (300, clamp(2.4rem, 7vw, 3.9rem), 1.06): hero headline only.
- **Headline** (300, clamp(2rem, 6vw, 3rem), 1.08): section titles; always contains one italic sage `em` phrase.
- **Title** (400, 1.15rem, serif): card and service headings.
- **Body** (400, 1rem/1.02rem, 1.65–1.7): prose; constrained to ≤56ch via `.section-body`.
- **Label** (500, 0.72rem, 0.2em tracking, uppercase): the section kicker — always preceded by a 20px sage rule (`::before` dash).

### Named Rules
**The Dash-Kicker Rule.** Section labels are a committed brand system: uppercase Figtree at 0.2em tracking with a leading 20px sage hairline. Use it on every major section or not at all — it is the one allowed eyebrow, and the dash is what makes it ours.

**The Light Serif Rule.** Fraunces never appears bolder than 400. Hierarchy comes from size and the italic-sage inflection, never from heavy weights.

## 4. Elevation

Depth is whisper-quiet and warm: shadows are tinted with deepest sage (rgba(34,51,44,…)), never neutral black, and surfaces are flat at rest with hairline `--line-soft` borders doing the structural work. Shadows assert only in response — hover lifts (cards −3px, buttons −2px) and the floating mobile call bar.

### Shadow Vocabulary
- **Hairline** (`box-shadow: 0 1px 2px rgba(34,51,44,0.04), 0 2px 6px rgba(34,51,44,0.04)`): resting definition for badges and small floats.
- **Hover Lift** (`box-shadow: 0 4px 18px rgba(34,51,44,0.06)`): cards and primary buttons on hover, paired with a small translateY.
- **Float** (`box-shadow: 0 12px 40px rgba(34,51,44,0.10)`): hero media, the map block, the mobile action bar — things that sit above the page.

### Named Rules
**The Flat-at-Rest Rule.** Cards rest on borders, not shadows. A shadow is a response to attention (hover) or genuine float (fixed bars), never decoration.

## 5. Components

### Buttons
- **Shape:** fully rounded pill (999px), inline-flex with a 16px icon and 10px gap.
- **Primary:** Deepest Sage background, Ivory text, 16px 26px padding. Hover: Deep Sage, −2px lift, Hover Lift shadow.
- **Ghost:** transparent with Soft Sage 1px border, Deepest Sage text. Hover: Sage Wash fill, Sage Mid border.
- **Focus:** follows the same transitions (transform .2s, colors .25s on the shared `--ease` curve `cubic-bezier(.2,.7,.2,1)`).

### Cards / Containers
- **Corner Style:** 18px standard (`--radius`), 28px for hero media and large frames (`--radius-lg`); the whole scale flexes via `--radius-mul`.
- **Background:** Warm Paper on tinted sections; Cream for image placeholder frames.
- **Border:** 1px Line Soft at rest, warming to Sage Mist on hover.
- **Shadow Strategy:** Flat-at-Rest Rule — hover lift only.
- **Internal Padding:** 26px 22px (service cards).

### Service Icon Chips
- **Style:** 44px square, 12px radius, Sage Wash background with Sage icon at 1.6 stroke. The emergency variant swaps to Terracotta Wash + Terracotta (the One Warm Thing).

### Navigation
- Fixed 64px bar over blurred Warm Paper (rgba(251,249,244,0.82), 14px backdrop blur); bottom hairline fades in on scroll. Links are Ink Mid 0.9rem with an underline that slides in left-to-right on hover. Brand mark is a Deepest Sage circle with an Ivory tooth glyph. Mobile gets a full-screen drawer and a slide-up call bar (Deepest Sage call button + ghost directions button).

### Section Header (signature)
The repeating cadence that structures the page: Dash-Kicker label → light Fraunces headline with one italic sage phrase → ≤56ch Ink Mid body. Every new section must use this stack; it is the grammar of the site.

## 6. Do's and Don'ts

### Do:
- **Do** keep a tap-to-call action reachable in every fold — `tel:8109878310` is the only conversion (PRODUCT.md: "The phone call is the only conversion").
- **Do** use the italic sage `em` inside every Fraunces headline; it is the brand's emphasis voice.
- **Do** tint every shadow with sage (rgba(34,51,44,…)) and every neutral warm.
- **Do** honor `prefers-reduced-motion` for any new animation — instant reveals, no exceptions.
- **Do** keep scroll-reveal motion at or below the current gentleness: 14px translate, .9s ease-out, ≤0.24s stagger.

### Don't:
- **Don't** introduce corporate dental-chain aesthetics: insurance-brochure blue, stock bleached-smile photography, discount banners, or urgency offers (PRODUCT.md anti-reference, verbatim).
- **Don't** go clinical: no pure white backgrounds, no cool grays, no portal-density layouts.
- **Don't** go cutesy: no cartoon tooth mascots or primary-color confetti — family-friendly is not childish.
- **Don't** use terracotta as a button color or at layout scale; it is an accent for one warm thing per view.
- **Don't** set Fraunces above weight 400 or below −0.02em letter-spacing.
- **Don't** add gradient text, side-stripe card borders, glassmorphism beyond the existing nav blur, or hero-metric stat blocks (PRODUCT.md: "generic AI landing-page tells").
