# Project 1: Zoo Website - Specifications

## Overview
A static multi-page website for a city zoo (HTML5 & CSS3).
The site has 3 pages:
1. `index.html` - Homepage with general information, daily hours, keeper talks and highlights.
2. `animals.html` - Animal cards gallery with species info, habitat video and sounds.
3. `tickets.html` - Admission prices table, reservation form and Google map.

---

## Page Breakdown

### 1. Home (`index.html`)
- Header with site logo and navigation links.
- About section introducing the zoo and its conservation work.
- Featured "Animal of the Month" card (Lion).
- Opening hours section with a schedule list.
- Sidebar (`<aside>`) with quick facts and keeper talks times.
- Footer with site links and contact info.

### 2. Animals & Habitats (`animals.html`)
- Header and navigation.
- Species gallery using CSS Grid (Lion, Bush Elephant, Penguin, Red Panda, Dart Frog, Giraffe).
  - Each card has an image, status badge, scientific name, short description and a link to Wikipedia.
- Media section:
  - Video player (featured lion clip).
  - Audio player (savannah sounds).
  - Visitor guide PDF embed.
- Footer.

### 3. Tickets & Visit (`tickets.html`)
- Header and navigation.
- Pricing table with columns for category, age, weekday/weekend price and perks.
- Visit tips ordered list.
- Booking/inquiry form:
  - Name, email, phone.
  - Visit date picker.
  - Number of tickets.
  - Habitat selection dropdown.
  - Special requests textarea.
  - Submit button.
- Location map embed (Google Maps iframe).
- Footer.

---

## Technical Checklist
- Semantic HTML tags: `header`, `nav`, `main`, `section`, `article`, `aside`, `footer`.
- At least 3 internal links per page (nav links + CTAs).
- At least 3 external links per page (WWF, IUCN, Wikipedia).
- Unordered (`<ul>`) and ordered (`<ol>`) lists.
- Styled table with `thead`, `tbody`, `tfoot`, `th`, `td`.
- Form with multiple input types (`text`, `email`, `tel`, `date`, `number`, `select`, `textarea`).
- Media tags: `img`, `iframe`, `audio`, `embed`.
- Responsive design: CSS Flexbox for nav/form, CSS Grid for animal cards and desktop layout.
