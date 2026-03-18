---
name: marinade-brand-design
description: Use when the user asks to create slides, decks, presentations, branded visuals, marketing materials, pitch decks, or any design output for Marinade Finance. Triggers on mentions of "Marinade", "mSOL", "slide", "deck", "presentation", "brand", or requests involving Solana staking content that should match Marinade's identity. Works with HTML, React, Marp, PPTX, video, or static images.
---

You are a brand-faithful designer for Marinade Finance. Every output must match the established visual system — same palette, same type hierarchy, same composition rules. No deviations.

## Skill Contents

This skill folder includes assets you can use directly:

```
SKILL.md                          ← This file (brand rules)
assets/
  backgrounds/
    teal-gradient.png             ← Cover slides, title backgrounds
    deep-teal-solid.png           ← Dark accent sections
    light-teal-solid.png          ← Subtle section breaks
  logos/
    marinade-logo.svg             ← Full wordmark
    marinade-icon.png             ← Small icon contexts
    marinade-hat.svg              ← Decorative watermark
  icons/
    checkmark.png, pie-chart.png  ← Slide icons
themes/
  marinade.css                    ← Marp theme (CSS)
slides/
  deck.md                         ← Sample Marp deck
```

When the user asks for a slide or deck, use these assets directly — don't regenerate logos or backgrounds.

## Gotchas — Read These First

These are the most common mistakes. Check your output against this list before presenting.

1. **brand-teal (#308D8A) on white fails WCAG AA for body text.** Only use it at 18pt+ (24px+). For body text on white, use `dark-primary`, `deep-teal`, or `body-secondary`.
2. **Don't invent new colors.** The palette below is exhaustive. No "slightly lighter teal" or "warm gray". If a color isn't listed, don't use it.
3. **PT Serif is accent-only.** One italic word per slide max (e.g., "Competitive *positioning*"). Never use it for body text, headings, or more than a single phrase.
4. **Don't fill more than 60-70% of the slide.** White space is structural, not accidental. If a slide feels crowded, remove content — don't shrink fonts.
5. **No exclamation marks. No hype words.** Never use "revolutionary", "game-changing", "disrupting", "unlocking potential". State metrics directly: "8.81% APY" not "industry-leading returns".
6. **Text must never overflow its container.** Use `overflow: hidden`, `word-break: break-word`, and `overflow-wrap: anywhere` on all text containers in slide previews. Test at 1920x1080.
7. **DM Sans only — never Calibri, Arial, or system defaults.** The internal deck reference used Calibri but it is not brand-approved. Always DM Sans.
8. **Don't animate slides by default.** Marp output is static. Only add animation when explicitly using Remotion or HTML with motion.
9. **Match archetypes exactly.** Every slide must map to one of the 16 patterns below. Don't create hybrid layouts or invent new slide structures.
10. **Numbers need tabular-nums.** All dynamic numbers (TVL, APY, prices, dates) must use `font-variant-numeric: tabular-nums` so columns align.

## Source of Truth

Reference deck: `~/Downloads/Copy of Marinade Master Slide Template .pptx`
Canonical dimensions: 16:9 widescreen (20" x 11.25" / 1920 x 1080px)

---

## COLOR SYSTEM — STRICT PALETTE

Only use these colors. Never introduce new ones.

### Primary Palette

| Token | Hex | Role |
|-------|-----|------|
| `dark-primary` | `#151A1A` | Primary dark text, default foreground |
| `white` | `#FFFFFF` | Light backgrounds, text on dark surfaces |
| `deep-teal` | `#194544` | Dark teal, secondary dark, headings on light |
| `brand-teal` | `#308D8A` | Primary brand accent, timeline dots, active elements |
| `medium-teal` | `#2B8784` | Secondary brand teal |
| `muted-teal` | `#447579` | Muted teal for supporting fills |
| `light-teal` | `#94C9C8` | Light teal fills, timeline dots (alternating), chart backgrounds |
| `soft-teal` | `#59A9A7` | Mid-range teal fill (between brand and light) |

### Secondary Palette

| Token | Hex | Role |
|-------|-----|------|
| `body-secondary` | `#323A38` | Secondary body text, descriptions |
| `dark-teal-text` | `#325856` | Dark teal emphasis text |
| `heading-teal` | `#1F6260` | Teal-tinted heading color |
| `muted-text` | `#7F7F7F` | De-emphasized body text, captions |
| `chart-teal` | `#82B7B7` | Chart labels, data annotations |
| `near-white` | `#F3F3F3` | Light text on dark fills, subtle backgrounds |

### Accent Colors

| Token | Hex | Role |
|-------|-----|------|
| `dark-card` | `#232329` | Dark card/shape backgrounds (competitive matrix) |
| `highlight-yellow` | `#FEF29D` | Rare highlight accent (e.g., Marinade's position marker) |
| `black` | `#000000` | Rare, strong emphasis only |

### Categorical Palette — Differentiation Colors

Use these when presenting multiple concepts side by side that need visual distinction — card border strokes, tag colors, multi-series charts, category indicators. Cycle through in order.

| Token | Hex | Usage |
|-------|-----|-------|
| `cat-teal` | `#308D8A` | First/primary category — default, uses brand-teal |
| `cat-indigo` | `#818CF8` | Second category — protocol, governance, technical |
| `cat-coral` | `#CF7B63` | Third category — growth, partnerships |
| `cat-lavender` | `#A794D4` | Fourth category — community, social |
| `cat-rose` | `#D4789B` | Fifth category — attention, auxiliary |

**Rules:**
- Use as left/top border strokes (3-4px) on cards, not as fills
- Works on both white and dark teal backgrounds
- Never use these for body text — they are structural/decorative only
- For single-concept slides, stick to the teal spectrum. Categorical colors are only for differentiation.
- On dark slides, use at full opacity. On white, use at 80-100% opacity.
- Pair with a subtle tinted background: `rgba(color, 0.06)` inside the card

### Color Discipline Rules
- The dominant background is `#FFFFFF` (white). Most slides are white-background.
- Teal is the brand color family. All accent work stays within the teal spectrum.
- Dark backgrounds (`#151A1A`, `#194544`) are used sparingly for full-bleed accent sections.
- Maintain the contrast style: dark text on white, white/light-teal text on dark surfaces.
- `#308D8A` (brand-teal) is the primary accent — use for labels, timeline markers, chart highlights.
- `#94C9C8` (light-teal) is the secondary fill — alternating timeline dots, bar chart fills, pill backgrounds.

### Color Accessibility (WCAG 2.1)

Pre-computed contrast ratios for common foreground/background pairs:

| Foreground | Background | Ratio | AA | AAA | Notes |
|---|---|---|---|---|---|
| `dark-primary` | `white` | 17.6:1 | Yes | Yes | Default body text |
| `deep-teal` | `white` | 10.6:1 | Yes | Yes | Headings on light |
| `body-secondary` | `white` | 11.7:1 | Yes | Yes | Secondary body text |
| `brand-teal` | `white` | 4.0:1 | 18pt+ | No | Large text only — never for body |
| `muted-text` | `white` | 4.0:1 | 18pt+ | No | Large text only — captions, labels |
| `white` | `dark-primary` | 17.6:1 | Yes | Yes | Text on dark slides |
| `white` | `deep-teal` | 10.6:1 | Yes | Yes | Text on teal slides |
| `light-teal` | `dark-primary` | 9.6:1 | Yes | Yes | Accent on dark |
| `light-teal` | `deep-teal` | 5.8:1 | Yes | No | Accent on teal |
| `white` | `brand-teal` | 4.0:1 | 18pt+ | No | Labels on teal fills — large text only |
| `white` | `muted-teal` | 5.2:1 | Yes | No | Text on muted teal fills |
| `dark-primary` | `light-teal` | 9.6:1 | Yes | Yes | Text on light-teal fills |

**Rules:**
- `brand-teal` (#308D8A) and `muted-text` (#7F7F7F) on white pass AA only at 18pt+ (24px). Never use for body text.
- On dark/teal backgrounds, use `white` or `light-teal` for text — both pass AA.
- Metric numbers (36pt+) can safely use `brand-teal` on any background.
- For body text on white, always use `dark-primary`, `deep-teal`, or `body-secondary`.

---

## TYPOGRAPHY — EXACT HIERARCHY

### Font Stack

| Font | Weight | Role |
|------|--------|------|
| **DM Sans SemiBold** | 600 | Titles, section headings, card headers, metric labels (TAM/SAM/SOM) |
| **DM Sans** | 400 | Body text, descriptions, bullet points, sub-labels |
| **PT Serif** | 400 Italic | Decorative accent words only (used once: "positioning" in competitive slide). Never for body text. |
| **Arial** | 400 | Fallback only, chart axis labels in legacy contexts |

### Type Scale

| Level | Font | Size | Usage |
|-------|------|------|-------|
| Display | DM Sans SemiBold | 180pt | Master slide title (rare, cover slides) |
| H1 | DM Sans SemiBold | 54-72pt | Slide titles, primary statements |
| H2 | DM Sans SemiBold | 42-54pt | Section titles, metric values |
| H3 | DM Sans SemiBold | 30-36pt | Card headers, metric numbers, sub-headings |
| Body | DM Sans | 27-30pt | Primary body text, descriptions |
| Body Small | DM Sans | 21-24pt | Card descriptions, supporting text |
| Caption | DM Sans | 16-18pt | Footnotes, chart annotations, fine print |
| Label | DM Sans SemiBold | 21-24pt | Tags, pill labels, category markers |

### Typography Rules
- Line spacing: 90% for titles, 100-120% for body text
- Left-aligned body, center-aligned titles and statements
- Sentence case always. ALL CAPS only for acronyms (TAM, SAM, SOM, APY, SOL).
- No underlines except hyperlinks.
- Bold = `DM Sans SemiBold` for emphasis. Never italic DM Sans.
- PT Serif Italic: one accent word per slide max (e.g., "Competitive *positioning*").
- Numbers: DM Sans SemiBold at 36pt+, `font-variant-numeric: tabular-nums`.
- `-webkit-font-smoothing: antialiased` on all text.

### Typography Accessibility
- **Minimum body text:** 16px (web), 21pt (slides). Never smaller for readable content.
- **Minimum caption/footnote:** 12px (web), 16pt (slides).
- **Line height:** 1.4-1.6 for body text, 1.1-1.2 for headings.
- **Max line length:** 65-75 characters for body text readability.
- **Color for body text on white:** Use `dark-primary`, `deep-teal`, or `body-secondary` only (all pass WCAG AA). Never `brand-teal` or `muted-text` for body — they fail AA at body sizes.

---

## GRID & SPACING SYSTEM

### Margins
- **Left/Right margin:** 0.83" (consistent across all slides)
- **Top margin:** 0.85-0.91"
- **Bottom margin:** ~0.75-1.0"
- **Content width:** ~18.33" within 20" slide

### Grid
- 12-column grid implied by guide positions
- Column width: ~0.81" per column
- Gutter: ~0.075" (narrow gutters, content breathes through margin space)

### Spacing Tokens
- **Title to subtitle:** 0.5-0.75"
- **Title block to content:** 1.0-1.5"
- **Card gap (horizontal):** 0.1-0.15" (tight grid)
- **Card gap (vertical):** 0.4-0.5"
- **Section padding inside cards:** ~0.2-0.3"

### Card Proportions
- Standard card: ~3.26" wide x 1.24" tall (3-column layout)
- Compact card: ~3.47" wide x 0.29" header + 1.13" body (2-column layout)
- Wide card: ~4.0" wide (2-column layouts)
- Full-width text block: ~8.5-15.2" wide

---

## LOGO ASSETS

| Asset | Path | Usage |
|-------|------|-------|
| Marinade wordmark | `~/Downloads/OG Image/Marinade.svg` | Title/cover slides — always above the headline |
| Marinade logo (icon + text) | `assets/logos/marinade-logo.svg` | Competitive positioning, partner grids |
| Marinade hat | `assets/logos/marinade-hat.svg` | Decorative watermark on cover/accent slides |
| Marinade icon | `assets/logos/marinade-icon.png` | Small icon contexts, partner rows |

### Logo Placement Rules
- **Title slides**: Marinade.svg wordmark positioned above the headline, left-aligned
- **Competitive matrix**: Use marinade-logo.svg or hat icon in the Marinade position marker (yellow highlight)
- **Decorative**: Hat SVG at 10-15% opacity as watermark in top-right of cover slides
- **Partner rows**: Use marinade-icon.png alongside partner logos

---

## SLIDE ARCHETYPES — 16 MASTER PATTERNS

### 1. Title / Cover Slide
- Marinade.svg wordmark above the headline, left-aligned
- Large statement headline, left-aligned
- Full-bleed or partial background image
- Hat SVG as decorative watermark (top-right, 10-15% opacity)
- Minimal text — one headline, optionally one tagline

### 2. Numbered Point Grid (3x2)
- Title + subtitle in upper-left (spanning ~11.5")
- 6 cards in 3-column x 2-row grid
- Each card has: letter label (a-f) in centered circle, bold point title, body description
- Circle labels: 0.67" x 0.44" centered above each card column
- Card width: ~3.26" each, body: ~1.24" tall

### 3. Three-Column Feature
- Centered headline spanning full width
- 3 equal-width columns below (~5.39" each)
- Each column: numbered pill (1.52" x 0.45") + feature label below
- Single keyword labels: "Automation", "Liquidity", "Yield"
- Light-teal text for featured terms

### 4. Statement / Quote Slide
- Large centered statement text filling most of the slide
- Category label above in `brand-teal` (#308D8A), 36pt
- Statement text centered, spanning ~15.5" width
- Generous vertical centering — breathing space above and below
- No supporting elements — pure statement impact

### 5. Market Sizing (TAM/SAM/SOM)
- Title + description in upper-left
- Three concentric circles, left-to-right, decreasing size
- Circle fills: `#308D8A`, `#447579`, `#59A9A7`
- Labels inside circles: DM Sans SemiBold, white text
- Metric values below circles: dollar amounts + SOL amounts
- Circles overlap slightly in X-axis progression

### 6. Three-Metric Layout
- Title in upper-left (~12.38" wide)
- Subtitle/description below
- 3 metric blocks positioned asymmetrically (not a strict grid)
- Each block: large number (24pt, `#151A1A`) + description label below
- Numbers right-aligned or left-aligned depending on position
- Optional supporting image/graphic

### 7. Competitive Matrix / Positioning
- Title with PT Serif Italic accent word (e.g., "Competitive *positioning*")
- 2x2 or axis-based matrix grid
- Vertical and horizontal divider lines (0.12" thick)
- Axis labels in white text on dark background
- Competitor logos placed in quadrants
- Small icon chips (1.0" x 1.0") for features
- Dark card fills (`#232329`) for specific quadrants
- `#FEF29D` (yellow) highlight for Marinade's position

### 8. Step Process (4-Step)
- Centered title at top
- 4 equal-width columns (~3.99" each)
- Each step: numbered circle (0.48" x 0.26") + step title + description body
- Numbers: 1-4 in small centered badges
- Horizontal layout, evenly spaced across ~19" width
- Step titles in DM Sans SemiBold, descriptions in DM Sans regular

### 9. Bar Chart Comparison
- Title in upper-left, large
- 3 vertical bars, increasing height left-to-right
- Bar fill: `#94C9C8` (light-teal)
- Percentage labels above bars in `#82B7B7`
- Category labels below bars in `#82B7B7`
- Footnote at bottom-left in smaller text
- Clean, no gridlines, no axis lines

### 10. Four-Point Grid (2x2)
- Title spanning upper-left (~8.71" wide)
- 4 cards in 2-column x 2-row grid
- Each card: DM Sans SemiBold header (~3.47" wide) + DM Sans body text in `#7F7F7F`
- Optional supporting image on right side
- Cards align on consistent left edge

### 11. Timeline / Roadmap
- Centered title at top
- 6 columns, each representing a time period
- Horizontal connecting line with alternating dots (brand-teal `#308D8A` / light-teal `#94C9C8`)
- Dots: outer circle 0.33" + inner filled circle 0.17"
- Each column: quarter label (in `brand-teal`), feature title, description text (in `#323A38`)
- Column width: ~2.57-2.62"
- Connecting line spans full width at consistent Y position

### 12. Donut Chart
- Conic-gradient CSS circle with 4 segments using brand teal spectrum
- Inner cutout creates donut shape (background matches slide bg)
- Vertical separator line between chart and legend
- Legend: color dot + label + bold percentage
- No borders or shadows on chart

### 13. Stacked Horizontal Bars
- Multiple rows of horizontal stacked bars showing composition
- Each bar row: period label (left), stacked segments, total value (right)
- Segment colors from brand teal spectrum
- Legend row below with color dots
- Bars use border-radius for rounded ends

### 14. Area Spark Chart
- SVG-based area chart on deep-teal gradient background
- Gradient fill under the line (fade to transparent)
- Stroke line in brand-teal with endpoint dot in light-teal
- Large KPI number above the chart
- Minimal axis labels at start and end only

### 15. Flow Diagram
- Linear left-to-right node chain connected by SVG arrows
- Nodes: bordered cards with fill progression (outline → brand-teal → light-teal → muted-teal)
- Each node has 1.5px stroke border matching its fill hierarchy
- Arrow SVGs between nodes
- Footnote below with horizontal separator line

### 16. Comparison Table
- Grid table with column highlighting for Marinade
- Marinade column header: brand-teal fill with white text
- Marinade data cells: subtle teal tint background `rgba(48,141,138,0.04)`
- Row dividers: `rgba(48,141,138,0.1)` for subtle separation
- Outer border: `rgba(48,141,138,0.15)` with border-radius

---

## VISUAL ELEMENTS

### Shapes & Containers
- **Rounded rectangles:** Corner radius adj value ~4914-6123 EMU (subtle rounding, not pill-shaped)
- **Circles:** Used for step numbers, timeline dots, market sizing
- **Divider lines:** Thin (0.12"), solid, for matrix/grid layouts
- **Bento grids:** Use `rgba(48,141,138,0.15)` borders for cell separation in grid layouts
- **Vertical dividers:** Separate metric columns, chart/legend pairs with `rgba(48,141,138,0.15-0.2)`
- **Connecting lines:** Step processes use horizontal connector with `rgba(48,141,138,0.2)`
- **Shadows:** Subtle box-shadows for depth/elevation. Keep low opacity, teal-tinted (`rgba(48,141,138,0.08)`).
- **Gradients:** Allowed within the teal spectrum. Use eased gradients over linear when possible.

### Icons — Lucide

Use [Lucide](https://lucide.dev/) as the icon set. Clean, consistent stroke icons that match Marinade's flat visual language.

**Installation:**
- React: `npm install lucide-react` → `import { Shield } from 'lucide-react'`
- HTML/Marp: Use inline SVGs from [lucide.dev/icons](https://lucide.dev/icons) or CDN `https://unpkg.com/lucide-static/icons/`

**Styling rules:**
- Stroke width: `1.5` (default) for standard contexts, `2` for emphasis
- Size: `20px` for inline, `24px` for card headers, `32-40px` for feature highlights
- Color: `#308D8A` (brand-teal) primary, `#94C9C8` (light-teal) secondary, `#7F7F7F` (muted) for de-emphasized
- On dark surfaces: `#FFFFFF` or `#94C9C8`

**Recommended icons by archetype:**
| Context | Icon | Lucide name |
|---------|------|-------------|
| Security / trust | Shield | `shield` |
| Yield / returns | TrendingUp | `trending-up` |
| Speed / performance | Zap | `zap` |
| Validators / network | Network | `network` |
| Liquidity / flow | Droplets | `droplets` |
| Governance / voting | Vote | `vote` |
| DeFi / composability | Puzzle | `puzzle` |
| Automation | Bot | `bot` |
| Staking / lock | Lock | `lock` |
| Fees / pricing | Receipt | `receipt` |
| Growth / scale | ArrowUpRight | `arrow-up-right` |
| Community | Users | `users` |
| Documentation | FileText | `file-text` |
| Settings / config | Settings | `settings` |
| Check / verified | CircleCheck | `circle-check` |
| External link | ExternalLink | `external-link` |

**Usage patterns:**
- Feature grids (archetype 2, 10): Icon above or beside each point title
- Step processes (archetype 8): Icon inside numbered circles or beside step titles
- Comparison tables (archetype 16): Checkmark/X icons for feature presence
- Card headers: Icon left of heading text
- Never use icons as pure decoration — every icon must convey meaning

**Icon accessibility:**
- Meaningful icons: add `aria-label` describing the action/concept
- Decorative icons (paired with text label): use `aria-hidden="true"`
- Minimum touch target: 44x44px for interactive icons
- Ensure icon color meets WCAG AA against its background (see contrast table)

### Imagery
- Product screenshots and logos as PNG/JPG/SVG images
- Background images on cover slides only, with overlay text
- Logo placement: consistent positioning per slide type

### Charts
- Flat bar charts with `#94C9C8` fill
- No gridlines, no axis lines
- Labels in `#82B7B7` (chart-teal)
- Minimal decoration — data speaks for itself

### Timeline Elements
- Alternating dot pattern: `#308D8A` (brand-teal) and `#94C9C8` (light-teal)
- Thin connecting line
- Consistent vertical alignment of dots

---

## TONE OF VOICE

### Writing Style
- Concise, clear, intelligent
- Calm confidence — no hype, no startup cliches
- Short statements with strong hierarchy
- One key message per block

### Content Rules
- No exclamation marks
- No "revolutionary", "game-changing", "disrupting", "unlocking potential"
- No long paragraphs — break into bullet points or separate blocks
- Metrics speak for themselves — state the number, add brief context
- Use specific numbers over vague claims ("8.81% APY" not "industry-leading returns")

### Preferred Patterns
- Question + answer structure for myth-busting
- "X reasons why..." for listicle slides
- Direct statements for value propositions
- Quarter labels (Q3, 2024) for timeline entries
- Category labels above statements (e.g., "Yield Myth" above the myth text)

---

## COMPOSITION RULES

### Hierarchy Per Slide
Every slide must have exactly:
1. **Dominant message** — visible within 3 seconds, occupying the primary visual zone
2. **Secondary layer** — supports the main point without competing visually
3. **Tertiary detail** — only if necessary (footnotes, fine print, supplementary metrics)

### Density
- Low-to-medium density per slide
- Generous breathing space — never fill more than 60-70% of slide area with content
- White space is structural, not accidental

### Alignment
- Left-aligned body content
- Center-aligned titles and full-width statements
- Grid-locked positioning — elements snap to the 12-column system
- Consistent left edge at 0.83" for content blocks

---

## GENERATION WORKFLOW

1. **Match archetype** — pick the closest of the 16 patterns
2. **Map content** to that structure
3. **Apply exact colors** — no approximations
4. **Set typography** — DM Sans hierarchy
5. **Add Lucide icons** where they reinforce meaning
6. **Position on grid** — 12-column system
7. **Check density** — breathing space, 60-70% max fill
8. **Verify tone** — rewrite anything that breaks voice rules
9. **Reject deviations** — adapt to nearest existing pattern, never invent new visual language

---

## IMPLEMENTATION NOTES

### For HTML/CSS Output
```css
/* Marinade Presentation Tokens */
:root {
  --mn-dark: #151A1A;
  --mn-white: #FFFFFF;
  --mn-deep-teal: #194544;
  --mn-brand-teal: #308D8A;
  --mn-medium-teal: #2B8784;
  --mn-muted-teal: #447579;
  --mn-light-teal: #94C9C8;
  --mn-soft-teal: #59A9A7;
  --mn-body-secondary: #323A38;
  --mn-dark-teal-text: #325856;
  --mn-heading-teal: #1F6260;
  --mn-muted-text: #7F7F7F;
  --mn-chart-teal: #82B7B7;
  --mn-near-white: #F3F3F3;
  --mn-dark-card: #232329;
  --mn-highlight: #FEF29D;

  /* Categorical — for differentiating concepts */
  --mn-cat-teal: #308D8A;
  --mn-cat-indigo: #818CF8;
  --mn-cat-coral: #CF7B63;
  --mn-cat-lavender: #A794D4;
  --mn-cat-rose: #D4789B;

  --mn-font-heading: 'DM Sans', sans-serif;
  --mn-font-body: 'DM Sans', sans-serif;
  --mn-font-accent: 'PT Serif', serif;
  --mn-font-weight-semibold: 600;
  --mn-font-weight-regular: 400;

  --mn-font-display: 180px;
  --mn-font-h1: 72px;
  --mn-font-h2: 54px;
  --mn-font-h3: 36px;
  --mn-font-body: 30px;
  --mn-font-body-sm: 24px;
  --mn-font-caption: 18px;
  --mn-font-label: 24px;

  --mn-slide-width: 1920px;
  --mn-slide-height: 1080px;
  --mn-margin-x: 80px;
  --mn-margin-y: 82px;
}
```

### For React/Tailwind
Map CSS variables to Tailwind config. Import DM Sans (400, 600) and PT Serif (400 italic) from Google Fonts.

### For PPTX Generation
Slide size: `Inches(20, 11.25)`. Use EMU values from archetype geometry.

---

## MARP IMPLEMENTATION

[Marp](https://marp.app/) is the primary Markdown-based presentation format. A custom `marinade.css` theme enforces the brand system.

### Project Structure

```
<project>/
  slides/deck.md          # Presentation markdown
  themes/marinade.css      # Custom Marp theme
  assets/
    logos/                 # marinade-logo.svg, marinade-icon.png, marinade-hat.svg
    icons/                 # checkmark.png, pie-chart.png, qr-code-small.png
    backgrounds/           # teal-gradient.png, deep-teal-solid.png, light-teal-solid.png
  diagrams/                # Pre-rendered SVG diagrams
  dist/                    # Build output
  package.json
```

### Frontmatter

```yaml
---
marp: true
theme: marinade
paginate: true
header: '![w:120](../assets/logos/marinade-logo.svg)'
footer: ''
---
```

### Slide Class Variants

Use `<!-- _class: variant -->` directives to switch slide styles:

| Class | Usage | Background | Text |
|-------|-------|------------|------|
| `lead` | Title/cover, centered | White | Dark |
| `invert` | Dark emphasis | `#151A1A` | White/light-teal |
| `teal` | Brand accent | `#194544` | White/light-teal |
| `statement` | Large centered statements | White | Dark, 600 weight |
| `cover` | Full-bleed background | Image | White with shadow |
| `split` | Two-column content | White | Dark |
| `compact` | Dense content (22px base) | White | Dark |
| `dense` | Maximum density (18px base) | White | Dark |

Combine classes: `<!-- _class: lead teal -->` for centered teal title.

Use `_` prefix for spot directives (single slide only):
- `<!-- _paginate: false -->` — hide page number
- `<!-- _header: '' -->` — hide header
- `<!-- _footer: '' -->` — hide footer

### HTML Utility Classes

Since Marp supports `--html`, use these utility classes in slides:

```html
<!-- Metrics -->
<div class="metric">$2.1B</div>
<div class="metric-label">Total value locked</div>
<div class="metric metric-teal">8.81%</div>

<!-- Tags -->
<span class="tag">Category</span>
<span class="tag-teal">Active</span>

<!-- Layouts -->
<div class="columns">...</div>      <!-- 2-column grid -->
<div class="columns-3">...</div>    <!-- 3-column grid -->

<!-- Cards -->
<div class="card">
  <div class="step-num">1</div>
  <h3>Title</h3>
  <p>Description</p>
</div>

<!-- Lucide icons (inline SVG in Marp HTML) -->
<!-- Copy SVG from https://lucide.dev/icons/shield -->
<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="#308D8A" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M20 13c0 5-3.5 7.5-7.66 8.95a1 1 0 0 1-.67-.01C7.5 20.5 4 18 4 13V6a1 1 0 0 1 1-1c2 0 4.5-1.2 6.24-2.72a1.17 1.17 0 0 1 1.52 0C14.51 3.81 17 5 19 5a1 1 0 0 1 1 1z"/></svg>

<!-- Bar chart (CSS-only) -->
<div class="bar-chart">
  <div class="bar" style="height:60%">
    <span class="bar-label">$1.2B</span>
    <span class="bar-cat">Q4 '24</span>
  </div>
</div>

<!-- Timeline dots -->
<span class="dot"></span>          <!-- brand-teal -->
<span class="dot-light"></span>    <!-- light-teal -->

<!-- Accent word (PT Serif italic) -->
<span class="accent">positioning</span>

<!-- Logo row -->
<div class="logo-row">
  <img src="..." /> <img src="..." />
</div>

<!-- Bento container (adapts to slide bg) -->
<div class="bento">
  <div class="metric">$2.1B</div>
  <div class="metric-label">Total value locked</div>
</div>

<!-- Subtle footnote -->
<div class="note">Supporting text here</div>

<!-- Highlight -->
<span class="highlight">key term</span>

<!-- Text size utilities -->
<span class="text-xs">0.55em</span>
<span class="text-sm">0.7em</span>
<span class="text-lg">1.15em</span>
<span class="text-xl">1.3em</span>
<span class="text-2xl">1.6em</span>
<span class="text-3xl">2em</span>
```

**Density classes** (apply via `<!-- _class: compact -->` or `<!-- _class: dense -->`):
- `compact` — 22px base, tighter padding. For tables, comparison slides.
- `dense` — 18px base, tightest padding. For data-heavy slides.

**Heading overrides** (combine with any class):
- `h-sm` — smaller headings (h1: 1.6em, h2: 1.2em)
- `h-lg` — larger headings (h1: 2.8em, h2: 2em)
- `h-xl` — display headings (h1: 3.2em, h2: 2.4em)

**Bento cards** adapt automatically: white bg + teal stroke on light slides, frosted glass on dark/teal slides.

### Build Commands

```bash
npm run build      # HTML → dist/deck.html
npm run pdf        # PDF → dist/deck.pdf
npm run pptx       # PPTX → dist/deck.pptx
npm run preview    # Browser with live reload
npm run dev        # Watch mode
```

### Asset Paths

From within `slides/deck.md`, reference assets with relative paths:
```markdown
![w:120](../assets/logos/marinade-logo.svg)
![w:80](../assets/logos/marinade-icon.png)
![bg](../assets/backgrounds/teal-gradient.png)
```

Marp image sizing: `![w:200](path)` for width, `![h:100](path)` for height, `![bg](path)` for background.

### Slide Background Assets

3 background images extracted from the master PPTX, bundled in the skill at `~/.claude/skills/marinade-brand-design/assets/backgrounds/`:

| File | Visual | Usage |
|------|--------|-------|
| `teal-gradient.png` | Teal-to-mint vertical gradient with subtle noise texture | Cover slides, title backgrounds. Auto-applied to `cover` class. |
| `deep-teal-solid.png` | Dark teal gradient into darker at bottom | Dark accent sections. Auto-applied to `teal` class. |
| `light-teal-solid.png` | Very light mint/teal solid | Subtle variation from white, section transitions. Manual `![bg]`. |

**Dark background** (`deep-teal-solid`): Auto-applied to `<!-- _class: teal -->`. Also works with `invert` class for white/light-teal text.

**Light background** (`light-teal-solid`): Keeps dark text readable. Use for subtle section breaks without going full-dark.

```markdown
<!-- Dark cover slide -->
<!-- _class: lead invert -->
![bg](../assets/backgrounds/deep-teal-solid.png)

# Your title here

---

<!-- Subtle light background -->
![bg](../assets/backgrounds/light-teal-solid.png)

## Content with dark text
```

---

## DIAGRAMS AND CHARTS

### Mermaid Diagrams

Approaches ranked by reliability:

#### Approach 1: Inline Mermaid code blocks

Source of truth for diagram content. Renders as code in Marp:

```markdown
​```mermaid
graph LR
    A[User SOL] -->|Deposit| B[Marinade Pool]
    B -->|Mint| C[mSOL Token]
​```
```

#### Approach 2: beautiful-mermaid color-mix() pattern

Inspired by [beautiful-mermaid](https://github.com/lukilabs/beautiful-mermaid), derive all diagram colors from two base variables:

```css
/* Marinade Mermaid base vars */
--bg: #EDF5F3;   /* slide background (light-teal) */
--fg: #194544;   /* deep teal foreground */

/* Derived palette via color-mix() */
Node fill:    color-mix(in srgb, var(--fg) 8%, var(--bg))   /* very subtle tint */
Node stroke:  color-mix(in srgb, var(--fg) 25%, var(--bg))  /* visible border */
Edge lines:   color-mix(in srgb, var(--fg) 50%, var(--bg))  /* medium contrast */
Edge labels:  color-mix(in srgb, var(--fg) 40%, var(--bg))  /* readable labels */
Arrow heads:  color-mix(in srgb, var(--fg) 85%, var(--bg))  /* strong accent */

/* Accent nodes use brand-teal directly */
Primary node:   fill: #308D8A, stroke: #194544, color: #FFFFFF
Secondary node: fill: #94C9C8, stroke: #2B8784, color: #151A1A
Tertiary node:  fill: #447579, stroke: #194544, color: #FFFFFF
```

For dark slides (`--bg: #0c2a29`, `--fg: #94C9C8`), the same derivation produces a dark-mode diagram.

#### Approach 3: Pre-rendered SVGs (for production output)

1. Generate diagrams at [mermaid.live](https://mermaid.live/) or use `mmdc` CLI
2. Apply Marinade brand colors in the Mermaid theme config:

```json
{
  "theme": "base",
  "themeVariables": {
    "primaryColor": "#308D8A",
    "primaryTextColor": "#FFFFFF",
    "primaryBorderColor": "#194544",
    "secondaryColor": "#94C9C8",
    "secondaryTextColor": "#151A1A",
    "secondaryBorderColor": "#2B8784",
    "tertiaryColor": "#447579",
    "tertiaryTextColor": "#FFFFFF",
    "tertiaryBorderColor": "#194544",
    "lineColor": "#308D8A",
    "textColor": "#151A1A",
    "mainBkg": "#308D8A",
    "nodeBorder": "#194544",
    "clusterBkg": "#F3F3F3",
    "clusterBorder": "#94C9C8",
    "titleColor": "#151A1A",
    "edgeLabelBackground": "#EDF5F3",
    "fontFamily": "DM Sans, sans-serif",
    "fontSize": "14px"
  }
}
```

3. Export as SVG, save to `diagrams/` folder
4. Embed in slides: `![w:800](../diagrams/staking-flow.svg)`

#### Approach 4: Mermaid style directives (inline in code blocks)

When writing Mermaid code blocks for documentation or future rendering, always include Marinade brand styling:

```
style NodeName fill:#308D8A,stroke:#194544,color:#FFFFFF
style NodeName fill:#94C9C8,stroke:#2B8784,color:#151A1A
style NodeName fill:#447579,stroke:#194544,color:#FFFFFF
style NodeName fill:#59A9A7,stroke:#2B8784,color:#FFFFFF
style NodeName fill:#194544,stroke:#151A1A,color:#FFFFFF
style NodeName fill:#FFFFFF,stroke:#308D8A,color:#151A1A
```

### Mermaid Diagram Types for Presentations

| Diagram | Use case | Example |
|---------|----------|---------|
| `graph LR` | Process flows, staking flows | SOL → Pool → mSOL → DeFi |
| `graph TB` | Architecture diagrams | Protocol layer stack |
| `pie` | Revenue/allocation breakdown | Revenue sources, delegation weights |
| `gantt` | Roadmap timelines | Quarterly milestones |
| `sequenceDiagram` | Transaction flows | Stake/unstake sequences |
| `classDiagram` | Smart contract structure | Program accounts |
| `stateDiagram-v2` | State machines | Stake account lifecycle |

### CSS-Only Charts

```html
<div class="bar-chart">
  <div class="bar" style="height:30%">
    <span class="bar-label">$420M</span>
    <span class="bar-cat">Q2 '24</span>
  </div>
  <div class="bar" style="height:60%">
    <span class="bar-label">$1.2B</span>
    <span class="bar-cat">Q4 '24</span>
  </div>
  <div class="bar" style="height:100%">
    <span class="bar-label">$2.1B</span>
    <span class="bar-cat">Q3 '25</span>
  </div>
</div>
```

Bar fill color: `#94C9C8` (light-teal). Labels: `#82B7B7` (chart-teal). No gridlines, no axis lines — data speaks for itself.

### Pie Charts via Mermaid

```mermaid
pie title Delegation distribution
    "Performance score" : 35
    "Decentralization" : 25
    "Commission rate" : 20
    "Uptime history" : 15
    "Community stake" : 5
```

Use the Marinade teal spectrum for slices. Max 5-6 slices for readability.

### Chart Color Sequence

When creating any chart or diagram, use colors in this order:
1. `#308D8A` (brand-teal) — primary data
2. `#94C9C8` (light-teal) — secondary data
3. `#447579` (muted-teal) — tertiary
4. `#59A9A7` (soft-teal) — quaternary
5. `#194544` (deep-teal) — quinary
6. `#82B7B7` (chart-teal) — annotations/labels

### Tables as Data Visualization

Marp renders Markdown tables with the Marinade theme styling. Use tables for competitive comparisons, feature matrices, and metric summaries:

```markdown
| Metric | Q1 | Q2 | Q3 | Q4 |
|--------|----|----|----|----|
| **TVL** | $1.2B | $1.5B | $1.8B | $2.1B |
| **APY** | 7.2% | 7.8% | 8.3% | 8.81% |
```

Tables use `font-variant-numeric: tabular-nums` for aligned numbers. Header border is `#308D8A`.

---

## MARP GENERATION WORKFLOW

1. Copy frontmatter template, set theme to `marinade`
2. Map content to the 16 slide archetypes
3. Apply class variants per slide purpose
4. Use HTML utilities for metrics, cards, columns, charts
5. Add Mermaid blocks for diagrams (pre-render for production)
6. Reference assets with relative paths
7. Build (`npm run build`) and verify output
8. Export (`npm run pdf` / `npm run pptx`)

### Slide Pacing
- 1 key message per slide
- Max 6-7 content slides between section breaks
- Statement slides as section dividers
- Lead slides for opening and closing
- Alternate text-heavy and visual slides

---

## VERIFICATION CHECKLIST

Run through this checklist before presenting any output. Every item must pass.

### Colors
- [ ] Every color used appears in the strict palette (no invented colors)
- [ ] `brand-teal` (#308D8A) on white is only used at 18pt+ (24px+)
- [ ] `muted-text` (#7F7F7F) on white is only used at 18pt+ (24px+)
- [ ] Body text on white uses `dark-primary`, `deep-teal`, or `body-secondary` only
- [ ] Text on dark/teal backgrounds uses `white` or `light-teal`

### Typography
- [ ] All text is DM Sans (400 or 600 weight). No Calibri, Arial, or system fonts.
- [ ] PT Serif italic used max once per slide, for a single accent word only
- [ ] `font-variant-numeric: tabular-nums` on all numbers (TVL, APY, prices, counts)
- [ ] `-webkit-font-smoothing: antialiased` applied
- [ ] Minimum body text: 16px (web) / 21pt (slides)
- [ ] Sentence case throughout. ALL CAPS only for acronyms (TAM, SAM, SOM, APY, SOL)

### Layout
- [ ] Slide maps to one of the 16 archetypes (no hybrid/invented layouts)
- [ ] Content fills 60-70% max — remaining is intentional white space
- [ ] Elements align to 12-column grid (0.83" margins)
- [ ] Text never overflows containers (`overflow: hidden`, `word-break: break-word`)

### Tone
- [ ] No exclamation marks
- [ ] No hype words ("revolutionary", "game-changing", "disrupting", "unlocking potential")
- [ ] Metrics stated directly with numbers, not vague claims
- [ ] One key message per slide

### Technical
- [ ] Slide dimensions are 1920x1080 (16:9)
- [ ] Asset paths resolve correctly (relative paths from slide location)
- [ ] Lucide icons use stroke-width 1.5, correct brand colors
- [ ] Interactive icons have 44px+ touch targets and aria-labels
- [ ] `prefers-reduced-motion: reduce` included for any animations
