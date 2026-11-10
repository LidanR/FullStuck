# Reference Code Snippets & Notes

Quick reference snippets used during the project development.

## 1. Page Template
Basic semantic skeleton used for each page:
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Page Title</title>
  <link rel="stylesheet" href="css/style.css">
</head>
<body>
  <header class="site-header">
    <div class="container navbar-container">
      <a href="index.html" class="brand-link">City Zoo Sanctuary</a>
      <nav class="site-nav">
        <ul class="nav-menu">
          <li><a href="index.html">Home</a></li>
          <li><a href="animals.html">Animals</a></li>
          <li><a href="tickets.html">Tickets</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <main class="site-main">
    <!-- Page Content -->
  </main>

  <footer class="site-footer">
    <!-- Footer Links -->
  </footer>
</body>
</html>
```

## 2. Responsive Card Grid
Used on `animals.html` for the animal cards:
```css
.gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 1.5rem;
}
```

## 3. Responsive Table Wrapper
Wrapping table in a div to prevent horizontal scroll issues on mobile:
```html
<div class="table-responsive-wrapper">
  <table class="pricing-table">
    <!-- content -->
  </table>
</div>
```
```css
.table-responsive-wrapper {
  width: 100%;
  overflow-x: auto;
  -webkit-overflow-scrolling: touch;
}
```

## 4. Video & Map 16:9 Aspect Ratio
Using modern CSS `aspect-ratio` to avoid layout shifts:
```css
.video-container, .map-iframe-container {
  width: 100%;
  aspect-ratio: 16 / 9;
}
.video-container iframe, .map-iframe-container iframe {
  width: 100%;
  height: 100%;
  border: 0;
}
```
