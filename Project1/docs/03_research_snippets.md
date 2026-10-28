# Research Snippets: HTML5 & CSS3 Best Practice Patterns

This document provides clean, standard-compliant, copy-paste-ready HTML5 and CSS3 patterns for the Zoo Static Website. All patterns follow W3C web standards, accessibility principles (WCAG 2.1), and modern responsive design conventions.

---

## 1. Semantic Document Boilerplate

A standard-compliant HTML5 boilerplate featuring proper encoding, viewport configuration for mobile readiness, SEO meta tags, favicon reference, and semantic landmark elements (`<header>`, `<nav>`, `<main>`, `<section>`, `<aside>`, `<footer>`).

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  
  <title>City Zoo Sanctuary | Wildlife Discovery & Conservation</title>
  <meta name="description" content="Explore natural wildlife habitats, meet over 300 animal species, and support active global conservation programs at City Zoo Sanctuary.">
  
  <!-- CSS Stylesheets -->
  <link rel="stylesheet" href="css/variables.css">
  <link rel="stylesheet" href="css/layout.css">
  <link rel="stylesheet" href="css/components.css">
</head>
<body>
  <!-- Header Landmark -->
  <header class="site-header">
    <div class="header-container">
      <a href="index.html" class="brand-logo" aria-label="City Zoo Sanctuary Home">
        <span class="logo-mark">🌿</span>
        <span class="logo-text">City Zoo Sanctuary</span>
      </a>

      <!-- Primary Navigation Landmark -->
      <nav class="site-nav" aria-label="Main Navigation">
        <ul class="nav-list">
          <li><a href="index.html" class="nav-link active" aria-current="page">Home</a></li>
          <li><a href="animals.html" class="nav-link">Animals &amp; Habitats</a></li>
          <li><a href="tickets.html" class="nav-link">Tickets &amp; Visit</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <!-- Main Content Landmark (Only one per page) -->
  <main id="main-content" class="site-main">
    <!-- Hero / Intro Section -->
    <section class="hero-section" aria-labelledby="hero-title">
      <h1 id="hero-title">Discover Wildlife, Protect the Future</h1>
      <p>Immerse yourself in nature across our world-class educational habitats.</p>
      <a href="tickets.html" class="btn btn-primary">Plan Your Visit</a>
    </section>

    <!-- Layout Container with Aside Landmark -->
    <div class="content-layout-wrapper">
      <section class="main-feature" aria-labelledby="features-title">
        <h2 id="features-title">Featured Highlights</h2>
        <p>Experience guided safari walks and habitat tours.</p>
      </section>

      <!-- Complementary Landmark -->
      <aside class="sidebar-schedule" aria-labelledby="schedule-title">
        <h3 id="schedule-title">Today's Feeding Times</h3>
        <ul>
          <li><strong>10:30 AM:</strong> Penguin Feeding</li>
          <li><strong>02:00 PM:</strong> Savannah Predator Talk</li>
        </ul>
      </aside>
    </div>
  </main>

  <!-- Footer Landmark -->
  <footer class="site-footer">
    <div class="footer-container">
      <p>&copy; 2026 City Zoo Sanctuary. All rights reserved.</p>
      <address>
        124 Safari Way, Green Valley &bull;
        <a href="mailto:contact@cityzoo.org">contact@cityzoo.org</a>
      </address>
    </div>
  </footer>
</body>
</html>
```

---

## 2. Responsive Flexbox Navbar

A responsive navigation header utilizing CSS Flexbox. It renders horizontally with distributed spacing on desktop displays and stacks cleanly into an accessible, centered column layout on viewports `768px` or narrower.

### HTML Structure
```html
<header class="site-header">
  <div class="nav-wrapper">
    <a href="index.html" class="nav-brand">
      <span class="brand-icon" aria-hidden="true">🐾</span>
      <span class="brand-name">City Zoo</span>
    </a>

    <nav class="main-nav" aria-label="Primary Site Navigation">
      <ul class="nav-menu">
        <li class="nav-item"><a href="index.html" class="nav-link">Home</a></li>
        <li class="nav-item"><a href="animals.html" class="nav-link">Animals</a></li>
        <li class="nav-item"><a href="tickets.html" class="nav-link">Tickets &amp; Hours</a></li>
      </ul>
    </nav>
  </div>
</header>
```

### CSS Implementation
```css
/* Base Mobile-First Styles (Stacked Navigation) */
.site-header {
  background-color: var(--color-bg-surface, #ffffff);
  border-bottom: 1px solid var(--color-border-subtle, #e2e5df);
  padding: 0.75rem 1rem;
}

.nav-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
}

.nav-brand {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  text-decoration: none;
  font-weight: 700;
  font-size: 1.25rem;
  color: var(--color-primary, #2d6a4f);
}

.main-nav {
  width: 100%;
}

.nav-menu {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
  width: 100%;
}

.nav-item {
  width: 100%;
  text-align: center;
}

.nav-link {
  display: block;
  padding: 0.625rem 1rem;
  color: var(--color-text-main, #1f2421);
  text-decoration: none;
  font-weight: 500;
  border-radius: 4px;
  transition: background-color 0.2s ease, color 0.2s ease;
}

.nav-link:hover,
.nav-link:focus-visible {
  background-color: var(--color-primary-light, #d8f3dc);
  color: var(--color-primary, #2d6a4f);
}

/* Desktop Breakpoint (> 768px): Horizontal Flex Layout */
@media (min-width: 769px) {
  .site-header {
    padding: 1rem 1.5rem;
  }

  .nav-wrapper {
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }

  .main-nav {
    width: auto;
  }

  .nav-menu {
    flex-direction: row;
    gap: 1rem;
    width: auto;
  }

  .nav-item {
    width: auto;
  }

  .nav-link {
    display: inline-block;
  }
}
```

---

## 3. Responsive CSS Grid for Animal Cards

An auto-fitting responsive CSS Grid layout that naturally scales from 1 column on mobile to 2, 3, or more columns on wider viewports without requiring rigid media query overrides. Includes cards with structured semantic content, badge tags, and image aspect ratio handling.

### HTML Structure
```html
<section class="gallery-section" aria-labelledby="gallery-heading">
  <h2 id="gallery-heading">Featured Resident Species</h2>

  <div class="animal-grid">
    <!-- Animal Card 1 -->
    <article class="animal-card">
      <div class="card-media">
        <img src="media/images/lion.jpg" alt="African Lion resting on a rock outcrop" loading="lazy">
        <span class="status-badge status-vulnerable">Vulnerable</span>
      </div>
      <div class="card-body">
        <h3 class="species-title">African Lion</h3>
        <p class="species-taxonomy"><em>Panthera leo</em> &bull; African Savannah</p>
        <p class="species-desc">Apex social predators that live in family prides and communicate via powerful roars.</p>
        <ul class="species-facts">
          <li><strong>Diet:</strong> Carnivore</li>
          <li><strong>Lifespan:</strong> 12–16 years</li>
        </ul>
      </div>
    </article>

    <!-- Animal Card 2 -->
    <article class="animal-card">
      <div class="card-media">
        <img src="media/images/elephant.jpg" alt="African Bush Elephant walking near waterhole" loading="lazy">
        <span class="status-badge status-endangered">Endangered</span>
      </div>
      <div class="card-body">
        <h3 class="species-title">African Elephant</h3>
        <p class="species-taxonomy"><em>Loxodonta africana</em> &bull; Savannah &amp; Forest</p>
        <p class="species-desc">Earth's largest land mammal, renowned for exceptional intelligence, memory, and social bonds.</p>
        <ul class="species-facts">
          <li><strong>Diet:</strong> Herbivore</li>
          <li><strong>Lifespan:</strong> 60–70 years</li>
        </ul>
      </div>
    </article>

    <!-- Animal Card 3 -->
    <article class="animal-card">
      <div class="card-media">
        <img src="media/images/penguin.jpg" alt="Humboldt Penguin perched on coast" loading="lazy">
        <span class="status-badge status-vulnerable">Vulnerable</span>
      </div>
      <div class="card-body">
        <h3 class="species-title">Humboldt Penguin</h3>
        <p class="species-taxonomy"><em>Spheniscus humboldti</em> &bull; Coastal Marine</p>
        <p class="species-desc">Medium-sized penguins adapted for rapid swimming and hunting small fish in cold currents.</p>
        <ul class="species-facts">
          <li><strong>Diet:</strong> Piscivore</li>
          <li><strong>Lifespan:</strong> 15–20 years</li>
        </ul>
      </div>
    </article>
  </div>
</section>
```

### CSS Implementation
```css
/* Responsive Grid with Clean Gap Management */
.animal-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: var(--space-lg, 1.5rem);
  padding: 1rem 0;
}

/* Card Presentation & Architecture */
.animal-card {
  display: flex;
  flex-direction: column;
  background-color: var(--color-bg-surface, #ffffff);
  border: 1px solid var(--color-border-subtle, #e2e5df);
  border-radius: var(--radius-md, 8px);
  overflow: hidden;
  box-shadow: var(--shadow-sm, 0 1px 3px rgba(0, 0, 0, 0.08));
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.animal-card:hover {
  transform: translateY(-4px);
  box-shadow: var(--shadow-md, 0 4px 12px rgba(0, 0, 0, 0.12));
}

.card-media {
  position: relative;
  width: 100%;
  aspect-ratio: 16 / 10;
  overflow: hidden;
  background-color: var(--color-bg-muted, #f2f3ee);
}

.card-media img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.status-badge {
  position: absolute;
  top: 0.75rem;
  right: 0.75rem;
  padding: 0.25rem 0.625rem;
  font-size: 0.75rem;
  font-weight: 600;
  border-radius: 9999px;
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

.status-vulnerable {
  background-color: #fef3c7;
  color: #92400e;
}

.status-endangered {
  background-color: #fee2e2;
  color: #991b1b;
}

.card-body {
  display: flex;
  flex-direction: column;
  flex-grow: 1;
  padding: 1.25rem;
}

.species-title {
  margin: 0 0 0.25rem 0;
  font-size: 1.25rem;
  color: var(--color-text-main, #1f2421);
}

.species-taxonomy {
  margin: 0 0 0.75rem 0;
  font-size: 0.875rem;
  color: var(--color-text-muted, #525c56);
}

.species-desc {
  margin: 0 0 1rem 0;
  font-size: 0.95rem;
  line-height: 1.5;
  color: var(--color-text-main, #1f2421);
  flex-grow: 1;
}

.species-facts {
  list-style: none;
  padding: 0.75rem 0 0 0;
  margin: 0;
  border-top: 1px solid var(--color-border-subtle, #e2e5df);
  display: flex;
  justify-content: space-between;
  font-size: 0.85rem;
  color: var(--color-text-muted, #525c56);
}
```

---

## 4. Media Embed Best Practices

Standard-compliant syntax patterns for native HTML5 video and audio players with fallbacks, a responsive embedded interactive map using `<iframe>`, and an external document/resource view using `<embed>`.

### 4.1 Native Video Embed (`<video controls>`)
Includes format fallbacks (`MP4` and `WebM`), a poster frame, accessible subtitles via `<track>`, and explicit fallback content for legacy browsers.

```html
<figure class="media-container video-frame">
  <video
    controls
    preload="metadata"
    poster="media/images/hero-banner.jpg"
    width="800"
    height="450"
    aria-label="Wildlife Conservation in Action documentary clip"
  >
    <source src="media/video/animal-behavior.mp4" type="video/mp4">
    <source src="media/video/animal-behavior.webm" type="video/webm">
    <track 
      src="media/video/captions-en.vtt" 
      kind="subtitles" 
      srclang="en" 
      label="English Subtitles"
      default
    >
    <p>
      Your browser does not support native HTML5 video.
      You can <a href="media/video/animal-behavior.mp4" download>download the wildlife video</a> instead.
    </p>
  </video>
  <figcaption>Watch our resident species engage in daily natural enrichment activities.</figcaption>
</figure>
```

### 4.2 Native Audio Embed (`<audio controls>`)
Includes multi-format sources (`MP3` and `OGG`) and descriptive captioning.

```html
<figure class="media-container audio-frame">
  <figcaption id="audio-caption">Listen: Dawn Chorus in the Rainforest Bio-Zone</figcaption>
  <audio 
    controls 
    preload="none"
    aria-labelledby="audio-caption"
  >
    <source src="media/audio/rainforest-ambience.mp3" type="audio/mpeg">
    <source src="media/audio/rainforest-ambience.ogg" type="audio/ogg">
    <p>
      Your browser does not support the audio element.
      <a href="media/audio/rainforest-ambience.mp3" download>Download the audio recording</a>.
    </p>
  </audio>
</figure>
```

### 4.3 Responsive Embedded Map (`<iframe loading="lazy">`)
Features lazy loading, security sandboxing/permissions policy, accessible title attribute, and a CSS container preserving an exact aspect ratio without layout shift.

```html
<div class="map-embed-wrapper">
  <iframe
    src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3151.835434509374!2d144.9537353153166!3d-37.81627977975171!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x0!2zMzfCsDQ4JzU4LjYiUyAxNDTCsDU3JzEzLjQiRQ!5e0!3m2!1sen!2sus!4v1614000000000"
    title="City Zoo Sanctuary Location Map & Directions"
    width="600"
    height="450"
    style="border:0;"
    allowfullscreen=""
    loading="lazy"
    referrerpolicy="no-referrer-when-downgrade"
  ></iframe>
</div>
```

### 4.4 External Resource / Document Embed (`<embed>`)
Demonstrates how to embed an external interactive PDF document (such as a printable Zoo Visitor Map) with type declaration and fallback handling.

```html
<section class="document-embed-section" aria-labelledby="map-pdf-heading">
  <h3 id="map-pdf-heading">Downloadable Park Map Guide</h3>
  <div class="embed-document-wrapper">
    <embed
      src="media/documents/zoo-visitor-guide.pdf"
      type="application/pdf"
      width="100%"
      height="500px"
      title="Zoo Visitor Map and Guide (PDF)"
    >
  </div>
  <p class="embed-fallback-note">
    Unable to view PDF directly in your browser? 
    <a href="media/documents/zoo-visitor-guide.pdf" download class="download-link">Download Zoo Map (PDF)</a>.
  </p>
</section>
```

### 4.5 Media CSS Helper Rules
```css
/* Responsive Video & Media Container */
.media-container {
  margin: 1.5rem 0;
  width: 100%;
}

.media-container video {
  width: 100%;
  max-width: 100%;
  height: auto;
  border-radius: var(--radius-md, 8px);
  background-color: #000000;
  box-shadow: var(--shadow-sm, 0 1px 3px rgba(0,0,0,0.1));
}

.media-container figcaption {
  margin-top: 0.5rem;
  font-size: 0.875rem;
  color: var(--color-text-muted, #525c56);
  font-style: italic;
}

/* Audio Player */
.audio-frame audio {
  width: 100%;
  margin-top: 0.5rem;
}

/* Aspect-Ratio Preserving Map Wrapper */
.map-embed-wrapper {
  position: relative;
  width: 100%;
  aspect-ratio: 16 / 9;
  border-radius: var(--radius-md, 8px);
  overflow: hidden;
  box-shadow: var(--shadow-sm, 0 1px 3px rgba(0,0,0,0.1));
}

.map-embed-wrapper iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

/* PDF Embed Wrapper */
.embed-document-wrapper {
  width: 100%;
  border: 1px solid var(--color-border-subtle, #e2e5df);
  border-radius: var(--radius-md, 8px);
  overflow: hidden;
}
```
