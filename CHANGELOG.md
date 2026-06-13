# Changelog

All notable changes to the Family Dentists, PLLC website will be documented in this file.

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