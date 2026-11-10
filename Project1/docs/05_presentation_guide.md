# 5-Minute Presentation Plan

Format: 2-person walkthrough (Partner A & Partner B).
Time: ~5 minutes total.

---

## Roles & Timeline

### 1. Home Page & Structure (0:00 - 1:30) - Partner A
- **What to show on screen:**
  - Open `index.html` in browser.
  - Open DevTools (F12) and quickly point out semantic tags: `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`.
  - Show the hero section, "Animal of the Month" article, and the aside block with the talks schedule.
- **Talking points:**
  - "We built a 3-page static zoo website using pure HTML5 and CSS3 without any external JS libraries."
  - "We focused on semantic structure: distinct sections, an article for featured content, an aside for quick facts, and accessible navigation."
  - "Notice all external links open securely with `rel='noopener noreferrer'`."

### 2. Responsiveness & DevTools (1:30 - 2:30) - Partner B
- **What to show on screen:**
  - Toggle device toolbar (`Ctrl+Shift+M`) to mobile view (e.g. 375px).
  - Scroll down the mobile homepage.
  - Slowly drag the screen width wider past 768px.
- **Talking points:**
  - "The site is built mobile-first. On small screens, everything flows into a clean single column so it's easy to read on mobile."
  - "The header switches from vertical on mobile to horizontal on desktop."
  - "At 769px, CSS Grid kicks in and splits the home page into 2 columns: main highlights on the left and the aside on the right."

### 3. Animals Page & Grid (2:30 - 3:30) - Partner A
- **What to show on screen:**
  - Click on "Animals" in the nav.
  - Scroll through the animal cards.
  - Resize the window slightly to show cards wrapping.
  - Scroll down to the media section: show the lion video, hit play on the audio player, and show the embedded PDF.
- **Talking points:**
  - "On the animals page, the card gallery uses CSS Grid with `repeat(auto-fit, minmax(280px, 1fr))`."
  - "This means the cards rearrange automatically based on available width without needing fixed breakpoints."
  - "For media, we included a YouTube video embed in a 16:9 container, a native audio player with nature sounds, and an embedded PDF visitor guide."

### 4. Tickets Page, Table & Form (3:30 - 4:30) - Partner B
- **What to show on screen:**
  - Click "Tickets" in the nav.
  - Show the pricing table.
  - Toggle mobile view to show the table scrolls horizontally without breaking the screen layout.
  - Scroll down to the reservation form.
  - Click "Confirm Reservation" empty to trigger browser validation. Fill in sample inputs.
  - Show the Google Maps embed at the bottom.
- **Talking points:**
  - "On tickets.html, we have our admission table with proper `thead`, `tbody`, `tfoot` and `scope` attributes for accessibility."
  - "On mobile, the table is wrapped in an overflow container so it scrolls horizontally without stretching the page."
  - "The booking form uses semantic inputs like `date`, `tel`, `email`, a dropdown, and pattern validation. Every input has a matching label."
  - "At the bottom is an interactive Google Maps iframe."

### 5. CSS & QA Summary (4:30 - 5:00) - Both
- **Partner A:**
  - "For styling, we used `variables.css` for consistent colors, fonts, and spacing. Added subtle hover transitions on buttons and cards."
- **Partner B:**
  - "We tested all pages with `html-validate` and checked mobile viewports. Everything passed with 0 errors. Thanks for listening!"
