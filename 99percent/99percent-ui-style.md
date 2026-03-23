# 99% Off Sale UI Style Guide

> Design system extracted from [99percentoffsale.com](https://www.99percentoffsale.com/) — Cards Against Humanity's Black Friday 2024 campaign site.

---

## Overview

A **maximally reduced, high-contrast, confrontational** design that uses only two colors (red + white), zero border-radius, zero shadows, and ultra-bold condensed type. The aesthetic is aggressive retail — think clearance warehouse signage meets punk zine. Every design choice screams "sale" as loudly as possible.

**Key Characteristics:**
- Strictly 2-color palette: `#FF0000` red + `#FFFFFF` white — nothing else
- Condensed bold (900) Helvetica for all display text
- Zero border-radius, zero box-shadow, zero gradients — pure flat
- Giant scrolling marquee text (124px) as section dividers
- Product cards alternate flex-direction (row / row-reverse) for visual rhythm
- Stickers as absolute-positioned badges on product images
- Intentionally chaotic, loud, "everything must go" energy

---

## Color Palette

The entire site uses exactly **two colors**. No grays, no opacity variations, no secondary palette.

| Name | Hex | RGB | Usage |
|------|-----|-----|-------|
| **Red** | `#FF0000` | `rgb(255, 0, 0)` | Page background, button text, FAQ text, border color on white |
| **White** | `#FFFFFF` | `rgb(255, 255, 255)` | Text, buttons, cards, borders, FAQ background |
| **Black** | `#000000` | `rgb(0, 0, 0)` | Pagination dots only (border + active fill) |

CSS variables:
```css
--red: #FF0000;
--white: #ffffff;
--black: #000000;
--foreground: var(--white);   /* Swapped in FAQ section */
--background: var(--red);     /* Swapped in FAQ section */
```

### Color Roles by Context

| Context | Background | Text | Border |
|---------|------------|------|--------|
| **Main page (red sections)** | Red | White | White |
| **FAQ section (inverted)** | White | Red | Red |
| **Buttons ("Sold Out")** | White | Red | `1px solid red` |
| **Product card borders** | — | — | `1px solid white` |
| **Pagination dots** | White / Black (active) | — | `2px solid black` |
| **Strikethrough prices** | — | White | — |
| **Links** | — | White (underline) | — |

> There is no dark mode, no hover color change, no disabled state colors. The palette is absolute.

---

## Typography

### Font Families

Three-font system via CSS custom properties:

| Font | CSS Variable | Type | Role | Fallback |
|------|-------------|------|------|----------|
| **Helvetica Neue LT Pro Cond** | `--font-helvetica-cond` | Condensed sans-serif | All display text: headings, product names, prices, buttons | Arial, sans-serif |
| **Helvetica Neue LT Pro** | `--font-helvetica` | Sans-serif | Body text, descriptions, small text | Arial, sans-serif |
| **Space Mono** | `--font-space-mono` | Monospace | Accent/decorative (minimal usage) | Arial, sans-serif |

### Font Pairing Strategy

**Condensed Heavy (display) + Regular (body) + Monospace (prices/inputs)**. The condensed font does all the heavy lifting — product names, sale prices, buttons, and marquee. Regular Helvetica is for paragraph body text. Space Mono is used for original prices (strikethrough), captcha inputs, and replay links.

### Fluid Typography System

The site uses CSS `clamp()` with viewport-inline (`vi`) units for fully responsive type — no breakpoint jumps:

```css
/* Format: clamp(min, preferred, max) */
--type-60-140: clamp(3.75rem, 1.92rem + 7.8vi, 8.75rem);  /* Marquee: 60→140px */
--type-40-80:  clamp(2.5rem, 1.59rem + 3.9vi, 5rem);      /* Large heading: 40→80px */
--type-38-46:  clamp(2.375rem, 2.19rem + 0.78vi, 2.875rem); /* Sale price: 38→46px */
--type-40-36:  clamp(2.25rem, 2.59rem - 0.39vi, 2.5rem);   /* Button (shrinks!): 40→36px */
--type-36-40:  clamp(2.25rem, 2.16rem + 0.39vi, 2.5rem);   /* Product name: 36→40px */
--type-26-34:  clamp(1.625rem, 1.44rem + 0.78vi, 2.125rem); /* FAQ heading: 26→34px */
--type-18-28:  clamp(1.125rem, 0.90rem + 0.98vi, 1.75rem);  /* Header richtext: 18→28px */
--type-18-24:  clamp(1.125rem, 0.99rem + 0.59vi, 1.5rem);   /* FAQ answer: 18→24px */
--type-18-20:  clamp(1.125rem, 1.08rem + 0.20vi, 1.25rem);  /* Deal body: 18→20px */
--type-16-20:  clamp(1rem, 0.91rem + 0.39vi, 1.25rem);      /* Deal richtext/OG price: 16→20px */
--type-14-16:  clamp(0.875rem, 0.83rem + 0.20vi, 1rem);     /* Replay link: 14→16px */
--type-20-28:  clamp(1.25rem, 1.07rem + 0.78vi, 1.75rem);   /* Input: 20→28px */
```

> **Key**: The button font-size actually **decreases** on larger viewports (`40px → 36px`), which is unusual.

### Typography Scale (Computed Desktop Values)

#### Display Text (Helvetica Neue LT Pro Condensed)

| Variant | Font Size | Font Weight | Line Height | Letter Spacing | Text Transform | Usage |
|---------|-----------|-------------|-------------|----------------|----------------|-------|
| **Marquee** | `124.39px` | `900` (Black) | `124.39px` (1×) | `-4.98px` | `UPPERCASE` | Scrolling section dividers |
| **Price (sale)** | `44.44px` | `900` | `44.44px` (1×) | `-0.32px` | `none` | Sale price display |
| **Product Name** | `39.22px` | `900` | `39.22px` (1×) | `-0.32px` | `none` | Product card titles (h3) |
| **Button** | `36.78px` | `900` | — | — | `UPPERCASE` | CTA buttons |
| **Price (original)** | `19.22px` | `700` (Bold) | — | — | `none` | Strikethrough original price |

#### Body Text (Helvetica Neue LT Pro)

| Variant | Font Size | Font Weight | Line Height | Letter Spacing | Usage |
|---------|-----------|-------------|-------------|----------------|-------|
| **Body** | `26.05px` | `400` | `28.65px` (1.1×) | `-0.32px` | Main paragraphs, descriptions |
| **Body Default** | `16px` | `400` | `17.6px` (1.1×) | — | Base font size |
| **Small/Link** | `15.61px` | `400` | — | — | "Replay Captcha" links, fine print |

### Font Weight Usage

| Weight | Value | Usage |
|--------|-------|-------|
| **Regular** | `400` | Body text, small text, links |
| **Bold** | `700` | Original prices (strikethrough) |
| **ExtraBold** | `800` | Rare emphasis |
| **Black** | `900` | Everything display: headings, prices, buttons, marquee |

> **Key Insight**: Weight 900 (Black) dominates. The condensed font at Black weight is the visual identity. Regular 400 is only for body text. There's almost no "medium" — it jumps straight from regular to maximum bold.

---

## Spacing System

Spacing is **fluid** like typography, using CSS `clamp()`:

### Fluid Spacing Scale

```css
--space-10-15:   clamp(0.625rem, 0.51rem + 0.49vi, 0.9375rem);   /* 10→15px */
--space-10-20:   clamp(0.625rem, 0.40rem + 0.98vi, 1.25rem);     /* 10→20px */
--space-12-20:   clamp(0.75rem, 0.57rem + 0.78vi, 1.25rem);      /* 12→20px */
--space-20-30:   clamp(1.25rem, 1.02rem + 0.98vi, 1.875rem);     /* 20→30px */
--space-20-40:   clamp(1.25rem, 0.79rem + 1.95vi, 2.5rem);       /* 20→40px */
--space-30-40:   clamp(1.875rem, 1.65rem + 0.98vi, 2.5rem);      /* 30→40px */
--space-40-60:   clamp(2.5rem, 2.04rem + 1.95vi, 3.75rem);       /* 40→60px */
--space-60-100:  clamp(3.75rem, 2.84rem + 3.90vi, 6.25rem);      /* 60→100px */
--space-45-65:   clamp(2.8125rem, 2.36rem + 1.95vi, 4.0625rem);  /* 45→65px (sticker) */
--space-340-566: clamp(21.25rem, 16.08rem + 22.05vi, 35.375rem); /* 340→566px (footer!) */
```

### Padding

| Value | Frequency | Context |
|-------|-----------|---------|
| `20px` | Very high | General element padding |
| `15px` | Very high | Compact padding |
| `10px` | High | Button vertical padding, tight spacing |
| `30px` | High | Button horizontal padding |
| `40px` | Medium | Hero horizontal padding |
| `92.2px` | Low | Hero vertical padding (large) |
| `80px` | Low | FAQ section bottom padding |
| `56.1px` | Low | Section bottom padding |

### Gaps

| Value | Frequency | Context |
|-------|-----------|---------|
| `20px` | Very high | Standard gap between elements |
| `5px` | High | Tight element spacing |
| `56.1px` | Medium | Product card vertical gap (between deals) |

### Margins

| Value | Context |
|-------|---------|
| `6.86px` | Very common — small inline margins |
| `10px` | Standard element margins |
| `35px` | Section spacing |
| `110px–175px` | Large section vertical margins |

---

## Layout & Containers

### Max Widths

| Value | Usage |
|-------|-------|
| `1080px` | Primary page container |
| `930px` | Product deals grid container |
| `760px` | Narrow content (FAQ area) |
| `650px` | Compact content blocks |

### Page Structure

```
┌─────────────────────────────────────────┐
│  Hero (video bg, centered text)         │
│  padding: 92px 40px, text-align: center │
├─────────────────────────────────────────┤
│  Intro Paragraphs (centered, red bg)    │
├─────────────────────────────────────────┤
│                                         │
│  Product Deals (red bg)                 │
│  flex-column, gap: 56px                 │
│  Each deal: flex row / row-reverse      │
│  alternating layout                     │
│                                         │
├═════════════════════════════════════════┤
│  ▶▶ Marquee: "Deals You Missed" ▶▶     │
│  (124px scrolling uppercase text)       │
├═════════════════════════════════════════┤
│                                         │
│  FAQ Section (WHITE bg, RED text)       │
│  max-width: 760px                       │
│                                         │
├═════════════════════════════════════════┤
│  ▶▶ Marquee: "FAQ" ▶▶                  │
├─────────────────────────────────────────┤
│  Footer (red bg, white text)            │
└─────────────────────────────────────────┘
```

### Product Card Layout — Alternating Direction

```css
/* Odd deals: image left, text right */
.deal:nth-child(odd) {
  display: flex;
  flex-direction: row;
}

/* Even deals: image right, text left */
.deal:nth-child(even) {
  display: flex;
  flex-direction: row-reverse;
}
```

---

## Component Styles

### Buttons

Only one button style exists: the **"Sold Out"** button.

```css
.button {
  font-family: var(--font-sans-cond);
  font-size: var(--type-40-36);       /* 40→36px — shrinks on desktop! */
  font-weight: 900;
  line-height: 1.3;
  color: var(--background);           /* Red text */
  background-color: var(--foreground); /* White bg */
  border: 1px solid var(--background);
  border-radius: 0px;
  padding: 10px 30px;
  text-transform: uppercase;
  white-space: nowrap;
  display: inline-block;
  text-align: center;
  cursor: pointer;
  transition: background-color 0.1s linear,
              color 0.1s linear,
              border-color 0.1s linear;
}

/* Hover: INVERTS colors */
.button:not(:disabled):hover {
  background-color: var(--background);  /* Red bg */
  color: var(--foreground);             /* White text */
  border-color: var(--foreground);      /* White border */
}

.button:disabled {
  opacity: 0.8;
  cursor: not-allowed;
}
```

### Product Cards (Deals)

```css
.deal {
  display: flex;
  flex-direction: row;           /* Alternates with row-reverse */
  border: 1px solid #FFFFFF;
  position: relative;            /* For absolute sticker positioning */
}

.deal-image {
  flex: 1;
  position: relative;            /* Sticker anchor */
}

.deal-info {
  flex: 1;
  padding: 20px;
  display: flex;
  flex-direction: column;
  gap: 5px;
}
```

### Stickers / Badges

Positioned absolutely at top-right with **rotation and translate**:

```css
.sticker-primary {
  position: absolute;
  top: 0;
  right: 0;
  z-index: 100;
  height: var(--space-45-65);       /* 45→65px fluid */
  width: auto;
  rotate: var(--rotate, 15deg);     /* Tilted! */
  translate: 50%;                   /* Hangs off edge */
  pointer-events: none;
  overflow: clip;
}

.sticker-many {
  height: var(--space-40-53);       /* 40→53px fluid */
  /* Some use --rotate: -15deg or --tx: -40%/40% for variation */
}
```

### Tape Banners (Hero Video Overlay)

Diagonal repeating-image banners overlaid on the hero video:

```css
.tape-banners {
  position: absolute;
  inset: 0;
  overflow: hidden;
  pointer-events: none;
  z-index: 10;
}

.tape {
  position: absolute;
  height: 82px;                     /* 42px tablet, 30px mobile */
  width: 400%;
  left: -150%;
  background-repeat: repeat-x;
  background-size: 1586px 82px;
  border-top: 1px solid;
  border-bottom: 1px solid;
  /* Uses tape-red.png or tape-white.png textures */
}

/* 4 tapes at different angles */
.tape-1 { top: 43%; rotate: 24deg;  z-index: 11; animation: scroll-left 16s linear infinite; }
.tape-2 { top: 57%; rotate: -15deg; z-index: 13; animation: scroll-right 16s linear infinite; }
.tape-3 { top: 18%; rotate: -4deg;  z-index: 14; animation: scroll-left 16s linear infinite; }
.tape-4 { top: 68%; rotate: 4deg;   z-index: 12; animation: scroll-right 16s linear infinite; }
```

### Marquee Border (Fixed 4-Sided Frame)

A fixed marquee running along all 4 edges of the viewport:

```css
cah-marquee-border {
  position: fixed;
  inset: 0;
  width: 100%;
  height: 100vh;
  pointer-events: none;
  z-index: 1000;               /* Highest z-index on page */
}
/* Contains top, left, right, bottom scrolling strips */
/* --marquee-height: 25px */
/* Left/right rotated 90deg/-90deg */
/* Only top visible on mobile; all 4 at 1024px+ */
```

### Pagination Dots (Image Slider)

```css
.pagination button {
  width: 12px;
  height: 12px;
  border-radius: 24px;             /* Circle */
  border: 2px solid #000000;       /* Black border */
  background-color: #FFFFFF;       /* White fill */
  transition: background-color 0.2s, border-color 0.2s;
}

.pagination button.active {
  background-color: #000000;       /* Black fill */
  border-color: #FFFFFF;           /* White border */
}
```

### Input (Captcha)

```css
input {
  display: block;
  width: 100%;
  border: 1px solid var(--foreground);
  color: var(--foreground);
  text-align: center;
  font-family: var(--font-mono);    /* Space Mono */
  font-weight: 700;
  font-size: var(--type-20-28);     /* 20→28px fluid */
  padding: var(--space-10-15);
}
```

### Marquee / Scrolling Text

Giant horizontal scrolling text used as section separators:

```css
.marquee-container {
  font-family: var(--font-helvetica-cond);
  font-size: 124.39px;
  font-weight: 900;
  line-height: 124.39px;         /* 1× — no extra line height */
  letter-spacing: -4.98px;       /* Tight negative tracking */
  color: #FFFFFF;                /* White on red bg */
  text-transform: uppercase;
  overflow: visible;
  height: 124.39px;              /* CSS var: --marquee-height: 25px base */
  white-space: nowrap;
}

/* In the FAQ (inverted) section: red text on white */
.marquee-container.inverted {
  color: #FF0000;
}
```

### Price Display

```css
/* Sale price — large, bold condensed */
.sale-price {
  font-family: var(--font-sans-cond);
  font-size: var(--type-38-46);          /* 38→46px fluid */
  font-weight: 900;
  line-height: 1;
  color: var(--foreground);
  letter-spacing: -0.32px;
}

/* Original price — monospace, strikethrough */
.original-price {
  font-family: var(--font-mono);          /* Space Mono! */
  font-size: var(--type-16-20);          /* 16→20px fluid */
  font-weight: 700;
  color: var(--foreground);
  text-decoration: line-through solid;
}
```

### Links

```css
a {
  color: #FFFFFF;
  text-decoration: underline solid #FFFFFF;
  font-size: 15.61px;
  font-weight: 400;
  transition: text-decoration-color 0.1s ease-out;
}
```

### Hero Section

```css
.hero {
  padding: 92.2px 40px;
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: transparent;   /* Red page bg shows through */
}

/* Video background section */
.hero-video {
  background-color: #FFFFFF;
  border-radius: 0px;
  width: 100%;
}
```

### FAQ Section (Inverted)

```css
.faq-section {
  background-color: #FFFFFF;
  color: #FF0000;
  padding: 0px 0px 80px;
  max-width: 760px;
}
```

### Footer

```css
footer {
  background-color: #FF0000;
  color: #FFFFFF;
  height: var(--space-340-566);     /* 340→566px fluid! */
  border-top: 1px solid #FF0000;
  background-image: url("/footer.svg");  /* SVG pattern background */
  background-repeat: repeat-x;
  background-size: auto 100%;
  background-position: center center;
}
```

---

## Shadows & Elevation

**None.** Zero box-shadow anywhere on the site. The design is completely flat.

---

## Animations & Transitions

### Transitions

| Property | Duration | Easing | Usage |
|----------|----------|--------|-------|
| `background-color` | `0.1s` | `linear` | Button hover |
| `color` | `0.1s` | `linear` | Button hover |
| `border-color` | `0.1s` | `linear` | Button hover |
| `text-decoration-color` | `0.1s` | `ease-out` | Link hover |
| `transform` | `0.3s` | — | Element transforms |

### Marquee Animation

The marquee uses a continuous CSS scroll animation:

```css
@keyframes marquee-scroll {
  0%   { transform: translateX(0); }
  100% { transform: translateX(-50%); }  /* Content is duplicated for seamless loop */
}

.marquee-content {
  animation: marquee-scroll linear infinite;
  /* Speed varies by content length */
}
```

> The marquee text is duplicated inside the container so the scroll loops seamlessly.

---

## Border Radius

**`0px` everywhere.** No border radius on any element — buttons, cards, images, inputs. Pure rectangles.

---

## Borders

| Style | Usage |
|-------|-------|
| `1px solid #FFFFFF` | Product card borders (on red bg) |
| `1px solid #FF0000` | Button borders (on white bg / FAQ section) |
| `0px none` | Most elements (no borders) |

---

## Opacity & Transparency

| Value | Usage |
|-------|-------|
| `1.0` | Everything (default) |
| `0.8` | Rare — subtle dimming on specific elements |

> Opacity is barely used. The design is fully opaque.

---

## Gradients

**None.** Zero gradients anywhere.

---

## Background Textures

**None.** Pure flat color backgrounds only.

---

## CSS Custom Properties

```css
:root {
  --font-helvetica: "Helvetica Neue LT Pro", Arial, sans-serif;
  --font-helvetica-cond: "Helvetica Neue LT Pro Cond", Arial, sans-serif;
  --font-space-mono: "Space Mono", Arial, sans-serif;
  --marquee-height: 25px;
}
```

---

## Icons & Imagery

### Image Treatment

- Product images: no border-radius, no shadows
- Images fill their container (no `object-fit` constraints)
- Sticker badges overlay images at top-right
- Hero section contains a background video
- **171 images** on the page (product photos, stickers, decorative)

### Sticker System

Stickers are SVG-based badges positioned absolutely over product images:
- **Primary sticker** (white): ~139×61px, top-right
- **"Many" sticker** (red variant): ~92×50px, top-right

---

## Tailwind CSS Mapping

```js
module.exports = {
  theme: {
    extend: {
      colors: {
        'sale-red': '#FF0000',
        'sale-white': '#FFFFFF',
      },
      fontFamily: {
        'helvetica': ['"Helvetica Neue LT Pro"', 'Arial', 'sans-serif'],
        'helvetica-cond': ['"Helvetica Neue LT Pro Cond"', 'Arial', 'sans-serif'],
        'space-mono': ['"Space Mono"', 'monospace'],
      },
      fontSize: {
        'marquee': ['124.39px', { lineHeight: '124.39px', letterSpacing: '-4.98px' }],
        'price': ['44.44px', { lineHeight: '44.44px', letterSpacing: '-0.32px' }],
        'product': ['39.22px', { lineHeight: '39.22px', letterSpacing: '-0.32px' }],
        'button': ['36.78px', { lineHeight: '1' }],
        'body-lg': ['26.05px', { lineHeight: '28.65px', letterSpacing: '-0.32px' }],
        'price-og': ['19.22px', { lineHeight: '1' }],
        'small': ['15.61px', { lineHeight: '1' }],
      },
      borderRadius: {
        'none': '0px',  /* The ONLY radius used */
      },
      maxWidth: {
        'page': '1080px',
        'deals': '930px',
        'faq': '760px',
        'compact': '650px',
      },
    },
  },
};
```

### Common Class Patterns

```html
<!-- Page body -->
<body class="bg-sale-red text-sale-white font-helvetica text-base">

<!-- Marquee section divider -->
<div class="font-helvetica-cond text-marquee font-black uppercase whitespace-nowrap overflow-hidden">

<!-- Product name -->
<h3 class="font-helvetica-cond text-product font-black">

<!-- Sale price -->
<span class="font-helvetica-cond text-price font-black">$0.40</span>

<!-- Original price (strikethrough) -->
<s class="font-helvetica-cond text-price-og font-bold line-through">$39.99</s>

<!-- Button -->
<button class="font-helvetica-cond text-button font-black uppercase
               bg-sale-white text-sale-red border border-sale-red
               rounded-none px-[30px] py-[10px]
               transition-colors duration-100 ease-linear">
  Sold Out
</button>

<!-- Product card (odd) -->
<div class="flex flex-row border border-sale-white relative">

<!-- Product card (even — reversed) -->
<div class="flex flex-row-reverse border border-sale-white relative">

<!-- Body text -->
<p class="font-helvetica text-body-lg font-normal">

<!-- FAQ section (inverted) -->
<section class="bg-sale-white text-sale-red max-w-faq mx-auto pb-20">

<!-- Link -->
<a class="text-small underline transition-colors duration-100">

<!-- Sticker badge -->
<div class="absolute top-0 right-0 z-[100]">
```

---

## Example Component Reference Code

### Hero Section

```html
<header class="bg-sale-red text-sale-white text-center py-[92px] px-10 flex flex-col items-center">
  <h1 class="font-helvetica-cond text-[80px] font-black uppercase leading-none tracking-tighter">
    99% Off Sale
  </h1>
  <p class="font-helvetica text-body-lg font-normal max-w-compact mt-8">
    Today is Black Friday, Cards Against Humanity's favorite day of the year.
    To celebrate, we're offering 99% off everything.
  </p>
</header>
```

### Product Deal Card

```html
<!-- Odd card: image left, info right -->
<div class="flex flex-row border border-sale-white relative max-w-deals mx-auto">
  <!-- Image -->
  <div class="flex-1 relative">
    <img src="product.jpg" alt="Product" class="w-full h-full object-cover" />
    <!-- Sticker -->
    <div class="absolute top-0 right-0 z-[100]">
      <img src="sticker.svg" alt="99% OFF" class="h-[61px]" />
    </div>
  </div>
  <!-- Info -->
  <div class="flex-1 p-5 flex flex-col gap-[5px] justify-center">
    <h3 class="font-helvetica-cond text-product font-black">
      Labubu
    </h3>
    <div class="flex items-baseline gap-2">
      <span class="font-helvetica-cond text-price font-black">$0.40</span>
      <s class="font-helvetica-cond text-price-og font-bold line-through">$39.99</s>
    </div>
    <button class="font-helvetica-cond text-button font-black uppercase
                   bg-sale-white text-sale-red border border-sale-red
                   rounded-none px-[30px] py-[10px] mt-4 self-start
                   transition-colors duration-100 ease-linear">
      Sold Out
    </button>
  </div>
</div>

<!-- Even card: reversed -->
<div class="flex flex-row-reverse border border-sale-white relative max-w-deals mx-auto">
  <!-- Same structure, direction flipped via flex-row-reverse -->
</div>
```

### Marquee Section Divider

```html
<div class="overflow-hidden bg-sale-red border-y border-sale-white">
  <div class="flex whitespace-nowrap animate-marquee">
    <span class="font-helvetica-cond text-marquee font-black uppercase">
      Deals You Missed&nbsp;&nbsp;&nbsp;Deals You Missed&nbsp;&nbsp;&nbsp;
      Deals You Missed&nbsp;&nbsp;&nbsp;Deals You Missed&nbsp;&nbsp;&nbsp;
    </span>
    <!-- Duplicate for seamless loop -->
    <span class="font-helvetica-cond text-marquee font-black uppercase" aria-hidden="true">
      Deals You Missed&nbsp;&nbsp;&nbsp;Deals You Missed&nbsp;&nbsp;&nbsp;
      Deals You Missed&nbsp;&nbsp;&nbsp;Deals You Missed&nbsp;&nbsp;&nbsp;
    </span>
  </div>
</div>

<style>
@keyframes marquee {
  0% { transform: translateX(0); }
  100% { transform: translateX(-50%); }
}
.animate-marquee {
  animation: marquee 20s linear infinite;
}
</style>
```

### FAQ Section (Inverted Colors)

```html
<section class="bg-sale-white text-sale-red py-20">
  <div class="max-w-faq mx-auto px-5">
    <h2 class="font-helvetica-cond text-[40px] font-black uppercase mb-8">
      Frequently Asked Questions
    </h2>
    <div class="flex flex-col gap-5">
      <div class="border-b border-sale-red pb-5">
        <h4 class="font-helvetica-cond text-[24px] font-black">
          Is this real?
        </h4>
        <p class="font-helvetica text-base font-normal mt-2">
          Yes. Everything on this page was actually for sale at 99% off.
        </p>
      </div>
    </div>
  </div>
</section>
```

---

## Framework & CSS Architecture

- **Framework**: Astro (static site generator)
- **CSS Architecture**: CSS `@layer` ordering — `reset, theme, components, elements`
- **Design Tokens**: All via CSS custom properties (`--type-*`, `--space-*`, `--font-*`)
- **Responsive Strategy**: Fluid `clamp()` with `vi` units — **no breakpoint media queries** for typography/spacing
- **Media Queries**: Only for layout changes (`flex-direction`, show/hide elements)
- **Custom Elements**: `cah-deal`, `cah-deal-slider`, `cah-marquee-header`, `cah-marquee-border`
- **Libraries**: Blaze Slider (image carousel), HTMX (interactivity)
- **No Tailwind/utility framework** — all custom CSS
- **CSS Reset**: Full Meyer-style reset with `box-sizing: border-box`
- **Astro features**: View Transitions API, scoped styles via `data-astro-cid-*`, Image component

### Key Breakpoints (Layout Only)

| Value | Usage |
|-------|-------|
| `max-width: 400px` | Mobile: tape banners smaller (30px height) |
| `max-width: 768px` | Tablet: tape banners 42px height |
| `min-width: 769px` | Desktop: video fills viewport |
| `min-width: 1024px` | Desktop layout: deals row/row-reverse, marquee border all 4 sides |

---

## Summary of Key Design Rules

1. **Only two colors exist**: `#FF0000` and `#FFFFFF` — no grays, no opacity tricks (`#000000` only for pagination dots)
2. **Border radius is always 0px** — except pagination dots (circles via `border-radius: 24px`)
3. **Box shadow is never used** — completely flat design
4. **No gradients** — pure solid colors only
5. **Condensed Black (900) for all display text** — Helvetica Neue LT Pro Condensed dominates
6. **Space Mono for prices and inputs** — original strikethrough prices and captcha inputs use monospace
7. **Line-height is 1.0–1.1 for display, 1.3 for body** — ultra-tight throughout
8. **Negative letter-spacing everywhere** — `-0.02em` body, `-0.04em` marquee, `-0.32px` headings
9. **Product cards alternate direction** — odd = row, even = row-reverse (at 1024px+)
10. **Marquee text is the section divider** — no `<hr>`, no borders, giant scrolling text
11. **Buttons invert on hover** — white→red bg, red→white text
12. **Stickers are rotated** — `rotate: 15deg` and `translate: 50%` to hang off card edge
13. **All sizing is fluid** — `clamp()` with `vi` units for both type and spacing, no fixed breakpoints
14. **Tape banners overlay the hero** — diagonal animated texture strips at various angles
15. **Fixed marquee border** — scrolling text runs along all 4 viewport edges at z-index 1000
16. **The footer is a giant SVG pattern** — `340→566px` tall, repeating horizontally
17. **Transitions are 0.1s linear** — instant, mechanical, no easing curves
18. **The design is intentionally aggressive** — loud, maximal contrast, zero subtlety
