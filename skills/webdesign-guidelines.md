---
name: webdesign-guidelines
description: >
  Layout, structure, responsiveness, and component guidelines
  for building Thirumurugan Real Estate website. Apply this
  skill for every section, component, and page layout decision.
triggers:
  - "build a website"
  - "create a section"
  - "design layout"
  - "responsive"
  - "component"
  - "real estate website"
---

# Webdesign Guidelines — Thirumurugan Real Estate

## Page Structure — Section Order
1. Navigation (sticky, transparent → solid on scroll)
2. Hero (fullscreen, 3D or cinematic background)
3. About / Brand Identity
4. Properties Showcase
5. Why Choose Us (Trust signals)
6. Interactive Map
7. Testimonials (optional)
8. Contact / Enquiry
9. Footer

## Navigation Rules
- Logo: left aligned — "Thirumurugan Real Estate" in Cormorant Garamond
- Links: right aligned — About, Properties, Map, Contact
- Default state: transparent background, white text
- Scrolled state: background #0A0A0F, gold bottom border 1px #C9A84C
- Mobile: hamburger menu, full screen overlay
- Height: 72px desktop, 60px mobile
- No dropdown menus in prototype

## Hero Section Rules
- Height: 100vh minimum
- Background: Three.js 3D terrain OR dark cinematic gradient
- Headline: max 6 words, Cormorant Garamond, 72px desktop / 40px mobile
- Subheadline: max 12 words, Inter, 18px, muted gold color
- CTA Button: "Explore Properties" — gold border, transparent fill
- Scroll indicator: animated chevron at bottom center

## Property Card Rules
- Size: 380px wide desktop, full width mobile
- Image area: 240px height, dark overlay on hover
- Content area: padding 24px
- Show: Property name, location, size, status badge, price
- Status badge colors:
  - Available: #1A6B3C background, #4ADE80 text
  - Sold: #6B1A1A background, #F87171 text
  - Reserved: #6B5A1A background, #FCD34D text
- Hover: card lifts 8px, gold border appears
- CTA: "View Details" text link with arrow

## Section Layout Patterns

### Two Column (About, Features)
- Left: 55% content
- Right: 45% visual
- Gap: 80px
- Stack to single column below 768px

### Three Column (Property Grid)
- Equal width columns
- Gap: 32px
- Stack to 2 col at 1024px
- Stack to 1 col at 640px

### Full Width (Hero, Map, CTA Banner)
- No max-width constraint
- Content inside max-width 1200px container

## Typography Scale
- Display (hero headline): 72px / line-height 1.1
- H1: 56px / line-height 1.15
- H2: 40px / line-height 1.2
- H3: 28px / line-height 1.3
- H4: 20px / line-height 1.4
- Body large: 18px / line-height 1.7
- Body: 16px / line-height 1.7
- Small / Caption: 13px / line-height 1.5
- Label / Badge: 11px / line-height 1

## Button Styles
### Primary Button
- Border: 1px solid #C9A84C
- Background: transparent
- Text: #C9A84C, Inter, 14px, letter-spacing 0.08em
- Padding: 14px 32px
- Hover: background #C9A84C, text #0A0A0F
- Transition: 0.3s ease

### Secondary Button
- Border: 1px solid #2A2A38
- Background: #111118
- Text: #F0EDE6
- Padding: 14px 32px
- Hover: border-color #C9A84C

## Form / Enquiry Rules
- Input background: #111118
- Input border: 1px solid #2A2A38
- Input focus border: #C9A84C
- Label: 12px, #8A8799, uppercase, letter-spacing 0.1em
- Fields needed: Name, Phone, Message, Property Interest
- Submit button: Primary button style
- WhatsApp CTA alongside form

## Footer Rules
- Background: #060609
- Top border: 1px solid #2A2A38
- Three columns: Brand info, Quick links, Contact
- Copyright: centered, 13px, muted
- Social icons: Instagram, Facebook (if available)

## Responsive Breakpoints
- Mobile: 0 - 639px
- Tablet: 640px - 1023px
- Desktop: 1024px - 1279px
- Wide: 1280px+

## Performance Rules
- Lazy load all images
- Three.js canvas: pause when not in viewport
- No more than 3 external font weights loaded
- GSAP: load only used modules
- Total page load target: under 3 seconds

## Accessibility Rules
- All images: meaningful alt text
- Color contrast: WCAG AA minimum
- Focus states: visible gold outline
- Keyboard navigation: fully supported
- Reduced motion: respect prefers-reduced-motion

## Z-Index Scale
- Base content: 1
- Cards on hover: 10
- Sticky nav: 100
- Mobile menu overlay: 200
- Modal / popup: 300
