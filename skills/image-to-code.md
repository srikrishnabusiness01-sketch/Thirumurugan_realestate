---
name: image-to-code
description: >
  Convert reference screenshots, design mockups, or inspiration
  images into clean production-ready HTML/CSS/JS code for
  Thirumurugan Real Estate website. Apply when a visual reference
  is provided and needs to be translated into code.
triggers:
  - "convert this image"
  - "replicate this design"
  - "build this from screenshot"
  - "match this layout"
  - "code this design"
  - "make it look like this"
---

# Image to Code Skill — Thirumurugan Real Estate

## Core Process
When given a reference image or screenshot:
1. Analyze the layout structure first
2. Identify the grid system being used
3. Extract colors and map to our brand palette
4. Identify typography hierarchy
5. Note all interactive elements
6. Build mobile-first, then scale up

## Layout Analysis Steps

### Step 1 — Identify Structure
- How many columns?
- What is the header/hero treatment?
- Where is the navigation?
- What sections exist top to bottom?

### Step 2 — Extract Visual Tokens
- Background colors → map to our palette
- Text colors → map to our palette
- Border colors → map to our palette
- Spacing rhythm → convert to our scale

### Step 3 — Component Inventory
List every component visible:
- Navigation bar
- Hero section
- Cards
- Buttons
- Forms
- Icons
- Dividers

## Color Mapping Rules
When extracting colors from reference images,
always remap to Thirumurugan brand palette:

| Reference Color Type | Map To |
|---------------------|--------|
| Any dark background | #0A0A0F or #111118 |
| Any gold/yellow accent | #C9A84C |
| Any light text | #F0EDE6 |
| Any muted text | #8A8799 |
| Any border/divider | #2A2A38 |
| Any card background | #111118 |

## Typography Mapping Rules
| Reference Font Type | Use |
|--------------------|-----|
| Serif display/headline | Cormorant Garamond |
| Sans body text | Inter |
| Any monospace | DM Mono (only for data) |

## Code Output Standards

### HTML Structure
- Use semantic HTML5 elements
- section, article, nav, header, footer, main
- BEM naming convention for classes
- Data attributes for JS hooks (data-animate, data-counter)

### CSS Standards
- CSS custom properties for all tokens
- Mobile first media queries
- No !important unless overriding third party
- Group properties: positioning, box model, typography, visual

### CSS Custom Properties to Always Include
```css
:root {
  --color-bg-primary: #0A0A0F;
  --color-bg-surface: #111118;
  --color-bg-deep: #060609;
  --color-accent-gold: #C9A84C;
  --color-accent-gold-light: #E8D5A3;
  --color-text-primary: #F0EDE6;
  --color-text-muted: #8A8799;
  --color-border: #2A2A38;
  --font-display: 'Cormorant Garamond', Georgia, serif;
  --font-body: 'Inter', system-ui, sans-serif;
  --transition-base: 0.3s ease;
  --transition-slow: 0.6s cubic-bezier(0.25, 0.46, 0.45, 0.94);
  --radius-card: 4px;
  --radius-button: 2px;
  --max-width: 1200px;
  --padding-section: clamp(60px, 10vw, 120px);
}
```

### JavaScript Standards
- Vanilla JS preferred over jQuery
- IntersectionObserver for scroll animations
- Event delegation for dynamic content
- No inline event handlers in HTML

## Component Code Templates

### Scroll Reveal Animation
```javascript
const revealElements = document.querySelectorAll('[data-animate]');
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('is-visible');
      observer.unobserve(entry.target);
    }
  });
}, { threshold: 0.2 });
revealElements.forEach(el => observer.observe(el));
```

### Counter Animation
```javascript
function animateCounter(el) {
  const target = parseInt(el.dataset.target);
  const duration = 2000;
  const start = performance.now();
  const update = (time) => {
    const elapsed = time - start;
    const progress = Math.min(elapsed / duration, 1);
    const eased = 1 - Math.pow(1 - progress, 4);
    el.textContent = Math.floor(eased * target);
    if (progress < 1) requestAnimationFrame(update);
    else el.textContent = target + (el.dataset.suffix || '');
  };
  requestAnimationFrame(update);
}
```

### Sticky Nav on Scroll
```javascript
const nav = document.querySelector('.nav');
window.addEventListener('scroll', () => {
  nav.classList.toggle('nav--scrolled', window.scrollY > 50);
});
```

## Quality Checks After Building
- [ ] Does the output match the reference layout?
- [ ] Are brand colors applied (not reference colors)?
- [ ] Is it responsive on mobile?
- [ ] Are hover states working?
- [ ] Are animations smooth?
- [ ] Is the code clean and readable?

## What NOT to Copy from References
- Colors (always remap to brand palette)
- Generic stock photos (use placeholders)
- Competitor brand names or logos
- Any non-premium design patterns
