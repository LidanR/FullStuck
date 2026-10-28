# Project Architecture & Baseline Styling Plan: Zoo Static Website

## 1. Folder Structure Mapping

The website uses a clean, maintainable static project layout. HTML pages reside in the project root, keeping relative asset paths simple and predictable across environments.

```text
Project1/
├── index.html                  # Homepage (Hero, Highlights, Daily Schedule, Hours)
├── animals.html                # Animals & Habitats (Bio-zones, Gallery, Native Video)
├── tickets.html                # Tickets & Visit Planning (Pricing Table, Booking Form, Map)
├── css/
│   ├── variables.css           # Design tokens, color palette, typography & spacing
│   ├── layout.css              # Global layout, header, nav, grid & flex rules, footer
│   └── components.css          # Cards, tables, forms, buttons & badges
├── media/
│   ├── images/
│   │   ├── logo.svg            # Zoo branding vector logo
│   │   ├── hero-banner.jpg     # High-resolution hero background
│   │   ├── savannah.jpg        # Habitat feature: Savannah
│   │   ├── rainforest.jpg      # Habitat feature: Rainforest
│   │   ├── lion.jpg            # Species card image
│   │   ├── elephant.jpg        # Species card image
│   │   └── penguin.jpg         # Species card image
│   └── video/
│       └── animal-behavior.mp4 # Educational wildlife feature clip
└── docs/
    ├── 01_specification.md     # Requirements and specification document
    └── 02_architecture.md      # Architecture, layout system & link mapping (this document)
```

---

## 2. Layout Plan: CSS Grid & Flexbox Strategy

To guarantee semantic integrity, responsiveness, and clear separation of concerns, the layout applies **CSS Grid** for two-dimensional structure and **CSS Flexbox** for one-dimensional component alignment.

### 2.1 CSS Grid (Two-Dimensional Layouts)
* **Animal Species Gallery (`animals.html`):**
  * Auto-fitting responsive grid: `grid-template-columns: repeat(auto-fit, minmax(280px, 1fr))`.
  * Consistent gap spacing (`gap: var(--space-lg)`) ensuring cards wrap naturally without requiring explicit per-card breakpoint overrides.
* **Home Page Main Content & Aside (`index.html` Desktop View):**
  * Two-column split layout: `grid-template-columns: 2fr 1fr;` pairing the main `#highlights` section with the schedule `<aside>`.
* **Habitat Bio-Zones Showcase (`animals.html`):**
  * Asymmetric or balanced 3-column habitat zone overview (`Savannah`, `Rainforest`, `Arctic`).

### 2.2 CSS Flexbox (One-Dimensional Alignment)
* **Global Navigation Header (`<header>` / `<nav>` on all pages):**
  * `display: flex; justify-content: space-between; align-items: center;`
  * Distributes logo and navigation menu cleanly; aligns menu items (`display: flex; gap: var(--space-md)`).
* **Form Rows & Input Groups (`tickets.html`):**
  * `display: flex; flex-direction: column;` for accessible stacked label-and-input controls.
  * Side-by-side split rows (e.g., Date and Ticket Category) using `flex-direction: row; gap: var(--space-md)`.
* **Card Headers and Footers (`article.animal-card`):**
  * `display: flex; justify-content: space-between; align-items: baseline;` for species common name and conservation badge.
* **Footer Metadata & Social Links (`<footer>` on all pages):**
  * `display: flex; flex-wrap: wrap; justify-content: space-between; align-items: center; gap: var(--space-md)`.

---

## 3. Responsive Breakpoints

The project follows a mobile-first approach with clear, standard viewport tiers:

| Breakpoint Target | Viewport Width | Layout Behavior & Adaptation |
| :--- | :--- | :--- |
| **Mobile** | `<= 768px` | - Single-column flow (`grid-template-columns: 1fr`).<br>- Header navigation shifts to vertical stack or accessible wrapped menu.<br>- Main content and `<aside>` stack vertically.<br>- Table scrolls horizontally via responsive wrapper or fits viewport cleanly.<br>- Form inputs occupy 100% container width. |
| **Desktop** | `> 768px` | - Multi-column grid configurations activate (`2fr 1fr` for highlights/aside, multi-column card grids).<br>- Navigation items align horizontally across the top right.<br>- Side-by-side form inputs and wider interactive table presentations. |

```css
/* Mobile First Base Rules apply by default */

/* Desktop Breakpoint */
@media (min-width: 769px) {
  .site-header {
    flex-direction: row;
  }
  .content-with-aside {
    display: grid;
    grid-template-columns: 2fr 1fr;
    gap: var(--space-xl);
  }
  .form-row-split {
    display: flex;
    gap: var(--space-md);
  }
}
```

---

## 4. Hyperlinks Mapping

All links adhere strictly to accessibility and security standards (`rel="noopener noreferrer"` for external targets).

### 4.1 Internal Links (Global Navigation & User Journeys)
1. **Home (`index.html`)**
   * Primary site entry point, hero banner, daily operating hours, and general zoo overview.
2. **Animals & Habitats (`animals.html`)**
   * Comprehensive species directory, educational bio-zone guides, and featured educational video.
3. **Tickets & Planning (`tickets.html`)**
   * Admission pricing table, visit reservation/inquiry form, and transit directions with location map.

### 4.2 External Authoritative Links
1. **Wikipedia Species & Conservation Reference:**
   * Target: `https://en.wikipedia.org/wiki/Wildlife_conservation` (or specific species articles like `https://en.wikipedia.org/wiki/Lion`).
   * Purpose: Educational reference providing background taxonomy and global conservation classification.
2. **Authoritative Nature Reserve & Conservation Partner:**
   * Target: `https://www.worldwildlife.org/` (World Wildlife Fund) or `https://www.iucnredlist.org/` (IUCN Red List).
   * Purpose: External conservation advocacy partner link in footer and habitat sections to validate wildlife protection standards.
3. **Interactive Navigation & Transit (Google Maps):**
   * Target: `https://maps.google.com/?q=Zoo+Sanctuary`
   * Purpose: External map directions link on `tickets.html` enabling visitors to plan travel routes via GPS and public transit.
