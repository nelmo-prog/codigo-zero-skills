---
task: createCarousel()
responsavel: "@visual-generator"
responsavel_type: Agent
atomic_layer: Task
elicit: true

Entrada:
  - campo: briefing
    tipo: string
    origem: User Input
    obrigatorio: true
  - campo: num_slides
    tipo: number
    origem: User Input
    obrigatorio: false

Saida:
  - campo: carousel_slides
    tipo: files
    destino: Console
    persistido: true

Checklist:
  - "[ ] All slides generated as HTML with ANI Design System tokens"
  - "[ ] Screenshots captured as PNG 1080x1350"
  - "[ ] Visual hierarchy clear on every slide"
  - "[ ] Brand consistency maintained across all slides"
---

# Task: Create Instagram Carousel Slides

**Task ID:** DESIGN-CAROUSEL-001
**Version:** 1.0.0
**Command:** `/design-squad:create-carousel`
**Agent:** Visual Generator (visual-generator) + Design Chief (design-chief)
**Purpose:** Generate production-ready Instagram carousel slides as PNG images from a text briefing.

---

## Inputs

| Input | Source | Required |
|-------|--------|----------|
| `briefing` | Slide content with text for each slide | YES |
| `num_slides` | Number of slides (default: auto-detect from briefing) | NO |
| `style` | Visual style: "dark-premium", "glass", "brutalist", "minimal" (default: dark-premium) | NO |
| `brand_colors` | Override colors (default: ANI palette) | NO |
| `format` | Dimensions: "instagram" (1080x1350), "story" (1080x1920), "linkedin" (1200x1200) | NO |
| `output_dir` | Where to save PNGs (default: ./carousel-output/) | NO |

## Preconditions

1. Python with Pillow installed OR Selenium with Chrome for HTML-to-PNG
2. ANI Design System tokens available at `~/ani-design-system/tokens/`
3. Briefing contains clear slide-by-slide content

## Execution Phases

### Phase 1: Parse Briefing (design-chief)

1. Read the user's briefing and identify each slide
2. For each slide extract:
   - Slide number and type (cover, content, comparison, CTA, etc.)
   - Headline text
   - Body text / bullet points
   - Visual direction (diagram, list, comparison, pyramid, hub-spoke, etc.)
   - Accent color override if specified
3. Determine total slide count
4. Plan visual variety (no two consecutive slides should have the same layout)

### Phase 2: Design Each Slide (visual-generator)

For each slide, create an HTML file using ANI Design System tokens:

**Layout Types Available:**
- `cover` — Big headline centered, subtitle, brand elements, CTA arrow
- `problem` — Pain points with urgency visual (red accents, question marks)
- `solution` — Two-column or split comparison (before/after, tool A + tool B)
- `feature` — Icon + title + description, checklist with green checks
- `hub-spoke` — Central element with radial connections (integrations)
- `flow` — Numbered steps with connecting arrows (vertical or horizontal)
- `grid` — 2x2 or 3x1 cards for use cases or features
- `comparison` — Side-by-side columns (red vs green, old vs new)
- `pyramid` — Hierarchy visualization (3 tiers with labels)
- `stats` — Big numbers with supporting text
- `quote` — Pull quote with attribution
- `cta` — Call to action with handle, arrows, premium gradient

**Design Rules:**
- Background: always var(--bg-canvas) (#070a0d) or subtle gradient
- Dot grid pattern at 8% opacity for texture
- Headlines: Garet/Inter Extra Bold, white or brand color
- Body: Poppins Regular, secondary gray
- Max 6-8 lines of text per slide (readability at mobile size)
- Slide number indicator bottom-right (N/total)
- Color accents match slide emotion (cyan=tech, green=positive, red=problem, gold=premium)
- Glass cards for grouping related content
- Glow effects on key elements (buttons, icons, highlights)
- All text must be readable at Instagram mobile size (min 24px effective)

### Phase 3: Render to PNG (visual-generator)

For each HTML slide:
1. Open in headless Chrome via Selenium
2. Set viewport to exact dimensions (1080x1350 for Instagram)
3. Wait for fonts to load (1s delay)
4. Capture screenshot as PNG
5. Save to output directory with naming: `slide_XX_type.png`

**Fallback:** If Selenium unavailable, use Python Pillow to render slides programmatically with:
- ImageDraw for shapes, lines, gradients
- ImageFont with system fonts (Roboto Bold, Arial)
- Same color palette and layout logic

### Phase 4: Quality Review (design-chief)

Review each generated slide against:
- [ ] Text is readable at mobile size
- [ ] Visual hierarchy guides the eye (headline → body → CTA)
- [ ] Brand colors consistent across all slides
- [ ] No text overflow or clipping
- [ ] Slide number visible
- [ ] Emotional tone matches content (problem=red, solution=cyan, CTA=gold)
- [ ] Sufficient contrast (WCAG AA minimum)

## Output Format

```
carousel-output/
  slide_01_cover.png
  slide_02_problem.png
  slide_03_solution.png
  ...
  slide_10_cta.png
  slides.html          (all slides as single HTML for preview)
```

## Example Usage

```
/design-squad:create-carousel

Briefing:
SLIDE 1 - CAPA: "Claude Code + OpenClaw — A dupla de IA que substitui uma equipe inteira"
SLIDE 2 - PROBLEMA: "Voce cria algo incrivel com IA. E depois? Quem roda isso todo dia?"
SLIDE 3 - SOLUCAO: "Claude Code = Construtor, OpenClaw = Operador"
...
```

## Veto Conditions

- **NEVER** generate slides with text smaller than 24px effective size
- **NEVER** use more than 3 colors per slide (brand + accent + neutral)
- **NEVER** put more than 8 lines of text on a single slide
- **NEVER** skip the dot grid texture (brand signature)
- **NEVER** use light/white backgrounds (ANI is dark-mode native)
- **NEVER** forget the slide number indicator

## Completion Criteria

- [ ] All slides generated as PNG at correct dimensions
- [ ] Every slide follows ANI Design System tokens
- [ ] Text readable at Instagram mobile viewport
- [ ] Visual variety across slides (no repetitive layouts)
- [ ] Output directory contains all PNGs ready for upload
