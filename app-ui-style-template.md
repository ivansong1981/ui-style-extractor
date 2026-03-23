# [Site Name] App UI Style Guide

> Derived from `[site-ui-style.md](./[site-ui-style.md])`
> Source website: [site-url](https://example.com/)
> Confidence note: core tokens below are inherited from the source website when possible. App shell, navigation, data views, and product flows are **adapted** or **inferred** unless real product UI was also analyzed.

---

## Overview

<!-- 2-3 sentences on how the website's visual language should translate into an app environment. -->

[Site Name]'s app UI should feel **[adjective], [adjective], [adjective]**. The goal is to preserve the brand's visual DNA while adapting it to denser, more functional product surfaces.

**Key App Characteristics:**
- [How brand color should appear in-product]
- [How typography should shift from marketing to product]
- [How spacing / density should feel]
- [How cards, borders, or surfaces should behave]
- [How motion should feel]
- [What should be reduced vs carried over from the website]

---

## Adaptation Scope

### Product Assumption

<!-- State what kind of app this guide is for. -->

- **Primary app type**: [e.g. B2B dashboard, creative tool, commerce admin, consumer utility]
- **Primary platforms**: [e.g. desktop web app first, mobile companion second]
- **Primary use cases**: [e.g. overview dashboards, detail views, forms, settings, data tables]

### Confidence Split

| Layer | Confidence | Notes |
|-------|------------|-------|
| **Inherited from website evidence** | High | [colors, type, spacing, radius, border, shadow, motion, icon tone] |
| **Adapted for app usage** | Medium | [shell, panel behavior, table density, form rhythm] |
| **Inferred where product UI is not visible** | Lower | [navigation model, states, mobile behavior, destructive patterns] |

---

## Website-to-App Translation

| Website Signal | App Translation |
|----------------|-----------------|
| **[Signal]** | [How it should show up in-product] |
| **[Signal]** | [How it should show up in-product] |
| **[Signal]** | [How it should show up in-product] |
| **[Signal]** | [How it should show up in-product] |

---

## Core Tokens to Preserve

### Color Roles

| Role | Color | Usage |
|------|-------|-------|
| **App Background** | `#______` | [Main workspace background] |
| **Primary Surface** | `#______` | [Cards, panels, drawers] |
| **Secondary Surface** | `#______` | [Sub-panels, grouped areas] |
| **Primary Text** | `#______` | [Headings, key values, labels] |
| **Secondary Text** | `#______` | [Body copy, meta text] |
| **Quiet Border** | `#______` | [Panel and table dividers] |
| **Primary Action** | `#______` | [CTA, active state] |
| **Focus / Selected** | `#______` | [Focus rings, selected rows, active nav] |
| **Success** | `#______` | [Positive status] |
| **Error** | `#______` | [Validation / failure state] |
| **Warning** | `#______` | [Warning state] |

### Typography

| Role | Size | Weight | Line Height | Usage |
|------|------|--------|-------------|-------|
| **Screen Title** | `__px` | `___` | `__px` | [Page-level title] |
| **Section Title** | `__px` | `___` | `__px` | [Panel headers] |
| **Body Default** | `__px` | `___` | `__px` | [Primary product copy] |
| **Body Small** | `__px` | `___` | `__px` | [Meta, secondary rows] |
| **Label / Control** | `__px` | `___` | `__px` | [Buttons, inputs, tabs] |
| **Numeric / KPI** | `__px` | `___` | `__px` | [Stats, dashboard metrics] |

### Spacing, Radius, and Elevation

| Token | Value | Usage |
|-------|-------|-------|
| **Page Padding** | `__px` | [Desktop shell padding] |
| **Panel Padding** | `__px` | [Cards, drawers, forms] |
| **Tight Gap** | `__px` | [Inline controls, labels] |
| **Standard Gap** | `__px` | [Common stacks and grids] |
| **Loose Gap** | `__px` | [Panel-to-panel rhythm] |
| **Control Radius** | `__px` | [Buttons, inputs] |
| **Panel Radius** | `__px` | [Cards, panels, drawers] |
| **Primary Shadow** | `[shadow]` | [Raised surfaces] |

---

## App Shell

### Desktop Shell

| Element | Recommendation |
|---------|----------------|
| **Top bar height** | `[value]` |
| **Sidebar width** | `[value]` |
| **Content padding** | `[value]` |
| **Default page max width** | `[value or fluid]` |
| **Panel gap** | `[value]` |

### Mobile Shell

| Element | Recommendation |
|---------|----------------|
| **Header height** | `[value]` |
| **Horizontal padding** | `[value]` |
| **Primary nav model** | [top tabs / bottom tabs / drawer] |
| **Bottom safe spacing** | `[value]` |

### Navigation Model

- **Primary navigation**: [sidebar / tab bar / segmented / mixed]
- **Secondary navigation**: [tabs / filter rail / inline segments]
- **Breadcrumbs**: [when to use]
- **Search placement**: [global bar / list view only / command palette]

---

## Screen Types

### 1. Overview / Dashboard

- [How KPIs should look]
- [How charts or highlights should be grouped]
- [How brand accents should be used]

### 2. List / Table Views

- [Default row density]
- [Sort / filter / search behavior]
- [Selected / hovered / focused row treatment]

### 3. Detail Views

- [Header structure]
- [Metadata layout]
- [Action placement]

### 4. Form / Create / Edit Flows

- [Field grouping rules]
- [Validation behavior]
- [Primary / secondary action placement]

### 5. Settings / Admin Screens

- [How to reduce visual drama]
- [How to preserve the brand tone]

---

## Component Patterns

### Buttons

| Variant | Recommendation |
|---------|----------------|
| **Primary** | [fill, text color, radius, height] |
| **Secondary** | [border, hover, quiet action] |
| **Ghost / Tertiary** | [text-first action] |
| **Destructive** | [how danger should be expressed] |

### Inputs and Selects

- Height: `[value]`
- Radius: `[value]`
- Border: `[value]`
- Focus style: `[value]`
- Error style: `[value]`

### Cards and Panels

- Background: `[value]`
- Border: `[value]`
- Radius: `[value]`
- Shadow behavior: `[value]`

### Tables and Data Blocks

- Header treatment: [background / border / typography]
- Row divider style: [border / zebra / none]
- Hover state: [value]
- Dense numeric alignment: [left / right]

### Badges and Status

- [How to map semantic states]
- [Whether badges should be pill, squared, or mixed]

### Modals, Drawers, and Overlays

- [Preferred entry pattern]
- [Backdrop treatment]
- [Spacing and action placement]

### Empty, Loading, and Error States

- [How expressive vs restrained they should be]
- [Whether gradients or illustrations are allowed]

---

## Platform Notes

### Desktop

- [What should be optimized for precision and density]

### Mobile

- [What should be simplified]
- [Minimum touch target]
- [How information hierarchy should collapse]

---

## Design Tokens / CSS Mapping

```css
:root {
  --app-bg: #______;
  --app-surface: #______;
  --app-border: #______;
  --app-text: #______;
  --app-text-soft: #______;
  --app-brand: #______;
  --app-focus: #______;
  --app-radius-control: __px;
  --app-radius-panel: __px;
  --app-shadow-panel: [shadow];
}
```

---

## Example Screen Recipes

### Dashboard

```text
Top bar
Sidebar | KPI row
Sidebar | Chart row
Sidebar | Activity / task / table row
```

### Detail Screen

```text
Top bar
Header: title + status + actions
Primary content column
Secondary metadata column
Related activity / notes / history
```

### Settings Screen

```text
Section nav
Page title
Grouped settings cards
Sticky save / footer actions if needed
```

---

## Summary of Key App Design Rules

- [Rule 1]
- [Rule 2]
- [Rule 3]
- [Rule 4]
- [Rule 5]
- [Rule 6]
- [Rule 7]
- [Rule 8]
- [Rule 9]
- [Rule 10]
