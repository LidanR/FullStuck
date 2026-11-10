# Project Architecture & CSS Notes

## Folder Structure
```
Project1/
├── index.html
├── animals.html
├── tickets.html
├── css/
│   ├── variables.css
│   ├── style.css
│   └── responsive.css
├── media/
│   ├── Lion.mp4
│   ├── Birds.wav
│   ├── posters/
│   │   └── lion-poster.jpg
│   └── documents/
│       └── visitor-guide.pdf
└── docs/
    ├── 01_specification.md
    ├── 02_architecture.md
    ├── 03_research_snippets.md
    ├── 04_qa_report.md
    └── 05_presentation_guide.md
```

## Styling Approach

### 1. Variables (`variables.css`)
Basic color palette, border colors, shared border-radius and shadow tokens.

### 2. Main Styles (`style.css`)
- Clean base resets and typography.
- Unified card and container styling (`.content-card`, `.sidebar-box`, `.booking-form-card`, `.map-card`).
- Flexbox for navigation, buttons and form controls.
- CSS Grid for the animal card gallery (`repeat(auto-fit, minmax(280px, 1fr))`).

### 3. Responsive Breakpoints (`responsive.css`)
Separated into its own file and imported via `@import url('responsive.css')`:
- Handles desktop screens (`@media (min-width: 769px)`).
- Nav alignment (horizontal layout).
- 2-column home page split (`2fr 1fr`).
- Side-by-side form rows and media grid.
