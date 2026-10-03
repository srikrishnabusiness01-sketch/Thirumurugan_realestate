---
name: playwright-cli
description: >
  Test, screenshot, and validate the Thirumurugan Real Estate
  website using Playwright CLI. Use this skill to capture
  screenshots of built pages, test responsiveness across
  devices, verify animations, and validate all links and forms.
triggers:
  - "test the website"
  - "take a screenshot"
  - "check responsiveness"
  - "validate the page"
  - "playwright"
  - "does it look right"
  - "check mobile view"
---

# Playwright CLI Skill — Thirumurugan Real Estate

## What Playwright Does Here
- Takes screenshots of built HTML files
- Tests across desktop, tablet, mobile viewports
- Validates that all sections render correctly
- Checks hover states and animations
- Verifies form functionality
- Catches layout bugs before delivery

## Installation
```bash
npm init -y
npm install -D @playwright/test
npx playwright install chromium
```

## Basic Screenshot Command
```bash
npx playwright screenshot --browser chromium \
  --viewport-size "1440,900" \
  index.html \
  screenshots/desktop.png
```

## Viewport Sizes for Testing

### Desktop
- Wide: 1920 x 1080
- Standard: 1440 x 900
- Small desktop: 1280 x 800

### Tablet
- iPad Pro: 1024 x 1366
- iPad: 768 x 1024

### Mobile
- iPhone 14 Pro: 393 x 852
- iPhone SE: 375 x 667
- Android: 360 x 800

## Screenshot Script for All Viewports
```javascript
// playwright-screenshots.js
const { chromium } = require('@playwright/test');
const path = require('path');

const viewports = [
  { name: 'desktop-wide', width: 1920, height: 1080 },
  { name: 'desktop', width: 1440, height: 900 },
  { name: 'tablet', width: 768, height: 1024 },
  { name: 'mobile', width: 393, height: 852 },
];

(async () => {
  const browser = await chromium.launch();

  for (const vp of viewports) {
    const page = await browser.newPage();
    await page.setViewportSize({ width: vp.width, height: vp.height });
    await page.goto(`file://${path.resolve('index.html')}`);
    await page.waitForTimeout(1000);
    await page.screenshot({
      path: `screenshots/${vp.name}.png`,
      fullPage: true
    });
    console.log(`Screenshot saved: ${vp.name}.png`);
    await page.close();
  }

  await browser.close();
})();
```

Run with:
```bash
node playwright-screenshots.js
```

## Section Screenshot Script
```javascript
// screenshot each section individually
const sections = [
  { selector: 'nav', name: 'navigation' },
  { selector: '#hero', name: 'hero' },
  { selector: '#about', name: 'about' },
  { selector: '#properties', name: 'properties' },
  { selector: '#map', name: 'map' },
  { selector: '#contact', name: 'contact' },
  { selector: 'footer', name: 'footer' },
];

for (const section of sections) {
  const el = await page.$(section.selector);
  if (el) {
    await el.screenshot({ path: `screenshots/section-${section.name}.png` });
  }
}
```

## Hover State Testing
```javascript
// Test card hover states
const cards = await page.$$('.property-card');
for (let i = 0; i < cards.length; i++) {
  await cards[i].hover();
  await page.waitForTimeout(500);
  await page.screenshot({ path: `screenshots/card-hover-${i}.png` });
}

// Test button hover
const btn = await page.$('.btn-primary');
await btn.hover();
await page.screenshot({ path: 'screenshots/btn-hover.png' });
```

## Navigation Test
```javascript
// Test sticky nav on scroll
await page.goto(`file://${path.resolve('index.html')}`);
await page.screenshot({ path: 'screenshots/nav-top.png' });
await page.evaluate(() => window.scrollTo(0, 300));
await page.waitForTimeout(500);
await page.screenshot({ path: 'screenshots/nav-scrolled.png' });
```

## Form Validation Test
```javascript
// Test enquiry form
await page.fill('input[name="name"]', 'Test User');
await page.fill('input[name="phone"]', '9999999999');
await page.fill('textarea[name="message"]', 'Interested in properties');
await page.screenshot({ path: 'screenshots/form-filled.png' });
await page.click('button[type="submit"]');
await page.waitForTimeout(1000);
await page.screenshot({ path: 'screenshots/form-submitted.png' });
```

## Animation Check
```javascript
// Scroll through entire page capturing sections
await page.goto(`file://${path.resolve('index.html')}`);
const totalHeight = await page.evaluate(() => document.body.scrollHeight);
const step = 500;
let currentPos = 0;
let frameNum = 0;

while (currentPos < totalHeight) {
  await page.evaluate(pos => window.scrollTo(0, pos), currentPos);
  await page.waitForTimeout(300);
  await page.screenshot({ path: `screenshots/scroll-${frameNum}.png` });
  currentPos += step;
  frameNum++;
}
```

## Quality Checklist After Screenshots
- [ ] Hero fills full viewport on all sizes
- [ ] Navigation is visible and correct on scroll
- [ ] Property cards display correctly in grid
- [ ] Cards stack properly on mobile
- [ ] Map section renders
- [ ] Contact form is accessible on mobile
- [ ] Footer renders completely
- [ ] No horizontal scroll on mobile
- [ ] Text is readable on all backgrounds
- [ ] Gold accents are visible throughout

## Common Issues & Fixes

### Fonts not loading in screenshots
Add wait before screenshot:
```javascript
await page.waitForLoadState('networkidle');
```

### Animations not visible
Disable reduced motion in test:
```javascript
await page.emulateMedia({ reducedMotion: 'no-preference' });
```

### Three.js canvas black
Add longer wait:
```javascript
await page.waitForTimeout(3000);
```

## Output Folder Structure
```
Thiru_real_estate/
└── screenshots/
    ├── desktop-wide.png
    ├── desktop.png
    ├── tablet.png
    ├── mobile.png
    ├── nav-top.png
    ├── nav-scrolled.png
    ├── section-hero.png
    ├── section-properties.png
    ├── section-contact.png
    └── card-hover-0.png
```
