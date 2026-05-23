# Divine Creative Solution — Landing Page

A modern, premium, single-file corporate landing page. No build tools, no dependencies, no frameworks — just open `index.html` in a browser or deploy it anywhere.

---

## Quick Start

```bash
git clone https://github.com/YOUR_USERNAME/divine-creative-solution.git
cd divine-creative-solution
open index.html        # macOS
# or just drag index.html into any browser
```

To deploy: upload `index.html` to any static host — **GitHub Pages**, **Netlify**, **Vercel**, or any web server.

---

## File Structure

```
divine-creative-solution/
├── index.html       ← entire site (HTML + CSS + JS in one file)
├── README.md        ← this file
└── assets/          ← put your images here (e.g. leader photo)
```

> All styling lives in the `<style>` block at the top of `index.html`.  
> All content lives in the `<body>` — each section is clearly commented.

---

## Customization Guide

### 1. Brand Colors

Open `index.html` and find the `:root` block near the top (~line 22). Change any value:

```css
:root {
  --vulcan:       #130f1e;  /* page background (darkest) */
  --purple-heart: #6438da;  /* primary accent — buttons, highlights */
  --purple-light: #7c52e8;  /* hover state for primary accent */
  --gray-suit:    #c7c0d4;  /* subtitle / secondary text */
  --gunsmoke:     #848c8a;  /* body / muted text */
  --white:        #ffffff;  /* headings, foreground text */
}
```

**Example — swap to a teal accent:**
```css
--purple-heart: #0ea5a0;
--purple-light: #14c4be;
```

---

### 2. Typography

Fonts are defined in the first `<style>` block (~line 9):

```css
:root {
  --font-title:    'Helvetica Neue', Helvetica, Arial, sans-serif;
  --font-subtitle: 'Helvetica Neue', Helvetica, Arial, sans-serif;
  --font-body:     'Montserrat', sans-serif;
  --fw-heavy: 900;   /* display titles */
  --fw-bold:  700;   /* subtitles, labels */
  --fw-light: 300;   /* body text */
}
```

To use a Google Font instead, add its `<link>` tag in `<head>` and update the variable:

```html
<!-- In <head> -->
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&display=swap" rel="stylesheet">
```
```css
--font-title: 'Playfair Display', serif;
```

---

### 3. Company Name & Nav Logo

Search for `Divine` in the file. The nav logo is at ~line 958:

```html
<a href="#" class="nav-logo">Divine<span>.</span></a>
```

The `<span>` wraps the accent dot — it uses `--purple-heart`. Change or remove it as needed.

---

### 4. Hero Section

Find `<!-- HERO -->` in the HTML:

```html
<!-- Eyebrow label -->
<p class="hero-eyebrow">Creative &amp; Strategic Development Partner</p>

<!-- Main display title -->
<h1 class="hero-title">
  Divine<br><span class="accent">Creative</span><br>Solution
</h1>

<!-- Subtitle -->
<p class="hero-subtitle">Creative Excellence Meets Operational Maturity</p>

<!-- Description paragraph -->
<p class="hero-desc">
  We combine creative excellence...
</p>

<!-- CTA buttons -->
<a href="#cta" class="btn-primary">Get in Touch</a>
<a href="#services" class="btn-secondary">Explore Our Services</a>
```

**Stats strip** (below the buttons):
```html
<div class="hero-stat">
  <div class="hero-stat-num">10<span>+</span></div>
  <div class="hero-stat-label">Years Experience</div>
</div>
```
Edit the number and label text for each of the three stats. The `<span>` inside `.hero-stat-num` renders in purple.

---

### 5. Core Takeaways — Three Pillars

Find `<!-- CORE TAKEAWAYS -->`. Each pillar follows this pattern:

```html
<div class="pillar reveal reveal-delay-1">
  <div class="pillar-num">01</div>
  <div class="pillar-title">What We Offer</div>
  <p class="pillar-text">Your description here.</p>
</div>
```

To **add a 4th pillar**, duplicate a `<div class="pillar">` block and add `reveal-delay-4`. Note: the grid is `grid-template-columns: repeat(3, 1fr)` — change to `repeat(4, 1fr)` in the CSS `.pillars-grid` rule for a 4-column layout.

---

### 6. Services List

Find `<!-- SERVICES -->`. Each service item:

```html
<div class="service-item reveal reveal-delay-1">
  <span class="service-num">01</span>
  <div class="service-info">
    <div class="service-name">Concept Development</div>
    <p class="service-text">Description of the service.</p>
  </div>
</div>
```

Add or remove `<div class="service-item">` blocks as needed. Update the `reveal-delay-N` class for stagger timing (delay-1 through delay-4 are defined; add more in CSS if needed).

**Service card tags** (the floating card on the right):
```html
<div class="sc-tags">
  <span class="sc-tag">Storytelling</span>
  <span class="sc-tag">Strategy</span>
  <!-- add/remove tags here -->
</div>
```

---

### 7. Why Us Section

Find `<!-- WHY US -->`. The big background text, quote, and bullet points:

```html
<!-- Giant background text (decorative) -->
<div class="why-bg-text">Why us?</div>

<!-- Italic pull quote -->
<p class="why-quote">
  "Your quote here."
</p>

<!-- Bullet points -->
<div class="why-point">
  <div class="why-point-dot"></div>
  <span class="why-point-text">Your point here</span>
</div>
```

---

### 8. Leadership Profile

Find `<!-- LEADERSHIP -->`.

**Photo:** Replace the `src` with your image path:
```html
<img src="assets/your-photo.jpg" alt="Name — Title" class="leader-img">
```
Place your image in the `assets/` folder. The photo renders in **grayscale** by default via CSS (`filter: grayscale(100%)`). To show it in color:
```css
.leader-img { filter: none; }
```

**Name and role:**
```html
<div class="leader-name">Taufika (Fika)</div>
<div class="leader-role">Senior Finance Manager · Chief Executive Officer</div>
```

**Achievement grid** — each cell is:
```html
<div class="achievement-item">
  <p class="achievement-text">Your achievement here</p>
</div>
```
The grid is 2 columns (`grid-template-columns: 1fr 1fr`). Add pairs of items to keep it balanced.

**Certifications:**
```html
<span class="cert-tag">Finance</span>
```
Add or remove `<span class="cert-tag">` elements freely.

---

### 9. Strategic Summary

Find `<!-- STRATEGIC SUMMARY -->`. Each strength item:

```html
<div class="strength-item reveal reveal-delay-1">
  <div class="strength-icon">
    <svg viewBox="0 0 24 24">
      <path d="M9 12l2 2 4-4M21 12a9 9 0 11-18 0 9 9 0 0118 0z"/>
    </svg>
  </div>
  <div>
    <div class="strength-title">Strong Financial Governance</div>
    <p class="strength-text">Description.</p>
  </div>
</div>
```

Icons use inline SVG stroke paths (stroke-only, no fill). You can swap in any Heroicons or similar outline SVG path.

**Stat blocks:**
```html
<div class="summary-stat-val">10+</div>
<div class="summary-stat-label">Years Financial Leadership</div>
```

---

### 10. CTA Section

Find `<!-- CTA -->`:

```html
<h2 class="cta-title">Work<br>With Us</h2>
<p class="cta-desc">Your call-to-action description.</p>

<a href="mailto:hello@yourcompany.com" class="btn-primary">Contact Us</a>
<a href="#summary" class="btn-secondary">View Company Profile</a>
<a href="#leadership" class="btn-secondary">Meet the Team</a>
```

Update the `href="mailto:..."` with your real email address.

---

### 11. Footer

```html
<div class="footer-brand">Divine<span>Creative</span> Solution</div>
<div class="footer-copy">© 2025 Divine Creative Solution. All rights reserved.</div>
```

Update the year and company name. The `<span>` in `.footer-brand` renders in purple.

---

### 12. Nav Links

```html
<ul class="nav-links">
  <li><a href="#takeaways">About</a></li>
  <li><a href="#services">Services</a></li>
  <li><a href="#why-us">Why Us</a></li>
  <li><a href="#leadership">Team</a></li>
  <li><a href="#cta" class="nav-cta">Get in Touch</a></li>
</ul>
```

Each `href` is an anchor ID matching a `<section id="...">` further down the page. Add new nav items by adding new `<li>` entries and a corresponding `<section id="your-id">`.

---

## Scroll Animations

Every element with the class `reveal` fades up when scrolled into view. This is powered by a small IntersectionObserver at the bottom of the file.

- `reveal` — base fade-up animation
- `reveal-delay-1` through `reveal-delay-4` — stagger delays (0.1s–0.4s)

Add `reveal` to any element to give it the scroll-in effect. Add a `reveal-delay-N` class to control its timing within a group.

---

## Deployment

| Platform | Steps |
|---|---|
| **GitHub Pages** | Push repo → Settings → Pages → Source: `main` branch, `/ (root)` |
| **Netlify** | Drag & drop the `divine-creative-solution/` folder onto netlify.com/drop |
| **Vercel** | `npx vercel` in the project folder |
| **Any web host** | Upload `index.html` (and `assets/` if used) via FTP/SFTP |

---

## Browser Support

Chrome, Firefox, Safari, Edge — all modern versions. No polyfills needed.

---

## License

MIT — use freely, modify freely, ship freely.
