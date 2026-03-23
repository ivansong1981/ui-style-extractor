# Stripe Marketing UI Style Guide

> Design system extracted from [stripe.com](https://stripe.com/).
> Pages analyzed: homepage hero, homepage feature grid, pricing page sticky nav, shared HDS marketing CSS tokens, and component CSS from the public marketing bundle.

---

## Overview

Stripe's marketing UI is a **high-precision, editorial, gradient-accented** system built on a restrained neutral foundation. The core interface is quiet and structured: white surfaces, blue-black text, fine gray borders, tight spacing rules, and soft rounded cards. The drama is pushed into accent gradients, product-colored badges, and oversized background art rather than heavy chrome.

**Key Characteristics:**
- White and near-white surfaces with deep navy text
- Product accents organized into named color families rather than one-off gradients
- Variable sans typography with light body text and slightly heavier headings
- 4 / 8 / 12-column responsive grid with fixed 16px gutters
- Small radii on controls, medium radii on marketing cards
- Soft but measurable shadow scale, used selectively
- Motion that feels smooth and premium rather than playful
- Hero art and section accents driven by luminous ribbon gradients

---

## Design Philosophy

| Principle | Implementation |
|-----------|---------------|
| **Quiet base, vivid accents** | Most surfaces are white or pale neutral; saturated color appears in gradients, CTAs, indicators, and product badges. |
| **Dense but controlled information design** | Layouts use a strict grid, short line lengths, and evenly spaced card modules rather than large empty hero-only compositions. |
| **Premium through polish, not ornament** | Shadows are soft, borders are fine, curves are restrained, and motion uses tuned easing curves. |
| **System over page styling** | Shared HDS tokens define color, spacing, radius, typography, and elevation across homepage, pricing, nav, footer, and badges. |

---

## Color Palette

### Core Neutrals

| Name | Hex | Usage |
|------|-----|-------|
| **White** | `#FFFFFF` | Primary quiet surface, cards, navigation, footer panels |
| **Neutral 25** | `#F8FAFD` | Subdued page sections, soft card backgrounds |
| **Neutral 50** | `#E5EDF5` | Quiet borders and separators |
| **Neutral 500** | `#64748D` | Subdued text and supporting copy |
| **Neutral 600** | `#50617A` | Soft body text / secondary interface copy |
| **Neutral 990** | `#061B31` | Primary text, headings, strong UI labels |

### Brand / Action Scale

| Token | Hex | Usage |
|------|-----|-------|
| `brand-200` | `#B9B9F9` | Focus halo / soft brand tint |
| `brand-400` | `#7F7DFC` | Secondary brand accent |
| `brand-500` | `#665EFD` | Soft action backgrounds |
| `brand-600` | `#533AFD` | Primary CTA and active state |
| `brand-700` | `#4032C8` | CTA hover / stronger action state |
| `brand-900` | `#1C1E54` | Deep brand dark |

### Product Accent Families

Stripe's marketing art is organized into reusable accent families rather than one global rainbow:

| Family | Solid | Gradient |
|--------|-------|----------|
| **Default** | `#533AFD` | `#864CFF → #5E4CFE → #564DFE` |
| **Payments** | `#F44BCC` | `#F98BF9 → #F96BEE → #B262F9` |
| **Management** | `#FF6118` | `#FE8C2D → #FD6252 → #FD5D7C` |
| **Connect** | `#EA2261` | `#F84C31 → #EA2261 → #F03CA4` |
| **Revenue** | `#F9B900` | `#FFD552 → #FFAF2D → #FF9014` |

### Common Semantic / Utility Colors

| Context | Hex |
|---------|-----|
| Success | `#00B261` |
| Error | `#F3432A` |
| Focus outer | `#9A9AFE` |
| Link text in classic marketing areas | `#0A2540` |

### Color Roles by Surface

| Context | Background | Text | Border |
|---------|------------|------|--------|
| **Quiet page section** | `#FFFFFF` | `#061B31` | `#E5EDF5` |
| **Subdued section** | `#F8FAFD` | `#061B31` | `#E5EDF5` |
| **Primary button** | `#533AFD` | `#FFFFFF` | None |
| **Secondary button** | Transparent / white | Brand or dark text | Quiet brand border |
| **Badge background** | Pale tint by product | Dark/product tint text | None |

> **Key Insight**: Stripe's brand feeling does not come from flooding the UI with purple. Most of the product feels neutral and editorial; the brand enters through gradients and action states.

---

## Typography

### Font Families

| Font | Type | Role | Source |
|------|------|------|--------|
| **Sohne Var** | Sans-serif variable | Primary UI and marketing typography | `@font-face` in marketing bundle |
| **SF Pro Display** | Sans-serif | Fallback for primary UI font stack | Fallback in HDS |
| **Source Code Pro** | Monospace | Code-like / technical supporting contexts | `@font-face` in marketing bundle |

Primary stack:

```css
font-family: "sohne-var", "SF Pro Display", sans-serif;
```

### Font Pairing Strategy

The main pairing is **Sohne Var for all interface and marketing copy + Source Code Pro for technical accents when needed**. This keeps the UI calm and polished while preserving a subtle developer-product feel.

### Weight Usage

| Weight | Value | Usage |
|--------|-------|-------|
| Light / Normal | `300` | Default body copy on marketing pages |
| Normal | `400` | Headings, emphasized interface text |
| Medium | `500` | Some buttons and HDS bold states |

### Marketing Type Scale

#### Headings

| Variant | Mobile | Desktop / Wide | Notes |
|---------|--------|----------------|-------|
| **Hero** | `48px / 56px` | `56px / 68px` | `letter-spacing: -0.02em` |
| **Section** | `34px / 1.294` | `38px / 1.263` | Slight negative tracking |
| **Subsection** | `24px / 1.333` | `26px / 1.385` | Used in feature groups |
| **Detail / Stat** | `15px / 1.6` or `24px / 1.333` | Same | Anchored titles and small data blocks |

#### HDS Global Scale

| Token | Mobile-ish | Desktop |
|-------|-------------|---------|
| `heading-sm` | `20px` | `22px` |
| `heading-md` | `22px` | `26px` |
| `heading-lg` | `28px` | `32px` |
| `heading-xl` | `34px` | `48px` |
| `heading-xxl` | `48px` | `56px` |
| `text-sm` | `14px / 1.4` | `14px / 1.4` |
| `text-md` | `16px / 1.4` | `16px / 1.4` |
| `text-lg` | `16px / 1.35` | `18px / 1.4` |
| `text-xl` | `18px / 1.4` | `20px / 1.4` |

#### Body Text Patterns

| Variant | Size | Line Height | Letter Spacing | Usage |
|---------|------|-------------|----------------|-------|
| **Hero / Section body** | `18px` | `1.5556` | `0.2px` | Intro and supporting marketing copy |
| **Detail body** | `15px` | `1.6` | `0.2px` | Small explanatory copy |
| **Disclaimer** | `13px` | `1.6` | default | Fine print |

> **Key Insight**: Stripe gets hierarchy more from scale, line length, and placement than from big weight jumps.

---

## Responsive Breakpoints

| Breakpoint | Value | Usage |
|------------|-------|-------|
| **Mobile** | `< 600px` | Compact nav, stacked cards, 4-column logic |
| **Small Tablet Grid** | `min-width: 640px` | Switch to 8-column content grid |
| **Tablet / Component Shift** | `min-width: 600px` | Component padding and nav behavior changes |
| **Desktop Card Shift** | `min-width: 900px` | Card bleed and larger compositions |
| **Desktop Grid** | `min-width: 940px` | 12-column layout, full-width marketing composition |
| **Wide Type** | `min-width: 1112px` | Hero and section type scale increase |
| **Wide Locale / Utility** | `min-width: 1295px` | Larger utility and globalization layouts |

### Grid Behavior

```text
Mobile:  4 columns
Tablet:  8 columns
Desktop: 12 columns
Gap:     16px across all core grid sizes
Max content width: 1264px
```

---

## Spacing System

**Base unit**: `2px`

### Core Spacing Tokens

| Token | Value |
|-------|-------|
| `space-25` | `2px` |
| `space-50` | `4px` |
| `space-75` | `6px` |
| `space-100` | `8px` |
| `space-150` | `12px` |
| `space-200` | `16px` |
| `space-250` | `20px` |
| `space-300` | `24px` |
| `space-350` | `28px` |
| `space-400` | `32px` |
| `space-500` | `40px` |
| `space-600` | `48px` |
| `space-700` | `56px` |
| `space-800` | `64px` |
| `space-1000` | `80px` |

### Section Padding Rhythm

| Context | Padding Block Start / End |
|---------|---------------------------|
| Mobile section container | `56px` |
| Tablet section container | `64px` |
| Desktop section container | `96px` |

### Common Gap Values

| Value | Usage |
|-------|-------|
| `8px` | Tight inline icon / label gaps |
| `12px` | Small field and footer stacks |
| `16px` | Global grid gap, button groups, sticky nav rhythm |
| `24px` | Card padding / nav content |
| `40px` | Desktop nav list gap / card content paddings |
| `56px` | Large section rhythm |
| `64px` | Major section spacing |

---

## Layout & Containers

### Max Widths

| Value | Usage |
|-------|-------|
| `1264px` | Primary content container |
| `43ch` | Large section heading measure |
| `46ch` | Medium section heading measure |
| `50ch` | Supporting description measure |

### Layout Rules

- Section containers center within `1264px` and use consistent inline margins.
- Grid switches from `4 → 8 → 12` columns at `640px` and `940px`.
- Gutters stay at `16px`; the system scales by adding columns, not by growing gutter size.
- Text blocks stay narrow with `pretty` or `balance` wrapping to maintain editorial polish.
- Footer and feature sections often use subgrids or quarter/half span patterns rather than arbitrary card widths.

### Page Structure

```text
Navigation
Hero with large gradient art
Logo / trust strip
Sectioned feature grid
Optional sticky nav or product-specific jump nav
Feature CTA / footer
```

---

## Component Styles

### Primary Button

```css
.hds-button {
  font-family: var(--hds-font-family);
  font-weight: var(--hds-font-weight-bold);
  font-size: 1rem;
  line-height: 1;
  padding: 15.5px 24px 16.5px;
  border-radius: 4px;
  background: #533afd;
  color: #fff;
}
```

**Behavior:**
- Hover shifts background from `brand-600` to `brand-700`
- No heavy shadow by default
- Focus uses a `2px` outline plus `3px` offset

### Secondary Button

```css
.hds-button--secondary {
  background: transparent;
  border: 1px solid var(--hds-color-action-border-quiet);
  color: var(--hds-color-action-text-solid);
}
```

### Marketing CTA Button

`CtaButton.variant--Button` uses a pill-like marketing treatment:

- Padding: `3px 16px 6px`
- Radius: `16.5px`
- Primary fill from `buttonColor`
- Link-style CTA variant keeps transparent background and leans on text color + opacity hover

### Cards

Base `Card`:

- White or subdued background
- Border radius from shared token system
- Optional top accent bar: `8px`
- Optional soft border: `1px solid`
- Optional shadow tiers from shared shadow scale

`AccentedCard` adds:

- Radius: `8px`
- Top accent stripe: `8px`
- Hover scale: `1.018`
- Hover easing: `500ms cubic-bezier(0.7, 0, 0, 1)`
- Hover shadow can strengthen to `0 100px 60px -40px rgba(0,0,0,.06), 0 60px 100px 0 rgba(50,50,93,.15)`

### Badges

- Default font: `12px / 15px`
- Padding: roughly `3px 8px`
- Default background: pale neutral tint
- Rounded pill by default, `4px` when squared
- Product-colored variants: purple, blue, cyan, teal, pink, green, slate

### Sticky Nav

- Fixed to top when activated
- Background: card background / white
- Large soft shadow on reveal
- Link list gap: `16px` mobile, `40px` desktop
- Progress indicator uses a six-stop gradient:

```css
linear-gradient(
  270deg,
  #0073e6 4.91%,
  #16cbe1 21.6%,
  #48a4ed 40.82%,
  #635bff 60.04%,
  #9966ff 80.27%,
  #d187ff 96.97%
)
```

### Footer

- Grid layout with `2` columns on mobile, `4` columns from `600px`
- Link color uses soft neutral, hovering to solid dark
- Newsletter and footer CTA areas keep the same border and spacing language as the main body

---

## Shadows & Elevation

Stripe's shadows are soft, vertical, and layered. They are precise enough to feel engineered rather than airy.

### Shared Shadow Scale

| Level | Recipe |
|-------|--------|
| **XS** | `0 1px 4px 0` + `0 2px 10px 0` |
| **SM** | `0 2px 8px 0` + `0 5px 14px 0` |
| **MD** | `0 4px 8px 0` + `0 6px 22px 0` |
| **LG** | `0 5px 20px -2px` + `0 15px 40px -2px` |
| **XL** | `0 10px 60px -16px` + `0 20px 80px -16px` |

### Usage Notes

- Many surfaces rely on borders instead of shadows.
- Sticky nav and prominent cards use larger shadow tiers.
- Hovered accented cards can switch to a custom marketing shadow rather than a strict token.

---

## Animations & Transitions

### Core Motion Rules

- Standard hover transitions: `0.3s cubic-bezier(0.25, 1, 0.5, 1)`
- Navigation easing: `240ms` or `300ms`, `cubic-bezier(0.45, 0.05, 0.55, 0.95)`
- Accent card hover motion: `500ms cubic-bezier(0.7, 0, 0, 1)`
- Sticky nav reveal: `0.25s`

### Motion Character

- Smooth and premium, not bouncy
- Very small transforms
- Opacity changes often paired with color changes
- Reduced motion is explicitly respected in nav and carousel behaviors

---

## Border Radius

### Shared Radius Scale

| Token | Value | Usage |
|-------|-------|-------|
| `radius-none` | `0px` | Hard-edged structural cases |
| `radius-xs` | `2px` | Tiny icon containers, focus corners |
| `radius-sm` | `4px` | Buttons, links, compact controls |
| `radius-md` | `6px` | Standard HDS cards and inputs |
| `radius-lg` | `16px` | Marketing pills / large soft surfaces |
| `radius-xl` | `32px` | Rare oversized curves |
| `radius-round` | `99999px` | Pills and circular badges |

### Practical Exception

- `AccentedCard` uses `8px` radius in marketing code, slightly softer than the base HDS medium radius.

---

## Borders

- Quiet structural borders are almost always `1px`
- Border color usually resolves to `neutral-50` or a brand-quiet token
- Dashed borders are used for some section dividers in the marketing shell
- Transparent/low-opacity borders appear in secondary buttons and translucent overlays

---

## Opacity & Transparency

- Translucent white overlays appear in navigation and popovers: `#FFFFFF8C`, `#FFFFFFA6`
- Hover feedback often uses opacity reduction around `0.6` to `0.7`
- Stripe generally prefers translucent surface layers over fully blurred glassmorphism

---

## Gradients & Background Effects

### Core Gradient Logic

- Large hero ribbons use product accent families blended into luminous curves
- Product identity is often encoded through warm-to-cool multi-stop blends
- Gradients usually sit in illustration space or indicators, not in body text backgrounds

### Common Treatments

- Hero ribbon gradients with purple, orange, pink, and gold
- Radial translucent white overlay in mobile nav footer
- Linear masked sticky-nav track fade
- Light blur / backdrop blur on overlays and consent surfaces

---

## Tailwind CSS Mapping

```js
theme: {
  extend: {
    colors: {
      stripe: {
        bg: '#ffffff',
        surface: '#f8fafd',
        border: '#e5edf5',
        text: '#061b31',
        soft: '#50617a',
        muted: '#64748d',
        brand: '#533afd',
        brandHover: '#4032c8'
      }
    },
    borderRadius: {
      xs: '2px',
      sm: '4px',
      md: '6px',
      marketing: '8px',
      pill: '99999px'
    },
    boxShadow: {
      stripeLg: '0 5px 20px -2px rgba(6, 27, 49, 0.08), 0 15px 40px -2px rgba(6, 27, 49, 0.08)'
    },
    maxWidth: {
      content: '1264px'
    }
  }
}
```

---

## Example Component Reference Design Code

```html
<section class="feature-card">
  <span class="badge badge-purple">Automation</span>
  <h3>Launch billing flows without rebuilding your product shell.</h3>
  <p>Keep the content original, but preserve Stripe's neutral base, soft border, and gradient accent language.</p>
  <a href="/">See details</a>
</section>
```

```css
.feature-card {
  padding: 32px;
  border: 1px solid #e5edf5;
  border-radius: 8px;
  background: #fff;
  box-shadow: 0 5px 20px -2px rgba(6, 27, 49, 0.05);
}

.badge-purple {
  display: inline-flex;
  align-items: center;
  padding: 3px 8px;
  border-radius: 99999px;
  background: #f0e8ff;
  color: #533afd;
  font: 500 12px/15px "sohne-var", "SF Pro Display", sans-serif;
}
```

---

## Summary of Key Design Rules

- Keep the base UI neutral and let color live in accents, indicators, and illustrations.
- Use `#061B31` or nearby navy tones for primary text instead of pure black.
- Use `#FFFFFF` and `#F8FAFD` as the dominant surface backgrounds.
- Keep gutters fixed at `16px`; scale layout by columns, not random spacing changes.
- Use short, editorial line lengths and balanced wrapping.
- Prefer `4px`, `6px`, or `8px` radii; avoid exaggerated softness.
- Reserve large rounded pills for CTAs and badges.
- Use very fine `1px` borders on quiet surfaces.
- Keep shadows soft, vertical, and layered; avoid hard or colorful shadows.
- Primary CTAs should read as crisp, flat fills with subtle hover darkening.
- Secondary CTAs should stay visually lighter and rely on borders.
- Use product accent families consistently rather than inventing new gradients.
- Put gradients in hero art, top borders, progress indicators, and illustration space.
- Avoid noisy backgrounds behind dense copy.
- Keep motion smooth and tuned; no springy or elastic animation.
- Respect reduced-motion preferences.
- Make hover states feel premium through opacity, color, and very small transforms.
- Favor structured grids and aligned card systems over freeform marketing collage.
- When building new pages, change the content completely but preserve the visual grammar.
