# Slide Archetypes — 16 Master Patterns

Every slide must map to one of these 16 patterns. Don't create hybrid layouts or invent new slide structures.

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
- Nodes: bordered cards with fill progression (outline -> brand-teal -> light-teal -> muted-teal)
- Each node has 1.5px stroke border matching its fill hierarchy
- Arrow SVGs between nodes
- Footnote below with horizontal separator line

### 16. Comparison Table
- Grid table with column highlighting for Marinade
- Marinade column header: brand-teal fill with white text
- Marinade data cells: subtle teal tint background `rgba(48,141,138,0.04)`
- Row dividers: `rgba(48,141,138,0.1)` for subtle separation
- Outer border: `rgba(48,141,138,0.15)` with border-radius
