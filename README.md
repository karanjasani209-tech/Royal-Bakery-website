# ✦ Royal Bakery — Premium Luxury Website

A production-ready, ultra-high-definition luxury bakery website built with vanilla HTML/CSS/JS, Three.js, and GSAP. No build tools required — drop the file on any static host and it runs.

---

## ✨ Features

### 3D & Visual
- **Three.js Hero Scene** — Atmospheric dark background with warm gold point lights, a fully procedural 3D multi-tier rotating cake, and 1,200 animated "flour particle" system
- **Interactive 3D Story Panel** — A second Three.js scene in the About section with a mouse-parallax rotating cake
- **4K Retina-Ready** — `devicePixelRatio`-aware renderer (`Math.min(devicePixelRatio, 2)`), fluid `clamp()` typography, SVG-level CSS icons
- **Flame animation** — Flickering point light on the candle using sinusoidal intensity oscillation

### Animations
- **GSAP ScrollTrigger** — Staggered scroll reveals on every section
- **Hero entrance timeline** — Orchestrated text cascade on page load
- **Elastic cake scale-in** — Three.js cake scales in with a spring physics ease
- **CSS marquee strip** — Continuous looping philosophy ticker
- **60fps transitions** — All CSS transitions use `cubic-bezier(0.16, 1, 0.3, 1)` for buttery smoothness

### Interactivity
- **Custom magnetic cursor** — Dot + elastic ring cursor, enlarges on hover
- **Hover Zoom Lens** — Magnifying glass follows the mouse over menu items, revealing "microscopic detail"
- **Category tabs** — Instant animated switching between Sourdough / Pastries / Custom Cakes / Seasonal
- **Live Order Summary** — Order panel updates in real time as user selects item, quantity, and delivery method
- **Toast notifications** — Gold confirmation toasts on Add to Order

### Pages
| Page | Key Content |
|------|------------|
| **Home** | Hero 3D scene, philosophy marquee, story section with 3D cake, featured items grid |
| **Services** | 4-service grid with animated gold border reveals, 4-step process timeline |
| **Menu** | Filterable grid (4 categories, 10+ items), hover zoom lens on every product |
| **Order** | Full order form with live summary panel, item picker, quantity stepper |

---

## 🚀 Getting Started

### Zero-dependency deployment
```bash
# Clone or download
git clone https://github.com/yourusername/royal-bakery.git

# Open directly in browser — no build step needed
open index.html
```

### Deploy to Netlify (recommended)
```bash
# Drag & drop the folder to netlify.com/drop
# Or via CLI:
netlify deploy --dir . --prod
```

### Deploy to GitHub Pages
1. Push to a GitHub repo
2. Go to **Settings → Pages → Source: main / root**
3. Done — live in 60 seconds

---

## 📦 CDN Dependencies

All external libraries are loaded via CDN — no npm install required:

```html
<!-- Three.js r128 — 3D rendering -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>

<!-- GSAP 3.12 — Animations -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollToPlugin.min.js"></script>

<!-- Google Fonts — Cormorant Garamond + Jost -->
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond...&family=Jost...&display=swap" />
```

---

## 🎨 Design System

All design tokens live in CSS custom properties at the top of the `<style>` block. Change these to retheme the entire site instantly:

```css
:root {
  --gold:        #C9A84C;   /* Primary accent */
  --gold-light:  #E8C97A;   /* Hover state */
  --gold-dark:   #8B6914;   /* Pressed state */
  --cream:       #FAF5EB;   /* Body text, headings */
  --charcoal:    #1A1612;   /* Background */
  --charcoal-mid:#2D2620;   /* Card backgrounds */

  --font-display: 'Cormorant Garamond'; /* All headings */
  --font-body:    'Jost';               /* UI text */
}
```

---

## 🗂️ Code Structure

```
index.html
├── <head>
│   ├── CDN links (Three.js, GSAP, Google Fonts)
│   └── <style>
│       ├── CSS Variables (design tokens)
│       ├── Reset & Base
│       ├── Custom Cursor
│       ├── Navigation
│       ├── Home Page styles
│       ├── Services Page styles
│       ├── Menu Page styles
│       ├── Order Page styles
│       └── Footer & Utilities
│
├── <body>
│   ├── #page-loader
│   ├── #cursor-dot + #cursor-ring
│   ├── <nav>
│   ├── #page-home (Home)
│   ├── #page-services (Services)
│   ├── #page-menu (Menu)
│   ├── #page-order (Order)
│   └── <script>
│       ├── 1. Custom Cursor logic
│       ├── 2. Page switching system
│       ├── 3. Three.js Hero Scene
│       ├── 4. Three.js Story Scene
│       ├── 5. GSAP animations
│       ├── 6. Menu tabs + zoom lens
│       └── 7. Order form logic
```

---

## 🛠️ Customisation Guide

### Swap product images
Find the `background-image: url(...)` lines in the menu item and featured card sections and replace with your own CDN-hosted images. For 4K sharpness, use images at minimum **1200×900px**.

### Add real order handling
In the `submitOrder()` function (bottom of `<script>`), replace the toast with a real API call:
```javascript
// Example: Netlify Forms
fetch('/', {
  method: 'POST',
  headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
  body: new URLSearchParams({ 'form-name': 'order', name: fn, email, item: orderState.item })
});
```

### Add new menu items
Duplicate any `.menu-item` block inside the relevant `#cat-XXX` div and update the image URL, name, description, and price.

### Change brand colours
Edit the `:root` CSS variables block at the very top of the `<style>` tag.

---

## 📱 Responsive Breakpoints

| Breakpoint | Layout Changes |
|-----------|---------------|
| `< 900px` | Single-column story section, services stack vertically, nav links hidden |
| `< 600px` | Single-column featured grid, form stacks, footer single column |

Mobile nav expansion (hamburger menu) can be added by toggling a class on `.nav-links`.

---

## ✦ Credits

- **Three.js** — [threejs.org](https://threejs.org)
- **GSAP** — [greensock.com](https://greensock.com)
- **Product photography** — [Unsplash](https://unsplash.com)
- **Fonts** — Google Fonts (Cormorant Garamond, Jost)

---

*Royal Bakery © 2024 — Built with flour & code.*
