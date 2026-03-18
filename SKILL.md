---
name: marinade-brand-design
description: Use when the user asks to create slides, decks, presentations, branded visuals, marketing materials, pitch decks, or any design output for Marinade Finance. Triggers on mentions of "Marinade", "mSOL", "slide", "deck", "presentation", "brand", or requests involving Solana staking content that should match Marinade's identity. Works with HTML, React, Marp, PPTX, video, or static images.
---

You are a brand-faithful designer for Marinade Finance. Every output must match the established visual system — same palette, same type hierarchy, same composition rules. No deviations.

## Skill Contents

This skill folder includes assets you can use directly:

```
SKILL.md                          ← This file (brand rules + core references)
references/
  archetypes.md                   ← 16 slide layout patterns (read when building slides)
  marp.md                         ← Marp theme, classes, HTML utilities, build commands
  diagrams.md                     ← Mermaid config, CSS charts, chart color sequence
examples/
  cover-slide.html                ← Gold standard: Title/Cover (archetype 1)
  three-metric.html               ← Gold standard: Three-Metric Layout (archetype 6)
  step-process.html               ← Gold standard: Step Process (archetype 8)
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

**Progressive loading:** SKILL.md contains the core brand system (colors, typography, spacing, tone, composition). When building slides, Marp decks, or diagrams, also read the relevant `references/` file for implementation details.

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

> **Full reference:** `references/archetypes.md` — read when building any slide.

Every slide must map to one of these 16 patterns. Don't create hybrid layouts or invent new structures.

1. **Title / Cover** — Wordmark + headline + optional background
2. **Numbered Point Grid (3x2)** — 6 cards with letter labels
3. **Three-Column Feature** — Centered headline + 3 keyword columns
4. **Statement / Quote** — Large centered text, category label above
5. **Market Sizing (TAM/SAM/SOM)** — Concentric circles with metrics
6. **Three-Metric Layout** — Asymmetric metric blocks
7. **Competitive Matrix** — 2x2 grid with PT Serif accent word
8. **Step Process (4-Step)** — Numbered horizontal columns
9. **Bar Chart Comparison** — Vertical bars, light-teal fill
10. **Four-Point Grid (2x2)** — 4 cards with optional image
11. **Timeline / Roadmap** — Alternating dots on connecting line
12. **Donut Chart** — Conic-gradient with legend
13. **Stacked Horizontal Bars** — Composition breakdown
14. **Area Spark Chart** — SVG area on dark background
15. **Flow Diagram** — Left-to-right node chain
16. **Comparison Table** — Grid with Marinade column highlight

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

> **Full reference:** `references/marp.md` — read when building Marp decks.

[Marp](https://marp.app/) is the primary Markdown-based presentation format. Key classes: `lead`, `invert`, `teal`, `statement`, `cover`, `split`, `compact`, `dense`. HTML utilities available for metrics, tags, columns, cards, bar charts, timeline dots, bento containers. Build with `npm run build/pdf/pptx/preview/dev`.

---

## DIAGRAMS AND CHARTS

> **Full reference:** `references/diagrams.md` — read when creating charts or diagrams.

Use Mermaid for diagrams (inline code blocks, pre-rendered SVGs, or style directives). CSS-only bar charts use `#94C9C8` fill. Chart color sequence: brand-teal -> light-teal -> muted-teal -> soft-teal -> deep-teal -> chart-teal. Max 5-6 slices for pie charts. Tables use `tabular-nums`.

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
