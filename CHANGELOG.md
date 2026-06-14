# Changelog

All notable changes to the Family Dentists, PLLC website will be documented in this file.

## [v1.2.0] - 2026-06-13

### Brand color — Indigo → Blue Water teal

The practice settled its brand-color direction (the last open item in DESIGN.md §8). After a side-by-side mockup of three candidates — indigo, sage, and deep teal (`brand-options.html`) — the choice is **Blue Water teal**: warmer and calmer than the shipped indigo, regionally rooted (the Blue Water Area / Lake Huron), and clear of both the brief's "insurance-brochure blue" anti-reference *and* the common sage/wellness-cliché reflex.

- **Palette swap (values-only).** Re-themed the nine role-based tokens in `:root` — `--brand-900…50`, `--accent`, `--accent-soft` — from the indigo ramp to the teal ramp (`#1E2540` → `#14333A`, and so on). Because the audit pass had already renamed every literal to a hue-agnostic role, no component CSS or markup changed.
- **WCAG-AA tuned, not eyeballed.** Verified every brand color against the surface it actually sits on (computed luminance/contrast). `--brand-600` (the Plus-Kicker eyebrow) was set to `#387079` — a touch darker than the mockup value — so it clears 4.5:1 on the **cream** Doctors-section background (4.80), not just on paper/ivory; the lighter mockup hex would have landed at 4.40 there.
- **Off-token literal sweep.** Re-tinted everything the token swap doesn't reach: the `theme-color` meta (`#14333A`), the favicon's hard-coded SVG stroke, the three indigo-tinted shadow values (`rgba(30,37,64,…)` → `rgba(20,51,58,…)`), the ambient-canvas orb colors, the `console.log` brand colors, and a dead `--accent-soft` CSS fallback. No half-teal/half-indigo edges remain.
- **Battle-tested** desktop + true-mobile via headless full-page capture (reduced-motion so reveals resolve): teal verified on the nav, hero, light content sections, the cream Doctors band, and the dark contact/CTA band. The status-green "Now welcoming new patients" dot is deliberately retained as the one sanctioned non-palette hue.

### Docs
- **DESIGN.md** re-synced to the teal system (North Star, color ramp, elevation, motion, do's/don'ts); §8 "Brand color direction" marked **settled**.
- Added **`brand-options.html`** — the three-way comparison board, kept in-repo as decision provenance.

## [v1.1.2] - 2026-06-13

### Layout — break the card-grid pattern (`/impeccable layout`)

- **Services: cards → editorial row list.** Replaced the 9 icon+heading+text cards (2/4-up grids) with hairline-separated rows (sage icon chip + serif title + description) flowing in two columns per category — the same calm, scannable grammar the About section uses. The "identical card grids" anti-pattern is gone.
- **Urgent Care** is now one deliberate emphasized callout (tinted, rounded, accent-bordered) instead of a card in the grid.
- **Comfort: de-carded** to an airy borderless 3-up layout with a top hairline per item — a distinct rhythm from the Services rows.
- **Unified the section eyebrow cadence.** The Plus-Kicker now appears on every left-aligned content section (added to Services + Comfort); the hero and centered CTA deliberately omit it. Resolves the prior 3-of-6 inconsistency.
- Removed the now-dead card CSS (`.service` card, `.group-grid-*`, `.comfort-item` box + hover-lift) and the stale 4-column comfort override.

## [v1.1.1] - 2026-06-13

### Typography & Font-Loading (`/impeccable typeset` + `/impeccable optimize`)

**Typeset**
- Added **Libre Caslon Display** (`--font-display`) for the fluid display headings (hero, section titles, CTA) — the honest replacement for the dead `font-variation-settings: "opsz" 144` (Caslon Text is not a variable font). Italic `<em>` emphasis routes to Caslon Text Italic.
- Removed 3 dead `opsz` declarations and made 6 serif `font-weight: 300` → 400 (Caslon ships only 400/700; 300 was a silent no-op).
- `tabular-nums` on the office-hours times; `+0.01em` light-on-dark tracking on `.contact .section-body`; unified `.about-point-title` 1.18rem → the documented 1.15rem Title size.

**Optimize — self-hosted fonts**
- **Removed the Google Fonts dependency entirely.** Dropped the two cross-origin preconnects + render-blocking `fonts.googleapis.com` stylesheet; fonts are now **self-hosted** (latin subset) in `assets/fonts/` via inline `@font-face`.
- Work Sans ships as a single **variable** woff2 (`wght 300–600`); Caslon Display + Caslon Text (roman/italic) are static. ≈100 KB total across 4 files.
- `<link rel="preload">` on the two dominant above-the-fold faces (Caslon Display, Work Sans). Net effect: no third-party round-trip, faster FCP/LCP on mobile, and no Google data dependency (privacy — relevant for a medical practice).

## [v1.1.0] - 2026-06-13

### Production-Readiness Audit Remediation (`/impeccable audit` → fixes)

A technical audit pass addressing the highest-impact accessibility, performance, responsive, and theming findings before launch.

### ⚡ Performance
- **Hero image: 8.5 MB → ~40 KB.** Re-encoded the 4K PNG hero into responsive AVIF/WebP/JPEG sets (1280/1920/2560w) served via `<picture>` + `srcset`, with `fetchpriority="high"` on the LCP image. The `about` team photo got the same treatment (1.6 MB → ~167 KB, 768/1160w). Removed the duplicate eager hero download (the hidden layout-fallback `<img>` now lazy-loads optimized sources).
- **Trimmed web-font request** to only the weights actually used (Caslon 400 + italic; Work Sans 300/400/500/600 — dropped unused 700s).
- **`will-change`** is now applied only while a reveal is pending (`.reveal:not(.in)`) and dropped after, instead of living permanently on ~20 elements.

### ♿ Accessibility
- **Parallax now honors `prefers-reduced-motion`** (it previously did not, contradicting the project's own motion-sensitivity promise); `scroll-behavior` reverts to `auto` under reduced motion.
- **Contrast fixes:** darkened `--ink-soft` (`#8A938C` → `#616B65`, AA-clear on paper/cream/ivory) and raised the "Closed"-hours and footer-attribution opacities to clear WCAG AA 4.5:1 on their backgrounds.
- **Map iframe** given a `title` and `tabindex="-1"` so keyboard focus no longer lands on the hidden embed.
- **Heading hierarchy:** service-card titles demoted `h3 → h4` so they nest correctly under their `h3` group labels.

### 📐 Responsive
- **Defined the missing `.wrap` container** (`max-width: 1240px`, centered). Five main sections (About, Services, Doctors, Comfort, Contact) previously sprawled edge-to-edge on large screens because the class had no rule.
- **Trust strip** now wraps on narrow screens instead of silently clipping behind a hidden scrollbar.

### 🎨 Theming
- **Role-based tokens:** renamed `--sage-*` → `--brand-*` and `--terracotta(-soft)` → `--accent(-soft)` so names match the indigo values (and survive any future palette change).
- **Purged leftover warm/green literals** that clashed with the indigo theme: the ambient canvas orbs (terracotta → indigo/periwinkle), the emergency box and mobile emergency-button border, and the Google Map backdrop/filter (now neutral).

### 🔎 SEO / Production
- Added **Open Graph + Twitter** meta, a **`theme-color`**, geo meta, and a **`Dentist` JSON-LD** block (address, geo, both phone numbers, opening hours, founders) for local search and rich social previews.
- Regenerated **DESIGN.md** from the shipped code (the prior version still described the retired sage/Fraunces system).

### 🧹 Code Quality
- Removed dead `.services-grid` CSS rules (no element used the class).

## [v1.0.0] - 2026-06-13

### The "Sunlit Waiting Room" Release

This foundational release establishes a high-quality, production-ready marketing site tailored to the "Gentle, warm, unhurried" brand personality. The interface has been completely refined from its initial scaffolding into a bespoke, performant, and accessible experience.

### 🎨 Design & Typography
- **Hardcoded Brand State**: Locked in the cohesive "Indigo/Ink/Mist" palette, removing all placeholder/preview theming logic.
- **Distinctive Typography**: Replaced the overused Fraunces font with **Libre Caslon Text** (for a stable, unhurried voice) and **Work Sans** (for clean humanist clarity).
- **Human Trust Anchors**: Replaced cold placeholder initials (JP/JH) with warm, professional portraits of Dr. Jeremy Parrott and Dr. Julie Anne Hengehold sourced directly from the practice.
- **Atmospheric Imagery**: Updated the "About" section placeholder with a high-quality interior shot of a modern, sunlit dental office.
- **Custom Favicon**: Implemented an SVG-based tooth glyph (`🦷`) utilizing the brand's Deepest Sage (`#1E2540`) color, serving as a lightweight and immediate brand anchor.

### ✨ Interactions & Overdrive (Motion)
- **Ambient Sunlit Canvas (Overdrive)**: Engineered a highly-optimized HTML5 Canvas layer behind the hero section. It renders slow-moving, warm light blobs blended via `soft-light` to emulate sunlight moving through a calm waiting room. Automatically pauses off-screen via `IntersectionObserver`.
- **Deliberate Animation**: Removed saturated "AI grammar" (generic fade-and-rise reveals on every text block). Motion is now purposefully reserved for the hero entrance and staggered lists (service cards, doctor profiles, comfort touches).
- **Tactile Micro-interactions**: Added subtle, satisfying hover and active states:
  - Cards and buttons lift and cast a warm sage shadow.
  - The map pin physically "lifts" when hovering the directions card.
  - The "Office hours" list items gently highlight and slide horizontally on hover.
- **Refined Hero Badge**: Upgraded the hero status dot from a basic shadow to a clean, rhythmic radar-ping pulse.

### 🧠 Information Architecture
- **Reduced Cognitive Load**: Reorganized the overwhelming 9-item service grid into intuitive, scannable clusters: *The Essentials*, *Restorative Care*, *Cosmetic Care*, and *Urgent Care*.
- **Integrated Real Map**: Replaced the stylized CSS-only map grid with a live Google Maps iframe embed, applying CSS filters (grayscale, sepia, hue-rotate) to perfectly match the brand's sage and terracotta palette.

### 🛡️ Hardening & Accessibility (WCAG 2.1 AA)
- **Semantic HTML & ARIA**: Implemented strict semantic tags (`<section>`, `<header>`, `<aside>`, `<footer>`) with explicit `role` attributes and `aria-labelledby` linkages.
- **Keyboard Navigation**: Added a robust focus trap and `Escape`-key closure support for the mobile drawer. Improved the `:focus-visible` state with a high-contrast 2px Sage ring and offset.
- **Motion Sensitivity**: Strictly honors `prefers-reduced-motion: reduce` by disabling the Ambient Canvas, stopping CSS animations, and instantly resolving all scroll reveals.
- **Defensive CSS**: Added `overflow-wrap: break-word` and `-webkit-line-clamp` boundaries to cards to prevent layout breaks from long text or translation tools.
- **SEO & Resilience**: Added a canonical URL (`https://porthuronfamilydentists.com`), explicit image aspect ratios to prevent Cumulative Layout Shift (CLS), and `rel="noopener noreferrer"` on external links.

### 🧹 Code Quality
- **Distilled Source**: Stripped 300+ lines of unnecessary "Tweaks" UI JavaScript, HTML, and CSS that bloated the initial bundle.
- **Systematic Spacing**: Extracted hardcoded padding and margin values into a cohesive CSS variables scale (`--spacing-xs` through `--spacing-section`) to enforce pixel-perfect rhythm across all viewports.
- **Optimized Scroll Handlers**: Consolidated scroll-driven effects (navigation transitions, mobile bar, and parallax) into a single, high-performance `requestAnimationFrame` tick.
- **Zero Anti-Patterns**: Passed all automated detector tests with 0 findings.