---
name: awesome-design-md
description: >
  Design pattern references, component inspiration, and visual
  language guide for Thirumurugan Real Estate website. Use this
  skill when deciding how to style specific components, sections,
  or interactions. Contains proven premium patterns from top
  luxury real estate and architecture websites.
triggers:
  - "design pattern"
  - "component style"
  - "how should this look"
  - "inspiration"
  - "reference"
  - "hero design"
  - "property card"
  - "luxury website"
---

# Awesome Design Reference — Thirumurugan Real Estate

## Hero Section Patterns

### Pattern 1 — Cinematic Text Reveal (RECOMMENDED)
- Full dark background or 3D canvas
- Large serif headline fades in word by word
- Thin gold horizontal line animates left to right
- Subtext fades in after headline
- Single CTA button appears last
- Reference feel: Zaha Hadid Architects homepage

### Pattern 2 — Split Screen Hero
- Left 60%: dark background with headline + CTA
- Right 40%: property image with gold frame border
- Diagonal divider between sections
- Reference feel: luxury penthouse websites

### Pattern 3 — Full 3D Terrain (ADVANCED)
- Three.js wireframe terrain fills entire viewport
- Gold wireframe color on dark background
- Headline overlaid with blur backdrop
- Camera slowly pans / rotates
- Reference feel: bruno-simon.com style

## Property Card Patterns

### Pattern 1 — Magazine Card (RECOMMENDED)
```
┌─────────────────────────┐
│                         │
│      PROPERTY IMAGE     │
│         240px           │
│                         │
│  [AVAILABLE] badge      │
├─────────────────────────┤
│ Property Name           │
│ Location · Size         │
│                         │
│ ₹ Price or Contact      │
│                         │
│ View Details →          │
└─────────────────────────┘
```
- Image has dark gradient overlay bottom
- Badge positioned top-left on image
- Clean minimal typography inside card
- Gold accent on hover border

### Pattern 2 — Horizontal Card (for featured property)
```
┌──────────────┬──────────────────────────┐
│              │ FEATURED PROPERTY        │
│    IMAGE     │ Location · Size          │
│    400px     │                          │
│              │ Description 2 lines max  │
│              │                          │
│              │ ₹ Price    [Enquire Now] │
└──────────────┴──────────────────────────┘
```
- Used for hero property or top listing
- Gold "FEATURED" label top left

## Navigation Patterns

### Minimal Luxury Nav (RECOMMENDED)
```
[TR Logo]                    About  Properties  Map  Contact  [Enquire]
```
- Logo uses initials "TR" in gold circle + full name
- Links spaced 40px apart
- Right-most item is gold CTA button
- On scroll: backdrop blur + dark background

### Mobile Nav Pattern
- Hamburger icon top right
- Full screen overlay slides in from right
- Links stacked centered, large 32px font
- Gold close button top right
- Social links at bottom of overlay

## About Section Patterns

### Pattern 1 — Legacy Statement (RECOMMENDED)
```
┌─────────────────────┬───────────────────┐
│                     │                   │
│  "Decades of trust  │   Proprietor      │
│   in Tamil Nadu     │   Photo or        │
│   land ownership"   │   Abstract Visual │
│                     │                   │
│  Bio paragraph      │                   │
│                     │                   │
│  3 stat counters    │                   │
│  Years · Plots · ₹  │                   │
└─────────────────────┴───────────────────┘
```
- Stats animate count-up on scroll into view
- Gold divider line between stat items

## Trust Signal Patterns

### Stats Counter Bar
```
┌──────────────────────────────────────────────┐
│   15+          50+          100%             │
│   Years        Properties   Clear Title      │
│   Experience   Sold         Guarantee        │
└──────────────────────────────────────────────┘
```
- Dark background section
- Gold numbers, white labels
- Thin vertical gold dividers between items
- Numbers count up when scrolled into view

### Trust Badge Row
- RERA Registered
- Legal Verified
- Clear Title Properties
- Direct Owner (No Broker)

## Map Section Patterns

### Interactive Property Map
- Full width section, 500px height
- Dark map style (Mapbox dark theme)
- Gold pin markers for each property
- Click pin: popup card with property details
- Zoom controls styled in gold

## Contact Section Patterns

### Split Contact (RECOMMENDED)
```
┌──────────────────────┬───────────────────────┐
│                      │                       │
│  Get In Touch        │   [ Enquiry Form ]    │
│                      │                       │
│  📞 Phone number     │   Name ____________   │
│  💬 WhatsApp         │   Phone ___________   │
│  📧 Email            │   Interest _________  │
│  📍 Address          │   Message __________  │
│                      │                       │
│  [WhatsApp Button]   │   [ Send Enquiry ]    │
└──────────────────────┴───────────────────────┘
```

## Animation Patterns

### Scroll Reveal (Apply to all sections)
```
Initial state:  opacity: 0, translateY: 40px
Final state:    opacity: 1, translateY: 0
Duration:       0.7s
Easing:         cubic-bezier(0.25, 0.46, 0.45, 0.94)
Trigger:        when 20% of element is visible
Stagger:        0.15s between child elements
```

### Gold Line Reveal (Section dividers)
```
Initial state:  width: 0
Final state:    width: 60px
Duration:       0.8s
Easing:         ease-out
Color:          #C9A84C
```

### Number Counter Animation
```
Duration: 2000ms
Easing: easeOutQuart
Trigger: IntersectionObserver threshold 0.5
```

## Micro Interaction Patterns

### Button Hover
- Background fills gold from left to right
- Text color transitions dark
- Duration: 0.3s

### Card Hover
- Translate Y: -8px
- Box shadow: 0 20px 60px rgba(201, 168, 76, 0.15)
- Border: 1px solid #C9A84C
- Duration: 0.3s ease

### Link Hover
- Gold underline grows from left
- Width: 0 → 100%
- Duration: 0.25s

## Section Divider Patterns
- Never use full horizontal rules
- Use: short 60px gold line centered
- Or: decorative diamond in gold
- Or: just generous whitespace (preferred)

## Image Treatment Patterns
- All property images: object-fit cover
- Aspect ratio: 16:9 for cards, 4:3 for featured
- Dark overlay: linear-gradient(
    to bottom,
    rgba(0,0,0,0) 40%,
    rgba(0,0,0,0.7) 100%
  )
- On hover: overlay lightens slightly

## Footer Pattern
```
┌─────────────────────────────────────────────┐
│  [TR Logo]                                  │
│  Thirumurugan Real Estate                   │
│  Trusted land proprietor since [year]       │
│                                             │
│  Quick Links    Properties    Contact       │
│  About          Plot 1        Phone         │
│  Properties     Plot 2        Email         │
│  Map            Plot 3        Location      │
│  Contact                                    │
│                                             │
│  ─────────────────────────────────────────  │
│  © 2024 Thirumurugan Real Estate            │
└─────────────────────────────────────────────┘
```

## Color Usage by Component
| Component          | Background  | Text      | Accent    |
|--------------------|-------------|-----------|-----------|
| Nav (default)      | transparent | #F0EDE6   | #C9A84C   |
| Nav (scrolled)     | #0A0A0F     | #F0EDE6   | #C9A84C   |
| Hero               | #0A0A0F     | #F0EDE6   | #C9A84C   |
| About              | #0D0D14     | #F0EDE6   | #E8D5A3   |
| Property cards     | #111118     | #F0EDE6   | #C9A84C   |
| Stats bar          | #0A0A0F     | #C9A84C   | #F0EDE6   |
| Map section        | #0D0D14     | #F0EDE6   | #C9A84C   |
| Contact            | #111118     | #F0EDE6   | #C9A84C   |
| Footer             | #060609     | #8A8799   | #C9A84C   |
