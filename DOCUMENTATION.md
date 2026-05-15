# SAS Migration Promo Page — Documentation

## Overview

`promo.html` is a single-page marketing site for T1A's SAS Migration Suite, designed for integration into a Webflow site. It uses the Alchemist/T1A dark theme aesthetic (sourced from getalchemist.io and the DAIS 2026 trifold leaflet).

**File:** `webpage/promo.html`
**Previous version:** `webpage/index.html` (orange/navy/purple theme — content reference only)

---

## Design System

### Color Palette

| Token | Hex | Usage |
|---|---|---|
| `--neon` | `#00E676` | Primary accent — CTAs, headings, icons, logo |
| `--neon-dim` | `#00C853` | Hover state for neon elements |
| `--neon-glow` | `rgba(0,230,118,0.15)` | Background radials, subtle glows |
| `--dark` | `#0A0A14` | Page background |
| `--dark-card` | `#111122` | Card backgrounds |
| `--dark-mid` | `#161628` | Alternate section backgrounds |
| `--dark-light` | `#1E1E36` | Badges, tags, icon backgrounds |
| `--dark-border` | `rgba(255,255,255,0.07)` | Borders, dividers |
| `--dark-border-hover` | `rgba(255,255,255,0.14)` | Hover border state |
| `--text-bright` | `#FFFFFF` | Headings, primary text |
| `--text-primary` | `rgba(255,255,255,0.92)` | Body text |
| `--text-secondary` | `rgba(255,255,255,0.58)` | Descriptions, supporting copy |
| `--text-dim` | `rgba(255,255,255,0.35)` | Labels, captions, muted text |
| `--orange` | `#E85722` | Secondary accent (empowerment, migration badges) |
| `--purple` | `#7B3FAA` | Tertiary accent (case cards, video refs) |
| `--teal` | `#00C4A8` | Tertiary accent (empowerment, checkmarks) |

### Typography

- **Font:** Inter (Google Fonts), 400–900 weights
- **Fallbacks:** -apple-system, BlinkMacSystemFont, sans-serif
- **H1:** `clamp(40px, 5vw, 64px)`, weight 900, letter-spacing -2px
- **H2:** `clamp(28px, 3.5vw, 42px)`, weight 900, letter-spacing -1px
- **H3 (cards):** 16–18px, weight 700–800
- **Body:** 14–16px, weight 400, line-height 1.6–1.75
- **Labels:** 11px, weight 700, uppercase, letter-spacing 0.14em
- **Small text:** 12–13px for captions, tags, meta

### Logo

The Alchemist geometric "A" mark is used as an inline SVG in neon green (`#00E676`) with 25% opacity secondary paths. It appears in:
- Navigation (22px height)
- Footer (20px height)

SVG viewBox: `0 0 55 44`

### Spacing & Layout

- **Max container width:** 1200px
- **Container padding:** 0 32px (20px on mobile)
- **Section padding:** 100px vertical (72px on mobile)
- **Card border-radius:** 14px
- **Button border-radius:** 8px (6px for nav CTA)
- **Card gap:** 20px
- **Grid system:** CSS Grid, responsive breakpoints at 1024px and 768px

### Interactive States

- **Card hover:** translateY(-2px to -4px), border lightens, box-shadow appears
- **Button hover (primary):** background shifts to `--neon-dim`, translateY(-1px), green glow shadow
- **Button hover (secondary):** background lightens, border brightens
- **Links:** color transition 0.2s
- **All transitions:** 0.2–0.25s ease

---

## Page Structure

### Sections (top to bottom)

| # | Section | HTML ID | Background | Description |
|---|---|---|---|---|
| 1 | Navigation | — | `rgba(10,10,20,0.85)` + blur | Fixed top bar with logo, links, CTA |
| 2 | Hero | — | `--dark` + radial glows | H1 "SAS Migration Suite", subtitle, 2 CTAs, partner pills |
| 3 | Stats | — | `--dark-mid` | 4-column stat bar (50+, ~2M, 10K+, 100+) |
| 4 | Why T1A | `#why` | `--dark` | 2-col: heading + badge / 4 differentiator items |
| 5 | Why Migrate | `#benefits` | `--dark-mid` | 6 benefit cards in 3-col grid |
| 6 | Challenges | — | `--dark` | 4 challenge cards in 2-col grid |
| 7 | Journey | `#approach` | `--dark-mid` | 5 phase cards in 3-col grid |
| 8 | Tools | `#tools` | `--dark` | 2 categories (Assessment, Migration), 3 cards each with screenshot placeholders |
| 9 | Empowerment | `#empowerment` | `--dark-mid` | 3 pillar cards (Trainings, Self-Serve, Coexistence) |
| 10 | Cases | `#cases` | `--dark` | 3 case study cards + 3 public reference cards |
| 11 | CTA | `#contact` | `--dark-mid` + radial glow | Headline, subtitle, 2 CTAs |
| 12 | Partners | `#partners` | `--dark` | 3 partner type cards + CTA |
| 13 | Footer | — | `--dark` | Logo, copyright, links |

---

## CSS Class Reference

### Layout
- `.section` — standard section padding (100px/72px responsive)
- `.container` — max-width 1200px centered wrapper

### Navigation
- `.nav` — fixed top bar with backdrop blur
- `.nav-inner` — flex row container
- `.nav-brand` — logo + divider + product name
- `.nav-logo` — wraps the Alchemist SVG mark
- `.nav-divider` — 1px vertical separator
- `.nav-product` — "SAS Migration" text label
- `.nav-links` — horizontal link list
- `.nav-cta` — green primary button

### Hero
- `.hero` — section with radial glow pseudo-elements
- `.hero-content` — centered text block
- `.hero h1 .accent` — neon green text span
- `.hero-sub` — subtitle paragraph
- `.hero-actions` — button row

### Stats
- `.stats` — section wrapper
- `.stats-grid` — 4-col / 2-col responsive grid
- `.stat-item` — individual stat cell
- `.stat-number` — large number
- `.stat-number .highlight` — neon-colored suffix ("+", "M", etc.)
- `.stat-desc` — description text

### Content Sections
- `.section-label` — green uppercase label with dash prefix
- `.benefits-grid` / `.challenges-grid` / `.phases-grid` / `.empower-grid` / `.cases-grid` / `.partners-grid` — responsive grids
- `.benefit-card` / `.challenge-card` / `.phase-card` / `.empower-card` / `.case-card` / `.partner-card` — dark cards with hover

### Tools
- `.tool-category` — wraps a category label + tool grid
- `.tool-category-label` — pill badge (`.tc-assess` green, `.tc-migrate` orange)
- `.tools-list` — 3-col grid of tool cards
- `.tool-card` — individual tool card
- `.tool-screenshot` — 16:9 screenshot container (replace placeholder with `<img>`)
- `.tool-screenshot-placeholder` — temporary "Screenshot" text label
- `.tool-desc` — tool description
- `.tool-features` — checkmark feature list
- `.tool-link` — green external link

### Empowerment Cards
- `.ec-green` / `.ec-orange` / `.ec-teal` — top border color variants
- `.eci-green` / `.eci-orange` / `.eci-teal` — icon background variants
- `.tag-soon` — "Coming Soon" inline badge

### Case Studies
- `.cc-neon` / `.cc-purple` / `.cc-card` — card background variants
- `.case-chip` — duration badge pill

### References
- `.refs-section` — sub-section within cases
- `.ref-card` — clickable reference card
- `.ref-preview` / `.ref-preview-blog` — top image/preview area
- `.ref-play-overlay` / `.ref-play-btn` — video play button overlay
- `.ref-body` — text content area
- `.ref-type-article` / `.ref-type-video` — type label color variants

### CTA
- `.cta` — dark section with radial glow
- `.cta-content` — centered text block
- `.cta h2 .accent` — neon green text

### Buttons
- `.btn` — base button styles
- `.btn-primary` — green solid button
- `.btn-secondary` — transparent with border

### Footer
- `.footer` — dark bar with top border
- `.footer-inner` — flex row (stacks on mobile)
- `.footer-logo` — wraps the Alchemist SVG mark
- `.footer-copy` — copyright text
- `.footer-links` — right-aligned link row

---

## Webflow Integration Guide

### Approach

The page is designed as a reference prototype. To integrate into Webflow:

1. **Create sections** in Webflow matching the 13 sections above. Each maps to a Webflow Section element.
2. **Use Container** elements for `.container` wrappers (set max-width to 1200px).
3. **Use Grid** elements for all `-grid` classes. Webflow's visual grid editor supports the column counts and gaps defined here.
4. **Copy CSS custom properties** into Webflow's custom code area (Project Settings > Custom Code > Head) inside a `<style>` tag with the `:root` block.
5. **Recreate cards** as Webflow Div Blocks with the matching class names and styles.

### Fonts

Add Inter via Webflow's Google Fonts integration (Project Settings > Fonts). Weights needed: 400, 500, 600, 700, 800, 900.

### Images / Screenshots

Each tool card has a `.tool-screenshot` div with a placeholder. In Webflow:
- Add an Image element inside the div
- Set object-fit: cover
- Upload the actual screenshots

Screenshot source files from the original page:
- `resources/screenshots/alchemist_analyzer/screenshot_1.png`, `screenshot_2.png`
- `resources/screenshots/logs_analyzer/screenshot_1.png`, `screenshot_2.png`
- `resources/screenshots/metascope/screenshot_1.png`, `screenshot_2.png`
- `resources/screenshots/alchemist_converter/screenshot_1.png`
- `resources/screenshots/change_management_platform/screenshot_1.png`, `screenshot_2.png`

### SVGs

Partner logos (Databricks, Microsoft, Snowflake) and the Alchemist mark are inline SVGs. In Webflow:
- Use Embed elements to paste the SVG code, or
- Upload as SVG assets and use Image elements

### Interactions

The only JavaScript is smooth scroll for anchor links — Webflow handles this natively with Link Blocks pointed to Section IDs.

Hover animations (card lift, border change, shadow) should be recreated using Webflow's hover states on each card class.

The backdrop-filter blur on `.nav` may need a custom CSS override in Webflow:
```css
.nav {
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
}
```

### Responsive Breakpoints

| Breakpoint | Behavior |
|---|---|
| > 1024px | Full layout: 3-col grids, 4-col stats, 2-col why |
| 768–1024px | 2-col grids, 2-col stats, stacked why, nav links hidden |
| < 768px | 1-col everything, reduced padding, stacked footer |

Map these to Webflow's Tablet and Mobile breakpoints.

### Custom Code

Add to Project Settings > Custom Code > Head:
```html
<style>
:root {
  --neon: #00E676;
  --neon-dim: #00C853;
  --neon-glow: rgba(0, 230, 118, 0.15);
  --dark: #0A0A14;
  --dark-card: #111122;
  --dark-mid: #161628;
  --dark-light: #1E1E36;
  --dark-border: rgba(255, 255, 255, 0.07);
  --dark-border-hover: rgba(255, 255, 255, 0.14);
  --text-bright: #FFFFFF;
  --text-primary: rgba(255, 255, 255, 0.92);
  --text-secondary: rgba(255, 255, 255, 0.58);
  --text-dim: rgba(255, 255, 255, 0.35);
  --orange: #E85722;
  --purple: #7B3FAA;
  --teal: #00C4A8;
}
</style>
```

---

## Files

| File | Purpose |
|---|---|
| `promo.html` | Current promo page (dark Alchemist theme) |
| `index.html` | Previous version (orange/navy theme) — content reference |
| `resources/screenshots/` | Tool screenshots from previous version |
| `DOCUMENTATION.md` | This file |

## Design Sources

| Source | What was used |
|---|---|
| `webpage/index.html` | All text content, section structure, feature lists |
| `getalchemist.io` | Dark theme aesthetic, card patterns, layout style |
| `sas_migration_trifold_v5.html` | Color palette (#00E676 neon, dark backgrounds), Alchemist logo SVG, "Why Migrate" and "Challenges" content |
