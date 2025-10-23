# EdgeLight Framework - Design Guidelines

## Design Approach

**Selected Approach:** Reference-Based with Modern Tech Product Inspiration

Drawing from industry leaders in developer tools and technical products:
- **Linear**: Bold typography, clean layouts, subtle animations
- **Stripe**: Technical sophistication with visual elegance, data-first design
- **Vercel**: Modern gradients, generous spacing, developer-focused aesthetics
- **Notion**: Clean information architecture, scannable content blocks

**Design Principles:**
1. Technical credibility through precision and clarity
2. Visual impact that communicates $60K professional value
3. Data-driven storytelling with interactive elements
4. Seamless blend of technical depth and accessibility

---

## Typography System

**Font Families (via Google Fonts CDN):**
- **Display/Headers:** 'Inter' (weights: 700, 800, 900)
- **Body/Technical:** 'Inter' (weights: 400, 500, 600)
- **Code/Metrics:** 'JetBrains Mono' (weight: 400)

**Type Scale:**
- Hero Headline: text-6xl lg:text-7xl xl:text-8xl (font-weight: 800)
- Section Titles: text-4xl lg:text-5xl (font-weight: 700)
- Subsection Titles: text-2xl lg:text-3xl (font-weight: 600)
- Feature Headings: text-xl lg:text-2xl (font-weight: 600)
- Body Text: text-base lg:text-lg (font-weight: 400)
- Small Text/Labels: text-sm (font-weight: 500)
- Metrics/Numbers: text-3xl to text-5xl (font-weight: 700, monospace)
- Code Snippets: text-sm (monospace)

---

## Layout System

**Spacing Primitives (Tailwind Units):**
Primary spacing set: **4, 6, 8, 12, 16, 20, 24, 32**

- Component padding: p-6 to p-8
- Section vertical spacing: py-20 to py-32 (desktop), py-12 to py-16 (mobile)
- Card spacing: p-6 lg:p-8
- Grid gaps: gap-6 to gap-8
- Element margins: mb-4, mb-6, mb-8, mb-12

**Container Strategy:**
- Full-width sections with inner max-w-7xl mx-auto px-6 lg:px-8
- Content sections: max-w-6xl
- Text-heavy areas: max-w-4xl
- Dashboard/metrics: max-w-7xl (full width for data visualization)

**Grid System:**
- Feature cards: grid-cols-1 md:grid-cols-2 lg:grid-cols-3
- Metrics display: grid-cols-2 lg:grid-cols-4
- Before/after comparisons: grid-cols-1 lg:grid-cols-2
- Technical specs: Single column with nested grids where appropriate

---

## Component Library

### Navigation
- Fixed header with backdrop blur effect
- Logo/title on left, navigation links center/right
- CTA button (Download/GitHub) on far right
- Height: h-16 to h-20
- Sticky positioning with smooth shadow on scroll

### Hero Section
**Layout:** Full viewport height (min-h-screen) with centered content
- Large headline with gradient text treatment
- Compelling subheadline (max-w-3xl mx-auto)
- Dual CTA buttons (primary + secondary) with spacing gap-4
- Animated metrics ticker below CTAs showing key stats (FPS, Cost Savings, Latency)
- Background: Subtle animated grid pattern or geometric shapes

**Image Strategy:** 
- Abstract tech visualization background (circuit patterns, neural network nodes, or data flow diagrams)
- Semi-transparent overlay for text readability
- Optional: Floating 3D mockup of Raspberry Pi or edge device

### Interactive Metrics Dashboard
**Multi-column layout (grid-cols-1 lg:grid-cols-2):**

Left Column - Performance Comparison Table:
- Side-by-side comparison cards (Baseline vs Optimized)
- Large metric numbers with icons (Heroicons)
- Progress bars showing improvements
- Metrics: Latency, FPS, Memory, Accuracy
- Card style with borders and subtle shadows

Right Column - Live Chart Visualization:
- Animated bar/line chart showing performance gains
- Use chart placeholder with clear axis labels
- Interactive data points (hover states with tooltips)
- Chart legend with clear labeling

### Technical Architecture Section
**Full-width diagram area:**
- ASCII flowchart converted to visual diagram
- Horizontal flow: Input → Pipeline Stages → Output
- Each stage as a card with icon + title + brief description
- Connecting arrows/lines between stages
- Use grid-cols-2 lg:grid-cols-4 xl:grid-cols-7 for pipeline stages

### Results Showcase
**Before/After Split Layout (grid-cols-1 lg:grid-cols-2):**
- Large comparison cards with prominent "Before" and "After" labels
- Performance metrics in table format inside each card
- Visual indicators (icons from Heroicons) for improvements
- Percentage change badges (e.g., "+300% faster")

### Video Demo Section
**Centered full-width container:**
- Video placeholder with 16:9 aspect ratio
- Large play button overlay
- Caption below: "Side-by-side GPU vs CPU comparison"
- Optional: Dual video panels for simultaneous playback mockup

### Downloadable Artifacts
**Grid layout (grid-cols-1 md:grid-cols-2 lg:grid-cols-3):**
- File cards with:
  - File type icon (Font Awesome file icons)
  - Filename in monospace font
  - File size and description
  - Download button/link
- Categories: Models, Scripts, Datasets, Documentation

### Cost Savings Calculator
**Interactive component (single column, max-w-4xl):**
- Slider input for number of devices
- Calculation breakdown showing:
  - GPU hardware cost (Jetson modules)
  - CPU hardware cost (Raspberry Pi)
  - Total savings with prominent display
- Results displayed as large numbers with currency formatting
- Visual representation: Simple bar comparison

### Technical Specifications Accordion
**Stacked accordion items (single column):**
- Each item: Pipeline stage title + expand icon
- Expanded content: Detailed description, code snippet examples, duration
- Smooth expand/collapse animations (max-height transitions)
- Clear visual hierarchy with borders/dividers

### Footer
**Multi-column grid (grid-cols-1 md:grid-cols-3):**
- Column 1: Project branding + tagline
- Column 2: Quick links (Documentation, GitHub, Demo, Contact)
- Column 3: Download CTAs + Social links
- Bottom bar: Copyright, links to related resources
- Generous padding: py-12 to py-16

---

## Animations & Interactions

**Strategic Animation Budget:**
- Hero section: Subtle fade-in on load, gentle floating animation on background elements
- Metrics counter: Number count-up animation on scroll into view
- Chart: Animated bar growth on initial render
- Accordion: Smooth height transitions (duration-300)
- Hover states: Subtle scale transforms (hover:scale-105) on cards
- Scroll-triggered: Fade-in-up animations for major sections (use Intersection Observer)

**Performance Rule:** Limit animations to CSS transforms (translate, scale) and opacity only

---

## Images

### Hero Background
**Description:** Abstract technical visualization - neural network nodes connected by glowing lines, circuit board patterns, or flowing data particles
**Placement:** Full-screen background with overlay gradient for text contrast
**Treatment:** Slightly blurred (blur-sm), reduced opacity (opacity-20 to opacity-30)

### Technical Diagram/Architecture
**Description:** Visual representation of the optimization pipeline - show model flowing through stages with icons representing each transformation
**Placement:** Full-width section after hero
**Style:** Clean, diagrammatic with connecting arrows

### Demo Video Thumbnail
**Description:** Split-screen showing same scene processed by GPU (left) and optimized CPU (right) with bounding boxes
**Placement:** Center of video demo section
**Treatment:** 16:9 aspect ratio, subtle shadow

### Before/After Comparison
**Description:** Performance graphs or actual inference outputs showing quality comparison
**Placement:** Results showcase section, side-by-side layout
**Treatment:** Equal sizing, clear labels

### Device Photography (Optional)
**Description:** Raspberry Pi 4 or similar SBC running the framework
**Placement:** Cost savings or capabilities section
**Treatment:** Clean product photography style, well-lit

---

## Accessibility & Form Elements

- All interactive elements have clear focus states (ring-2 ring-offset-2)
- Sufficient contrast ratios for all text
- Semantic HTML: proper heading hierarchy (h1 → h2 → h3)
- ARIA labels for icon-only buttons
- Keyboard navigation support for all interactive components
- Form inputs (if contact form added): Consistent styling with clear labels, placeholder text, and validation states

---

## Page Structure Flow

1. **Fixed Navigation** (always visible)
2. **Hero Section** (100vh) - Headline, CTAs, animated metrics
3. **Problem Statement** (py-20) - Brief context on GPU cost challenges
4. **Interactive Metrics Dashboard** (py-24) - Main results showcase
5. **Technical Architecture** (py-24) - Visual pipeline diagram
6. **Detailed Results** (py-24) - Before/after tables and charts
7. **Video Demo** (py-20) - Embedded comparison video
8. **Cost Savings Calculator** (py-24) - Interactive ROI tool
9. **Downloadable Artifacts** (py-20) - File grid with downloads
10. **Technical Specifications** (py-24) - Accordion with pipeline details
11. **Call-to-Action Banner** (py-16) - Final conversion section
12. **Footer** (py-12) - Links and information

**Total Sections:** 12 comprehensive sections creating a feature-rich, $60K-worthy presentation