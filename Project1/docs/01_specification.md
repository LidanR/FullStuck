# Project Specification: Zoo Static Website

## 1. Project Overview & Target Audience

### 1.1 Project Overview
This project is an academic, static multi-page website (pure HTML5 and CSS3) for a modern zoological park and wildlife conservation center. The site aims to provide essential visitor information, showcase animal species and habitats, promote educational engagement, and facilitate ticket booking inquiries.

### 1.2 Target Audience & Primary User Scenarios
* **Scenario A: Families with Children**
  * **Goal:** Plan a safe, entertaining, and educational family day trip.
  * **Journey:** Visits the homepage (`index.html`) to check today's opening hours and key highlights -> Navigates to `animals.html` to find family-favorite exhibits and kid-friendly feeding schedules -> Moves to `tickets.html` to review bundle pricing (family discounts) and submits a ticket booking inquiry via the form.
* **Scenario B: Solo Visitors & Wildlife Enthusiasts**
  * **Goal:** Explore specific habitats, watch educational multimedia, and check directions.
  * **Journey:** Arrives on `animals.html` to study conservation programs, watch the featured animal behavior video, and review animal facts -> Navigates to `tickets.html` to inspect general admission rates and view the zoo's transit/map location.

---

## 2. 3-Page Website Structure

| Page | Filename | Key Sections & Features |
| :--- | :--- | :--- |
| **Home** | `index.html` | - Hero banner with welcome tagline and primary CTA<br>- Zoo highlights & conservation pillars<br>- Operating schedule & real-time daily opening hours<br>- Quick sidebar announcement (`<aside>`) for seasonal events |
| **Animals & Habitats** | `animals.html` | - Overview of global zoo bio-zones (Savannah, Rainforest, Arctic)<br>- Animal cards gallery with taxonomy, status, and facts<br>- Featured educational video with native HTML5 media controls<br>- Quick-fact lists for species |
| **Tickets & Planning** | `tickets.html` | - Structured admission pricing table (Adult, Child, Senior, Family pass)<br>- Interactive visit reservation/inquiry form with validation fields<br>- Zoo directions, transit guide, and embedded map/location overview |

---

## 3. Wireframes & Semantic Layout (`index.html`)

The layout strictly uses semantic HTML5 elements to structure content cleanly for accessibility and search engine optimization.

```text
+--------------------------------------------------------------------------+
|  <header>                                                                |
|    +-----------------------------+  <nav>                                |
|    | [Logo] City Zoo Sanctuary   |    [Home]  [Animals]  [Tickets & Visit]|
|    +-----------------------------+  </nav>                               |
+--------------------------------------------------------------------------+
|  <main>                                                                  |
|    +------------------------------------------------------------------+  |
|    | <section id="hero">                                              |  |
|    |   <h1>Discover Wildlife, Support Conservation</h1>               |  |
|    |   <p>Explore over 300 species in natural habitats.</p>           |  |
|    |   <a href="tickets.html" class="btn">Book Your Visit</a>         |  |
|    | </section>                                                       |  |
|    +-------------------------------------------------+----------------+  |
|    | <section id="highlights">                       | <aside>        |  |
|    |   <h2>Zoo Highlights</h2>                       |  <h3>Daily     |  |
|    |   +-----------------------+ +-----------------+ |  Schedule</h3> |  |
|    |   | <article>             | | <article>       | |  <ul>          |  |
|    |   |   <h3>Savannah Walk</h3>|   <h3>Rainforest</h3>| |   <li>Hours</li>|
|    |   |   <p>Guided safari...</p>   <p>Canopy tour</p>| |   <li>Show</li> |
|    |   | </article>            | | </article>      | |  </ul>         |  |
|    |   +-----------------------+ +-----------------+ | </aside>       |  |
|    | </section>                                      |                |  |
|    +-------------------------------------------------+----------------+  |
|    | <section id="hours-info">                                        |  |
|    |   <h2>General Admission & Hours</h2>                             |  |
|    |   <p>Open daily 09:00 - 18:00 (Last entry at 17:00)</p>          |  |
|    | </section>                                                       |  |
|  </main>                                                                 |
+--------------------------------------------------------------------------+
|  <footer>                                                                |
|    <p>&copy; 2026 City Zoo Sanctuary. All rights reserved.             |
|    <address>124 Safari Way, Green Valley | contact@cityzoo.org</address> |
+--------------------------------------------------------------------------+
```

---

## 4. Requirements Mapping Checklist

This checklist tracks where every required HTML element category is implemented across the 3 pages:

- [x] **Hyperlinks (`<a>`):**
  - Global site navigation links in `<nav>` (`index.html`, `animals.html`, `tickets.html`).
  - Hero call-to-action button linking from `index.html` to `tickets.html`.
  - External links to conservation partners in `<footer>` (`all pages`).
  - Anchor jump links to specific habitat sections (`animals.html`).

- [x] **Lists (`<ul>`, `<ol>`, `<dl>`):**
  - Unordered list (`<ul>`) for header navigation menu (`all pages`).
  - Unordered list (`<ul>`) for daily events/feeding times (`index.html`).
  - Definition list (`<dl>`) or bullet list (`<ul>`) for animal taxonomy, diet, and lifespan facts (`animals.html`).
  - Ordered list (`<ol>`) for "How to Plan Your Visit" steps (`tickets.html`).

- [x] **Tables (`<table>`):**
  - Structured pricing table with `<thead>`, `<tbody>`, `<th>`, `<tr>`, and `<td>` for ticket tiers (Adult, Child, Senior, Group rates) on `tickets.html`.

- [x] **Forms (`<form>`):**
  - Contact and ticket reservation booking form on `tickets.html` containing:
    - `<input type="text">` (Full Name)
    - `<input type="email">` (Email address)
    - `<input type="date">` (Visit Date)
    - `<select>` with `<option>` (Ticket Category/Count)
    - `<textarea>` (Special accessibility requests / inquiries)
    - `<button type="submit">` (Submit Booking Inquiry)

- [x] **Media Elements (`<img>`, `<video>`, `<iframe>`):**
  - `<img>`: Zoo logo in header, hero image on `index.html`, animal photography grid cards on `animals.html`.
  - `<video>`: Featured native HTML5 video with `controls`, `<source>`, and fallback text on `animals.html`.
  - `<iframe>` or responsive vector map image: Interactive/styled map location for zoo directions on `tickets.html`.
