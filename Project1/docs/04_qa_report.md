# QA & Testing Report

Project: Zoo Static Website
Tested by: Team
Files tested: `index.html`, `animals.html`, `tickets.html`, `css/style.css`, `css/variables.css`

---

## 1. Requirements Check

| Requirement | Where it is | Status |
| :--- | :--- | :--- |
| Semantic HTML | `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>` across all pages | Pass |
| Internal links (>= 3) | Nav links, buttons, footer links on all 3 pages | Pass |
| External links (>= 3) | WWF, IUCN Red List, Wikipedia links on all 3 pages | Pass |
| Lists (`ul`, `ol`) | Nav menus, opening hours, quick facts, daily talks schedule, visit tips | Pass |
| Table | Admission pricing table with `thead`, `tbody`, `tfoot`, `th scope`, responsive wrapper | Pass |
| Form | Ticket booking form with name, email, phone, date, quantity, select, textarea, submit | Pass |
| Media elements | Images with alt tags, YouTube video embed, native audio player, PDF embed, Google map | Pass |
| Responsive design | Mobile-first, flexbox nav/form, CSS grid for cards and 2-column home layout | Pass |

---

## 2. Issues Found & Fixed During Testing

1. **Inline styles**:
   - Problem: Had some inline styles in `style="..."` in the HTML files.
   - Fix: Moved them to CSS classes in `css/style.css` (`.gallery-title`, `.gallery-subtitle`, spacing utility classes).

2. **PDF embed cross-origin issue**:
   - Problem: The test PDF from w3.org was blocked by browser security (CORS) and showed a blank/broken icon.
   - Fix: Created a local PDF (`media/documents/visitor-guide.pdf`) and linked to it directly.

3. **Video embed update**:
   - Updated the sample video to the African Lion YouTube clip with responsive 16:9 iframe styling.

4. **Footer simplification**:
   - Cleaned up the footer across all 3 pages so it is clean, centered, and easy to read while keeping all required external and internal links.

5. **HTML Validation**:
   - Tested all 3 HTML files with `html-validate`.
   - Result: 0 errors, 0 warnings.
