# QA Verification & Test Report: Zoo Static Website

**Test Engineer Role:** QA Web Engineer  
**Date of Inspection:** 2026-10-28  
**Scope:** HTML files (`index.html`, `animals.html`, `tickets.html`) & CSS stylesheets (`css/variables.css`, `css/style.css`)  
**Project:** Pure Semantic HTML5 & CSS3 Zoo Static Website  
**Overall Status:** **PASSED (100% Compliant)**

---

## 1. Executive Summary

A comprehensive quality assurance inspection was executed across the multi-page static website to verify adherence to W3C standards, project specifications, responsive behavior, accessibility guidelines, and multimedia embedding requirements.

All 3 core HTML pages and the unified CSS architecture were validated using automated static analysis (`html-validate`), responsive layout audits, and manual syntax inspections. Initial issues detected (inline styles and trailing whitespace) were directly rectified and consolidated into dedicated utility classes in `css/style.css`. The codebase now achieves a **clean zero-error validation status**.

---

## 2. Requirements Verification Matrix

| Category | Requirement Criteria | Inspected Target | Status | Notes |
| :--- | :--- | :--- | :---: | :--- |
| **Semantic HTML5** | Proper nesting, closed tags, valid attributes, valid landmarks | All HTML pages (`index.html`, `animals.html`, `tickets.html`) | **PASS** | Valid `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`. Clean W3C / `html-validate` pass. |
| **Internal Hyperlinks** | $\ge 3$ internal links per page | Global navigation + in-page CTAs | **PASS** | `animals.html`: 7 links<br>`index.html`: 11 links<br>`tickets.html`: 8 links |
| **External Hyperlinks** | $\ge 3$ external links per page | Footer partners & species resources | **PASS** | `animals.html`: 11 external links<br>`index.html`: 5 external links<br>`tickets.html`: 4 external links<br>All use `rel="noopener noreferrer"`. |
| **Lists** | Ordered (`<ol>`) & Unordered (`<ul>`) lists | Header, aside, guides, footer | **PASS** | `<ul>` across nav menus, daily hours, footer.<br>`<ol>` for daily schedule talks (`index.html`) and visitor planning tips (`tickets.html`). |
| **Tables** | Styled structured table with semantic elements | `tickets.html` admission pricing | **PASS** | Includes `<caption>`, `<thead>`, `<tbody>`, `<tfoot>`, `<th scope="col">`, `<th scope="row">`, and responsive scroll wrapper. |
| **Forms** | Complete interactive form with diverse input controls | `tickets.html` ticket reservation | **PASS** | Includes `text`, `email`, `tel`, `date`, `number`, `<select>`, `<textarea>`, accessible `<label>` pairings, helper text, and submit button. |
| **Media Elements** | `<img>`, `<video>`, `<audio>`, `<iframe>`, `<embed>` | Across `index.html`, `animals.html`, `tickets.html` | **PASS** | `<img>` (6 on `animals.html`, 1 on `index.html`), `<video>` (native HTML5 controls), `<audio>` (native HTML5 controls), `<iframe>` (lazy-loaded Google Maps), `<embed>` (visitor guide PDF). |
| **Responsive Design** | Flexbox & CSS Grid scaling across mobile & desktop | `css/style.css`, `@media (min-width: 769px)` | **PASS** | Mobile-first baseline (single-column flow, touch targets, wrapped menus) scaling to desktop multi-column Grid (`2fr 1fr`, `repeat(auto-fit, minmax(280px, 1fr))`, 3-column media grid). |

---

## 3. Checklist Audit Breakdown

### 3.1 Hyperlinks Audit ($\ge 3$ Internal & $\ge 3$ External)
* **`index.html`**:
  * **Internal Links (11):** Brand home link (`index.html`), `<nav>` links (`index.html`, `animals.html`, `tickets.html`), hero CTA buttons (`tickets.html`, `animals.html`), in-body link (`animals.html`), hours CTA (`tickets.html`), footer links (`index.html`, `animals.html`, `tickets.html`).
  * **External Links (5):** WWF (`worldwildlife.org`), Wikipedia Lion reference (`en.wikipedia.org/wiki/Lion`), WWF in footer, IUCN Red List (`iucnredlist.org`), Wikipedia Wildlife Conservation (`en.wikipedia.org/wiki/Wildlife_conservation`).
* **`animals.html`**:
  * **Internal Links (7):** Brand home link, `<nav>` links, and footer navigation links.
  * **External Links (11):** 6 Wikipedia species reference links (Lion, Bush Elephant, Humboldt Penguin, Red Panda, Golden Poison Frog, Reticulated Giraffe), video/audio fallback download links, PDF tab link, and 3 footer conservation authority links.
* **`tickets.html`**:
  * **Internal Links (8):** Brand home link, `<nav>` links, planning tip in-body link (`animals.html`), and footer navigation links.
  * **External Links (4):** Google Maps external GPS navigation, WWF, IUCN Red List, Wikipedia Zoo history.

### 3.2 Lists Audit (`<ul>` and `<ol>`)
* **Unordered Lists (`<ul>`):**
  * Global navigation menus on all pages (`.nav-menu`).
  * Operating schedule & entry guidelines (`index.html`).
  * Sanctuary quick facts (`index.html`).
  * Species key facts in gallery cards (`animals.html`).
  * Footer navigation & partner columns on all pages (`.footer-links-list`).
* **Ordered Lists (`<ol>`):**
  * Daily keeper talk demonstrations timeline (`index.html`).
  * "Planning Tips for First-Time Visitors" sequential steps (`tickets.html`).

### 3.3 Styled Table Audit (`tickets.html`)
* **Semantic Structure:** Full implementation of `<table>`, `<caption>`, `<thead>`, `<tbody>`, and `<tfoot>`.
* **Accessibility:** Column headers mapped via `<th scope="col">` and row headers via `<th scope="row">`.
* **Styling & Usability:** Clean green tint header (`var(--color-primary-surface)`), row hover highlights, formatted currency tags, and an outer `.table-responsive-wrapper` with `-webkit-overflow-scrolling: touch` ensuring zero horizontal viewport breakage on mobile screens.

### 3.4 Complete Form Audit (`tickets.html`)
* **Form Attributes:** `<form action="#" method="post" class="booking-form" novalidate>`.
* **Controls & Inputs:**
  * Full Name: `<input type="text" autocomplete="name" required>`
  * Email Address: `<input type="email" autocomplete="email" required>`
  * Phone Number: `<input type="tel" pattern="[0-9+() -]{7,20}" autocomplete="tel" required>`
  * Visit Date: `<input type="date" required>`
  * Ticket Quantity: `<input type="number" min="1" max="50" value="1" required>`
  * Primary Bio-Zone: `<select required>` with disabled prompt option and 5 options
  * Special Requests: `<textarea>` with accessible placeholder
  * Submission: `<button type="submit" class="btn btn-primary btn-form-submit">`
* **Accessibility:** Every input explicitly linked to `<label for="...">` with visible required asterisks and `.form-helper` descriptions.

### 3.5 Media Elements Audit
* **Images (`<img>`):** Featured animal of the month (`index.html`), 6 high-resolution resident species cards (`animals.html`). All specify descriptive `alt` tags and `loading="lazy"`.
* **Native Video (`<video>`):** Features `controls`, `preload="metadata"`, `poster` image, nested `<source type="video/mp4">`, and fallback text with download link (`animals.html`).
* **Native Audio (`<audio>`):** Features `controls`, `preload="none"`, `aria-label`, `<source type="audio/mpeg">`, and fallback text (`animals.html`).
* **Interactive Map (`<iframe>`):** Responsive 16:9 Google Maps embed on `tickets.html` with `loading="lazy"`, `title`, and `referrerpolicy="no-referrer-when-downgrade"`.
* **Document Embed (`<embed>`):** Digital park visitor PDF guide on `animals.html` with `type="application/pdf"`, `title`, and external view fallback.

---

## 4. Responsive Design & Layout Verification

### 4.1 CSS Flexbox Behavior
* **Header & Navigation:** Mobile stacks logo and links vertically for easy tapping; desktop (`min-width: 769px`) transitions seamlessly to horizontal space-between alignment.
* **Form Controls:** Stacks vertically on mobile; splits into 2-column flex rows (`.form-row-2col`) on viewports `> 768px`.
* **Animal Cards:** Card internal layout utilizes flex column direction with `flex-grow: 1` on body descriptions to ensure uniform card heights across uneven text lengths.
* **Footer:** Stacks to single column on mobile; distributes into 3 columns on desktop.

### 4.2 CSS Grid Behavior
* **Home Page Layout (`index.html`):** Single column on mobile; desktop splits into a `2fr 1fr` grid pairing the main highlights column with the daily keeper talks aside.
* **Wildlife Gallery (`animals.html`):** Uses modern responsive fluid auto-fitting:  
  `grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));`  
  Naturally reflows from 1 column on phone viewports to 2 and 3 columns on tablet and desktop screens without media query bloat.
* **Multimedia Section (`animals.html`):** 1 column on mobile; transforms to 3 equal columns (`repeat(3, 1fr)`) on desktop.

---

## 5. Bugs Detected & Corrections Applied

During the initial inspection, automated linter tests identified 37 issues (consisting of disallowed inline `style="..."` attributes and minor trailing whitespace). The following corrections were directly implemented:

1. **Extraction of Inline Styles to CSS Classes:**
   * **In `Project1/css/style.css`**: Added clean utility and component classes:
     * `.gallery-title`: Centralized title typography and primary branding color.
     * `.gallery-subtitle`: Centered subtitle with max-width and balanced margins.
     * `.article-heading-spaced`: Standardized top margin for featured article titles.
     * `.text-subtle` & `.text-subtle-sm`: Consistent muted caption typography.
     * `.mt-xs`, `.mt-sm`, `.mt-md`, `.mt-lg`, `.mb-xs`: Design-token-aligned margin spacing utilities.
     * `.btn-form-submit`: Minimum width rule for booking button.
     * `.fallback-text-spaced`: Top margin rule for media fallback descriptions.
   * **In `Project1/animals.html`**: Replaced all inline styles on headings, subtitles, and media captions with the corresponding CSS classes.
   * **In `Project1/index.html`**: Replaced inline margins and font styles on paragraphs, headings, and aside lists with CSS classes.
   * **In `Project1/tickets.html`**: Replaced inline margins on tip wrappers, submit buttons, and map links with CSS classes.
2. **Whitespace Normalization:**
   * Cleaned trailing whitespace across all HTML documents to guarantee compliance with standard formatting rules.
3. **Re-Validation Verification:**
   * Executed `html-validate` post-correction: **0 errors, 0 warnings**.

---

## 6. QA Sign-Off

The Zoo Static Website meets all functional, structural, accessibility, and visual responsive specifications outlined in the project documentation. All files are corrected, verified, and production-ready.

