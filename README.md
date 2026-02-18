# B2B Design Methodology
Purposeful Media Design System - Figma-to-Code Generation

A showcase of the design-to-code methodology behind [Purposeful Media Promotions](https://purposefulmediapromotions.com) — a B2B digital marketing agency built on systematic design system principles.

This repository demonstrates how a structured pipeline converts Figma design decisions into production-ready, responsive web components. It's intended as a reference for collaborators, developers, and anyone interested in systematic approaches to B2B web development.

---

## Methodology Overview

### Atomic Design Structure

Components follow [Brad Frost's Atomic Design](https://bradfrost.com/blog/post/atomic-web-design/) hierarchy:

**Atoms** → Base elements (buttons, inputs, typography, labels)
**Molecules** → Simple component groups (form fields, card elements)
**Organisms** → Complex assemblies (headers, heroes, footers, content sections)
**Templates** → Full page structures composed from organisms

### 3-Tier Development Pipeline

Every component moves through three stages from design to deployment:

| Tier | Purpose | Input | Output |
|------|---------|-------|--------|
| **1: Export** | Preserve design fidelity | Figma components via AutoHTML | Raw HTML/CSS files |
| **2: Demo** | Validate responsive behavior | Tier 1 exports + manual cleanup | Standalone demo HTML with implementation notes |
| **3: Production** | Centralize and tokenize | Validated Tier 2 code | Consolidated CSS variables, production-ready components |

This pipeline eliminates interpretation gaps between design and development. Each tier has a clear handoff point, making delegation straightforward and quality auditable.

---

## What's in This Repository

```
b2b-design-methodology/
├── demos/                    # Responsive component demos (from Tier 2)
│   ├── header-responsive/
│   ├── footer-responsive/
│   ├── hero-responsive/
│   └── hero-carousel-responsive/
├── tokens/                   # Design system CSS variables (from Tier 3)
│   └── variables.css
├── docs/                     # Pipeline and architecture documentation
│   └── pipeline-overview.md
└── screenshots/              # Figma-to-code visual comparisons
```

---

## Design Tokens

All visual decisions are centralized as CSS custom properties in a single `variables.css` file. This serves as the contract between design and code.

**Typography** — Font families (Lato headings, Open Sans body), sizes from 10px captions to 52px pullquotes, weights from 300 to 800, and line heights using a consistent 1.5× ratio for headings.

**Color System** — Three brand palettes (Navy, Gold, Teal) each defined as a full 50–900 scale with semantic aliases. Includes surface colors, text variants, and opacity tokens for gradients and overlays.

**Layout** — Four responsive breakpoints (Mobile 380px, Tablet 768px, Desktop 1150px, Desktop+ 1920px), spacing scale, border radii, and shadow definitions.

**Example:**
```css
:root {
  --color-primary-700: #1b1464;   /* Primary Navy */
  --color-accent-500: #d4af37;    /* Primary Gold */
  --color-secondary-500: #39cccc; /* Primary Teal */

  --font-family-heading: 'Lato', sans-serif;
  --font-family-body: 'Open Sans', sans-serif;

  --breakpoint-mobile: 380px;
  --breakpoint-tablet: 768px;
  --breakpoint-desktop: 1150px;
  --breakpoint-desktop-plus: 1920px;
}
```

---

## Responsive Demos

Each demo is a self-contained HTML file that renders a single organism across all four breakpoints. These validate that design system tokens produce the intended visual result at every screen size.

**Header** — Responsive navigation with mobile hamburger menu, sprite-based icons, and progressive disclosure across breakpoints.

**Hero** — Full-width hero section with headline, supporting text, and call-to-action. Typography and spacing scale fluidly between mobile and desktop.

**Hero Carousel** — Multi-slide variant with navigation controls and auto-advance behavior.

**Footer** — Multi-column layout that collapses gracefully to stacked mobile format with contact, navigation, and social links.

---

## Design System Source

The Figma design system (v3) is the single source of truth. Components are exported via AutoHTML plugin, then refined through the 3-tier pipeline. This ensures:

- Design intent is preserved through code generation
- Responsive behavior is validated before production integration
- Token values trace directly back to Figma definitions
- Any developer can audit design-to-code fidelity

---

## Tech Stack

- **Design:** Figma with AutoHTML export
- **Tokens:** CSS custom properties (no preprocessor dependency)
- **Fonts:** Google Fonts (Lato, Open Sans)
- **Icons:** Custom sprite sheets (UI and decorative)
- **Target Platform:** WordPress with ACF Pro
- **Methodology:** Atomic Design + 3-tier validation pipeline

---

## About

This repository is maintained by [Geoff Craig](https://www.upwork.com/freelancers/geoffreycraig), founder of Purposeful Media Promotions. The agency serves B2B companies with digital marketing resources for branding, design, and promotion.

The design system and methodology documented here are the foundation of the agency's web presence and serve as a working example of the systematic approach applied to client projects.

**Contact:** [purposefulmediapromotions.com](https://purposefulmediapromotions.com)
