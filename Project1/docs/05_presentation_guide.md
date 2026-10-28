# Course Evaluation Presentation Guide: City Zoo Sanctuary Website

**Project:** City Zoo Sanctuary Static Website (Pure Semantic HTML5 & CSS3)  
**Format:** 2-Person Pair Presentation  
**Total Target Time:** 5 Minutes (300 Seconds)  
**Division of Roles:** Partner A (50% / 150s) | Partner B (50% / 150s)  
**Evaluator Goal:** Demonstrate full compliance with semantic HTML5 standards, responsive CSS Grid/Flexbox architecture, accessible components, and rich media embeds without external frameworks or JavaScript.

---

## Presentation Timeline Overview

```
[0:00 - 0:45] Partner A: Introduction, Architectural Vision & Semantic Layout (index.html)
[0:45 - 1:45] Partner B: Mobile-First Responsiveness & DevTools Demonstration (index.html)
[1:45 - 2:45] Partner A: Animals Gallery, Fluid CSS Grid & Media Embeds (animals.html)
[2:45 - 3:45] Partner B: Accessible Pricing Table & Form Validation (tickets.html)
[3:45 - 4:45] Partner A: CSS Token System, Micro-Interactions & Responsive Map (tickets.html)
[4:45 - 5:00] Partner B: QA Audit Results, Standards Compliance & Wrap-up
```

---

## Step-by-Step Walkthrough & Script

### Segment 1: Introduction, Architecture & Semantic HTML5 (0:00 – 0:45)
**Speaker:** Partner A  
**Time:** 45 seconds

* **Screen Action:**
  1. Open browser in full desktop mode displaying `index.html`.
  2. Right-click anywhere and select **Inspect** to reveal the Elements panel.
  3. Briefly hover over top-level semantic tags: `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, and `<footer>`.
* **Speaking Points (Partner A):**
  > "Hello everyone. Today we are presenting the City Zoo Sanctuary website, built strictly with pure semantic HTML5 and modern CSS3—free of JavaScript frameworks or utility libraries.
  >
  > Our architectural priority was semantic integrity and web accessibility. As shown here in DevTools, the document is structured strictly around semantic landmark regions: a sticky `<header>` with flex-aligned navigation, a single clear `<main>` landmark with structured `<section>` containers, a self-contained `<article>` spotlighting our 'Animal of the Month', a complementary `<aside>` for daily feeding schedules, and a comprehensive `<footer>`.
  >
  > Every link across the site meets W3C guidelines, with verified internal links and secure external references utilizing `rel="noopener noreferrer"`."

---

### Segment 2: Mobile Responsiveness & Flexbox Header (0:45 – 1:45)
**Speaker:** Partner B  
**Time:** 60 seconds

* **Screen Action:**
  1. In Chrome/Edge DevTools, click the **Toggle device toolbar** button (`Ctrl+Shift+M` / `Cmd+Shift+M`).
  2. Switch to an iPhone or 375px mobile viewport.
  3. Scroll through the homepage to show the single-column reflow.
  4. Drag the DevTools width resizer past `768px` to demonstrate the breakpoint transition into the two-column layout.
* **Speaking Points (Partner B):**
  > "Thanks, Partner A. Moving to the responsive design system, we adopted a strict **Mobile-First methodology**.
  >
  > Notice when we toggle the mobile device emulator at 375 pixels:
  > - The global navigation menu in `<header>` stacks naturally into touch-friendly targets without layout overflow.
  > - The desktop two-column split automatically cascades into a clean single-column sequence: hero banner, primary mission card, featured lion article, operating hours, and finally the aside facts.
  >
  > Now, watch as I scale the viewport across our main breakpoint at 769 pixels:
  > - CSS Flexbox converts the navigation into a distributed horizontal header.
  > - CSS Grid smoothly activates a `2fr 1fr` split, placing our main narrative on the left and the keeper schedule `<aside>` on the right.
  > - Notice the zero horizontal scrolling and fluid typography scaling throughout."

---

### Segment 3: Animals Gallery, Fluid CSS Grid & Media Elements (1:45 – 2:45)
**Speaker:** Partner A  
**Time:** 60 seconds

* **Screen Action:**
  1. Click the **Animals & Habitats** link in the nav bar to navigate to `animals.html`.
  2. Scroll down to the **Featured Wildlife Gallery**.
  3. Hover over several animal cards to showcase image zoom, tag badges, and smooth card elevation.
  4. Slowly resize the window width to demonstrate fluid card wrapping (`minmax(280px, 1fr)`).
  5. Scroll to the **Interactive Media** section at the bottom, briefly play the native `<video>` clip and the `<audio>` player, and highlight the PDF `<embed>`.
* **Speaking Points (Partner A):**
  > "Navigating to `animals.html`, we showcase our species collection and multimedia integration.
  >
  > In the gallery section, we implemented modern two-dimensional CSS Grid using:
  > `grid-template-columns: repeat(auto-fit, minmax(280px, 1fr))`
  > This provides automatic reflow: on mobile it forms 1 column, on tablets 2 columns, and on desktop 3 columns—all without arbitrary per-card breakpoint overrides.
  >
  > For the media requirement, we deployed three distinct elements:
  > 1. A featured wildlife video embed: *Meet new African lion Kiume*, embedded in a fluid 16:9 aspect-ratio container with fullscreen and HD streaming capabilities.
  > 2. A native HTML5 `<audio>` soundscape capturing savannah morning recordings.
  > 3. An `<embed>` element displaying our downloadable park visitor guide and map directly in the viewport."

---

### Segment 4: Admission Pricing Table & Interactive Form (2:45 – 3:45)
**Speaker:** Partner B  
**Time:** 60 seconds

* **Screen Action:**
  1. Click **Tickets & Visit** in the navigation to go to `tickets.html`.
  2. Scroll to the **Standard Admission Pricing** table.
  3. In DevTools, inspect the table to show `<caption>`, `<thead>`, `<tbody>`, `<tfoot>`, `<th scope="col">`, and `<th scope="row">`.
  4. Switch to mobile view to show the table's horizontal touch-scrolling container (`.table-responsive-wrapper`).
  5. Return to desktop and scroll down to the **Online Ticket Inquiry & Reservation** form.
  6. Attempt to click **Confirm Reservation** with empty fields to show browser form validation; type in valid/invalid values (e.g., date, email, dropdown, quantity).
* **Speaking Points (Partner B):**
  > "On `tickets.html`, we address visitor planning with two major interactive components:
  >
  > First, our **Admission Pricing Table**. It is built for full screen-reader accessibility, utilizing `<caption>`, structured column scopes (`scope="col"`), and row scopes (`scope="row"`). For mobile usability, the table is wrapped in a dedicated overflow container so wider rate tiers can scroll horizontally on narrow screens without breaking the page container.
  >
  > Second, our **Online Reservation Form**. It contains 7 distinct input controls:
  > - Name and email with HTML5 autocompletion attributes.
  > - Phone input with regex pattern validation.
  > - Date picker, integer ticket quantity counter, and accessible habitat `<select>` dropdown.
  > - A `<textarea>` for accessibility needs.
  > Every field has an explicit `<label for="...">` pairing and assistive helper text, satisfying WCAG 2.1 accessibility criteria."

---

### Segment 5: Design Tokens, Micro-Interactions & Directions Map (3:45 – 4:45)
**Speaker:** Partner A  
**Time:** 60 seconds

* **Screen Action:**
  1. In DevTools, open the Sources or Elements Styles pane to highlight `css/variables.css` (`:root` tokens).
  2. Hover over buttons (`.btn-primary` and `.btn-secondary`) to show the micro-interaction (`transform: translateY(-2px)`, shadow elevation, and active pushdown).
  3. Hover over links in the body to show the smooth color and underline opacity transition.
  4. Scroll down to the **Park Location & Directions** card on `tickets.html` to showcase the 16:9 responsive Google Maps `<iframe>`.
* **Speaking Points (Partner A):**
  > "Underpinning our design is a maintainable token system defined in `variables.css`. All colors, spacing steps, typography scales, and shadows are managed through centralized CSS Custom Properties.
  >
  > To elevate the user experience without cluttering the stylesheet, we introduced subtle micro-interactions:
  > - Buttons lift slightly with an elevated box-shadow on hover and depress naturally on `:active`.
  > - Content cards gently elevate on hover, providing tactile feedback.
  > - Text links feature smooth color transitions and animated underline accents.
  >
  > Finally, our transit guide embeds an interactive Google Maps `<iframe>` enclosed within a CSS aspect-ratio container (`16 / 9`) with lazy loading enabled, preventing Cumulative Layout Shift during page load."

---

### Segment 6: QA Audit Results, Standards Compliance & Wrap-up (4:45 – 5:00)
**Speaker:** Partner B  
**Time:** 15 seconds

* **Screen Action:**
  1. Scroll down to the footer showing the copyright and standards note.
  2. Briefly show the `docs/04_qa_report.md` file in the IDE or project tree.
  3. Close with both presenters facing the evaluator.
* **Speaking Points (Partner B):**
  > "Before submitting, we conducted a rigorous automated and manual QA audit documented in `docs/04_qa_report.md`. Our codebase passed `html-validate` with zero errors, zero warnings, and 100% compliance across semantic landmarks, lists, tables, forms, and responsive breakpoints.
  >
  > Thank you for your time. We are now ready to answer any questions!"

---

## Evaluator Q&A Preparation Sheet

| Anticipated Evaluator Question | Recommended Response | Presenter |
| :--- | :--- | :---: |
| **Why use `auto-fit` instead of explicit breakpoints in the gallery?** | "`repeat(auto-fit, minmax(280px, 1fr))` dynamically calculates how many 280px cards fit within the container. If the user has a wide monitor, it naturally expands to 3 or 4 columns without requiring rigid media queries, promoting true fluid design." | Partner A |
| **How do you ensure accessibility for the pricing table and form?** | "The table uses `<caption>` and explicit `scope` attributes (`col` for headers, `row` for ticket tiers) so screen readers can announce context. The form pairs every control with explicit `<label for="...">` tags and descriptive helper spans." | Partner B |
| **How did you prevent layout shift with the embedded map and media?** | "We applied modern CSS `aspect-ratio: 16 / 9` on map containers and `16 / 10` on animal image wrappers, ensuring the browser reserves the exact space before remote assets finish loading." | Partner A |
| **Why Mobile-First instead of Desktop-First?** | "Mobile-First guarantees a lighter initial CSS cascade, faster rendering on resource-constrained devices, and cleaner progressive enhancement as screen real estate increases." | Partner B |

