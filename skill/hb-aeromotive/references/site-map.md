# HB Aeromotive — Site Map

Full structural reference for `index.html`.

## Table of Contents
1. [Nav Bar](#nav-bar)
2. [Hero](#hero)
3. [Inventory](#inventory)
4. [About](#about)
5. [Contact](#contact)
6. [Footer](#footer)

---

## Nav Bar
```html
<header class="nav-bar">
  <div class="nav-inner">
    <a class="logo" href="/">
      <span class="logo-hb">HB</span><span class="logo-aero">Aeromotive</span>
    </a>
    <nav>
      <a href="#inventory">Inventory</a>
      <a href="#about">About</a>
      <a href="#contact">Contact</a>
    </nav>
  </div>
</header>
```
- Logo color: `--accent` (gold) for "HB", white for "Aeromotive"
- Nav links: add/remove `<a href="#section-id">Label</a>` to match any new sections

---

## Hero
```html
<section class="hero">
  <div class="hero-content">
    <h1>Built to Fly.</h1>
    <p class="hero-sub">Tagline here.</p>
    <a class="btn-primary" href="#inventory">Browse Inventory</a>
  </div>
  <div class="hero-art" aria-hidden="true">
    <!-- SVG plane silhouette — edit or replace freely -->
  </div>
</section>
```
- `h1` and `hero-sub` are the primary marketing copy — update freely
- `btn-primary` CTA can change label and target

---

## Inventory
```html
<section class="section" id="inventory">
  <div class="container">
    <h2>Current Inventory</h2>
    <p class="section-sub">Intro sentence.</p>
    <div class="card-grid">
      <!-- card × N -->
      <div class="card">
        <div class="card-icon">✈️</div>
        <h3>Category</h3>
        <p>Description.</p>
      </div>
    </div>
  </div>
</section>
```
- `.card-grid` uses CSS `auto-fill` — any number of cards lays out naturally
- Current cards: ARF/RTF Kits ✈️, Engines & Motors ⚙️, Electronics & ESCs 🔋, Parts & Hardware 🛠️

---

## About
```html
<section class="section section-alt" id="about">
  <div class="container about-grid">
    <div class="about-text">
      <h2>About HB Aeromotive</h2>
      <p>Bio paragraph 1.</p>
      <p>Bio paragraph 2.</p>
      <p>Bio paragraph 3.</p>
    </div>
    <div class="about-badge">
      <div class="badge-circle">
        <span class="badge-hb">HB</span>
        <span class="badge-tagline">Decades of<br/>Flying Experience</span>
      </div>
    </div>
  </div>
</section>
```
- `badge-tagline` text can be updated (2 short lines)
- Add a photo: replace `.about-badge` contents with `<img>` styled `border-radius: 50%`

---

## Contact
```html
<section class="section" id="contact">
  <div class="container contact-block">
    <h2>Get in Touch</h2>
    <p>Intro sentence.</p>
    <div class="contact-details">
      <div class="contact-item">
        <span class="contact-label">Email</span>
        <a href="mailto:harold@hb-aeromotive.com">harold@hb-aeromotive.com</a>
      </div>
      <div class="contact-item">
        <span class="contact-label">Location</span>
        <span>Nebraska, USA</span>
      </div>
    </div>
    <p class="contact-note">Closing note.</p>
  </div>
</section>
```
- Add a phone `.contact-item` the same way as email/location
- `.contact-label` is the left-aligned bold label; right side is any inline element

---

## Footer
```html
<footer class="footer">
  <div class="container">
    <p>&copy; 2026 HB Aeromotive. All rights reserved.</p>
  </div>
</footer>
```
- Update year as needed
