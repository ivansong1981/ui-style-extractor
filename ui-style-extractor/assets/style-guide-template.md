# [Site Name] UI Style Guide

> Design system extracted from [site-url](https://example.com/).
> Pages analyzed: [list the specific pages you inspected]

---

## Overview

<!-- 2-3 sentences describing the overall visual identity. What does it feel like? What design movement does it reference? -->

[Site Name]'s design language is a **[adjective], [adjective]** system that [describe the core visual approach]. The aesthetic feels like [analogy or reference point].

**Key Characteristics:**
- [Primary typography choice and how it's used]
- [Border radius philosophy — sharp? rounded? mixed?]
- [Shadow style — blurry? offset? none?]
- [Background treatment — pure white? warm? dark? textured?]
- [Color strategy — high contrast? muted? monochromatic? colorful?]
- [Border usage — thick? thin? none? decorative?]
- [Any unique or distinctive visual element]

---

## Design Philosophy

<!-- What principles drive the visual decisions? Map each to how it shows up in the CSS. -->

| Principle | Implementation |
|-----------|---------------|
| **[Principle 1]** | [How it manifests in the design] |
| **[Principle 2]** | [How it manifests in the design] |
| **[Principle 3]** | [How it manifests in the design] |
| **[Principle 4]** | [How it manifests in the design] |

---

## Color Palette

### Primary Colors

<!-- The 3-5 most-used colors. Include exact hex, RGB, and where each is used. -->

| Name | Hex | RGB | Usage |
|------|-----|-----|-------|
| **[Primary Text/Dark]** | `#______` | `rgb(_, _, _)` | [Where it's used] |
| **[Brand Accent]** | `#______` | `rgb(_, _, _)` | [Where it's used] |
| **[Background]** | `#______` | `rgb(_, _, _)` | [Where it's used] |
| **[Surface/Card]** | `#______` | `rgb(_, _, _)` | [Where it's used] |

### Secondary Colors

<!-- Additional palette colors. Skip if the site is strictly 2-3 colors. -->

| Name | Hex | RGB | Usage |
|------|-----|-----|-------|
| **[Color Name]** | `#______` | `rgb(_, _, _)` | [Where it's used] |

### Neutral Colors

| Name | Hex | RGB | Usage |
|------|-----|-----|-------|
| **[Dark Gray]** | `#______` | `rgb(_, _, _)` | [Usage] |
| **[Medium Gray]** | `#______` | `rgb(_, _, _)` | [Usage] |
| **[Light Gray]** | `#______` | `rgb(_, _, _)` | [Usage] |

### Semantic Colors

<!-- Colors with functional meaning. -->

| Context | Color | Hex |
|---------|-------|-----|
| **Success** | [Name] | `#______` |
| **Error** | [Name] | `#______` |
| **Warning** | [Name] | `#______` |
| **Info** | [Name] | `#______` |

### Dark Theme / Inverted Sections

<!-- If the site has dark sections or a dark mode, document the palette swap. -->

| Element | Color |
|---------|-------|
| Background | `#______` |
| Text | `#______` |
| Accent | `#______` |

---

## Typography

### Font Families

<!-- List every font used. Check DevTools > Computed tab for actual rendered fonts. -->

| Font | Type | Role | Fallback |
|------|------|------|----------|
| **[Display Font]** | [Serif/Sans/Mono] | [Headings, buttons, nav...] | `[fallback stack]` |
| **[Body Font]** | [Serif/Sans/Mono] | [Body text, descriptions...] | `[fallback stack]` |
| **[Accent Font]** | [Serif/Sans/Mono] | [Special elements...] | `[fallback stack]` |

### @font-face Declarations

<!-- If the site uses custom fonts (not Google Fonts), document the declarations. -->

```css
@font-face {
  font-family: '[Font Name]';
  src: url('[path].woff2') format('woff2');
  font-weight: [weight];
  font-style: normal;
  font-display: swap;
}
```

### Font Pairing Strategy

<!-- Explain WHY these fonts are paired. What contrast do they create? -->

The core pairing is **[Display Font] (headings/UI) + [Body Font] (body)**. This creates [describe the contrast — technical vs readable, formal vs casual, etc.].

### Typography Scale

#### Headings

| Level | Font Size | Font Weight | Line Height | Letter Spacing | Text Transform | Usage |
|-------|-----------|-------------|-------------|----------------|----------------|-------|
| **H1** | `__px` | `___` | `__px` (_._ ×) | `___` | `[UPPERCASE/none]` | [Usage] |
| **H2** | `__px` | `___` | `__px` (_._ ×) | `___` | `[UPPERCASE/none]` | [Usage] |
| **H3** | `__px` | `___` | `__px` (_._ ×) | `___` | `[UPPERCASE/none]` | [Usage] |

#### Body Text

| Variant | Font Size | Font Weight | Line Height | Letter Spacing | Usage |
|---------|-----------|-------------|-------------|----------------|-------|
| **Body Large** | `__px` | `___` | `__px` | `___` | [Usage] |
| **Body Default** | `__px` | `___` | `__px` | `___` | [Usage] |
| **Body Small** | `__px` | `___` | `__px` | `___` | [Usage] |

#### UI Text

| Variant | Font Size | Font Weight | Line Height | Letter Spacing | Text Transform | Usage |
|---------|-----------|-------------|-------------|----------------|----------------|-------|
| **Nav Link** | `__px` | `___` | — | `___` | `[transform]` | [Usage] |
| **Button** | `__px` | `___` | — | `___` | `[transform]` | [Usage] |
| **Label/Tag** | `__px` | `___` | — | `___` | `[transform]` | [Usage] |

### Font Weight Usage

| Weight | Value | Usage |
|--------|-------|-------|
| **Light** | `300` | [Where used, or remove row] |
| **Regular** | `400` | [Where used] |
| **Medium** | `500` | [Where used, or remove row] |
| **SemiBold** | `600` | [Where used, or remove row] |
| **Bold** | `700` | [Where used] |

> **Key Insight**: [Describe the weight strategy — e.g., "Headings stay light, hierarchy comes from size and case, not weight."]

---

## Responsive Breakpoints

<!-- List breakpoints in order. Note mobile-first vs desktop-first approach. -->

| Name | Value | Usage |
|------|-------|-------|
| **Mobile** | `< ___px` | [Default / base styles] |
| **Tablet** | `min-width: ___px` | [Layout changes] |
| **Desktop** | `min-width: ___px` | [Full layout] |
| **Desktop Large** | `min-width: ___px` | [Max sizes] |

<!-- If the site uses fluid sizing (clamp/vi units) instead of breakpoints, document that approach here. -->

---

## Spacing System

<!-- Identify the base unit (4px? 8px? fluid?) and document the scale. -->

**Base unit**: `__px`

### Spacing Scale

| Token | Value | Usage |
|-------|-------|-------|
| `space-1` | `_px` | [Context] |
| `space-2` | `_px` | [Context] |
| `space-3` | `_px` | [Context] |
| `space-4` | `_px` | [Context] |
| `space-6` | `_px` | [Context] |
| `space-8` | `_px` | [Context] |
| `space-12` | `_px` | [Context] |
| `space-16` | `_px` | [Context] |

### Common Padding Values

| Value | Context |
|-------|---------|
| `_px` | [Where used] |

### Common Gap Values

| Value | Context |
|-------|---------|
| `_px` | [Where used] |

---

## Layout & Containers

### Max Widths

| Value | Usage |
|-------|-------|
| `____px` | Primary content container |
| `____px` | Narrow content sections |
| `____px` | Text-focused content |

### Page Structure

<!-- Draw an ASCII diagram of the page structure. -->

```
┌─────────────────────────────────────────┐
│  [Header / Navigation]                  │
├─────────────────────────────────────────┤
│                                         │
│  [Hero Section]                         │
│                                         │
├─────────────────────────────────────────┤
│                                         │
│  [Content Sections]                     │
│                                         │
├─────────────────────────────────────────┤
│  [Footer]                              │
└─────────────────────────────────────────┘
```

---

## Component Styles

### Buttons

#### Primary Button

```css
.button-primary {
  font-family: "[Font]", sans-serif;
  font-size: __px;
  font-weight: ___;
  color: #______;
  background-color: #______;
  border: _px solid #______;
  border-radius: _px;
  padding: __px __px;
  text-transform: [uppercase/none];
  cursor: pointer;
  transition: [property] [duration] [easing];
}

.button-primary:hover {
  /* [Describe hover behavior] */
}

.button-primary:active {
  /* [Describe active behavior] */
}
```

#### Secondary Button

```css
/* [Document secondary button styles] */
```

### Cards

```css
.card {
  background: #______;
  border: _px solid #______;
  border-radius: _px;
  padding: __px;
  /* [Shadow if any — see Shadows section] */
}
```

### Navigation

```css
/* [Document nav structure and styles] */
```

### Form Inputs

```css
.input {
  font-family: "[Font]", sans-serif;
  font-size: __px;
  color: #______;
  background-color: #______;
  border: _px solid #______;
  border-radius: _px;
  padding: __px __px;
}

.input:focus {
  border-color: #______;
  outline: [outline style];
}
```

### [Site-Specific Components]

<!-- Document any unique components: marquees, badges, stickers, etc. -->

```css
/* [Component-specific styles] */
```

---

## Shadows & Elevation

<!-- Describe the shadow philosophy: blurry depth? hard offset? none? -->

**Shadow style**: [Describe — e.g., "Hard offset shadows with 0 blur" or "Subtle blur shadows for depth" or "No shadows at all"]

| Level | CSS Value | Usage |
|-------|-----------|-------|
| **Small** | `_px _px _px _px #______` | [Usage] |
| **Medium** | `_px _px _px _px #______` | [Usage] |
| **Large** | `_px _px _px _px #______` | [Usage] |

---

## Animations & Transitions

### Transition Defaults

| Property | Duration | Easing | Usage |
|----------|----------|--------|-------|
| [Property] | `_.__s` | `[easing]` | [Context] |

### Hover Behaviors

<!-- Document what happens on hover for key elements. -->

| Element | Hover Effect |
|---------|-------------|
| Buttons | [Describe] |
| Cards | [Describe] |
| Links | [Describe] |

### Keyframe Animations

<!-- If the site uses CSS keyframe animations (marquees, loading states, etc.) -->

```css
@keyframes [name] {
  /* [Document animation] */
}
```

---

## Border Radius

<!-- Document the radius scale. Many distinctive sites have a strict policy. -->

| Element | Radius | Notes |
|---------|--------|-------|
| Cards | `_px` | |
| Buttons | `_px` | |
| Inputs | `_px` | |
| Images | `_px` | |
| Badges/Tags | `_px` | |

> **Rule**: [Describe the radius philosophy — e.g., "Never exceed 2px" or "Fully rounded pills for all interactive elements"]

---

## Borders

| Context | Width | Style | Color |
|---------|-------|-------|-------|
| Card borders | `_px` | `solid` | `#______` |
| Section dividers | `_px` | `solid` | `#______` |
| Input borders | `_px` | `solid` | `#______` |

---

## Opacity & Transparency

| Name | Value | Usage |
|------|-------|-------|
| **[Name]** | `rgba(_, _, _, _._)` | [Usage] |

<!-- If the site avoids opacity entirely, note that. -->

---

## Gradients

<!-- Many strong design systems avoid gradients. Document either way. -->

**Gradient usage**: [e.g., "No decorative gradients — only functional edge fading" or "Linear gradients used for hero backgrounds"]

---

## Background Textures

<!-- Document any background patterns, noise overlays, or texture images. -->

**Texture usage**: [e.g., "SVG noise overlay at 3% opacity" or "No textures — pure flat"]

---

## CSS Custom Properties

<!-- If the site defines CSS variables, document the key ones. -->

```css
:root {
  /* Colors */
  --color-primary: #______;
  --color-accent: #______;
  --color-bg: #______;

  /* Typography */
  --font-display: '[Font]', [fallback];
  --font-body: '[Font]', [fallback];

  /* Spacing */
  --space-unit: _px;
}
```

---

## Icons & Imagery

<!-- Document icon style, size, and source. -->

| Attribute | Value |
|-----------|-------|
| Icon style | [Outline / Filled / Duotone] |
| Icon source | [Custom SVG / Phosphor / Lucide / etc.] |
| Default icon size | `__px` |
| Image treatment | [Rounded? Bordered? Filtered?] |

---

## Tailwind CSS Mapping

<!-- Map the design system to Tailwind config. This is what makes the guide immediately actionable. -->

```js
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        '[prefix]-dark': '#______',
        '[prefix]-accent': '#______',
        '[prefix]-bg': '#______',
        '[prefix]-surface': '#______',
      },
      fontFamily: {
        'display': ['"[Font]"', '[fallback]'],
        'body': ['"[Font]"', '[fallback]'],
      },
      borderRadius: {
        '[prefix]': '_px',
      },
      boxShadow: {
        '[prefix]-sm': '_ _ _ _ #______',
        '[prefix]-md': '_ _ _ _ #______',
      },
    },
  },
}
```

### Common Tailwind Patterns

```html
<!-- Heading -->
<h2 class="font-display text-[__px] font-[___] leading-[_._] uppercase tracking-[___]">
  HEADING TEXT
</h2>

<!-- Body -->
<p class="font-body text-[__px] font-[___] leading-[_._] text-[prefix]-dark">
  Body text content.
</p>

<!-- Primary Button -->
<button class="font-display text-[__px] bg-[prefix]-accent text-[prefix]-dark
               border-[_px] border-[prefix]-dark rounded-[prefix] px-_ py-_
               uppercase hover:[hover-effect]">
  Button Label
</button>

<!-- Card -->
<div class="bg-[prefix]-surface border-[_px] border-[prefix]-dark
            rounded-[prefix] p-_ shadow-[prefix]-sm">
  Card content
</div>
```

---

## Example Component Reference Code

<!-- Provide 2-3 fully composed components that combine multiple design tokens.
     These serve as integration tests for the style guide. -->

### [Component 1: e.g., Hero Section]

```html
<!-- [Paste a complete, working HTML+CSS snippet] -->
```

### [Component 2: e.g., Feature Card]

```html
<!-- [Paste a complete, working HTML+CSS snippet] -->
```

---

## Summary of Key Design Rules

<!-- 15-20 non-negotiable rules. These are the "guardrails" that keep generated pages on-brand.
     This section is arguably the MOST important for AI generation quality. -->

1. **[Rule about typography]** — [explanation]
2. **[Rule about shadows]** — [explanation]
3. **[Rule about border radius]** — [explanation]
4. **[Rule about borders]** — [explanation]
5. **[Rule about colors]** — [explanation]
6. **[Rule about spacing]** — [explanation]
7. **[Rule about backgrounds]** — [explanation]
8. **[Rule about hover states]** — [explanation]
9. **[Rule about font weights]** — [explanation]
10. **[Rule about transitions]** — [explanation]
11. **[Rule about text transform]** — [explanation]
12. **[Rule about layout]** — [explanation]
13. **[Rule about unique element]** — [explanation]
14. **[Rule about responsive]** — [explanation]
15. **[Rule about overall feel]** — [explanation]
