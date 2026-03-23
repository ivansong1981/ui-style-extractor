# Stripe App UI Style Guide

> Derived from [stripe-ui-style.md](./stripe-ui-style.md)
> Source website: [stripe.com](https://stripe.com/)
> Confidence note: colors, typography, spacing, radius, borders, shadows, and motion below are inherited from Stripe's marketing UI and shared HDS tokens. App shell, table density, navigation, and workflow patterns are **adapted for a desktop-first B2B product UI** rather than directly extracted from a logged-in Stripe app surface.

---

## Overview

Stripe's app UI should feel **precise, restrained, premium, and operational**. The website's quiet neutral foundation, deep navy text, and measured brand accents translate well into product surfaces, but the app version should reduce decorative gradients and hero-like spacing in favor of sharper information grouping, stronger state clarity, and reliable data density.

**Key App Characteristics:**
- Neutral-first workspace with white and near-white panels
- Deep navy text, fine gray borders, and low-drama surfaces
- Brand purple reserved for primary actions, focus, and selected states
- Product accent families used for tags, charts, and categorical highlights rather than full-screen decoration
- Small, exact radii and soft engineered shadows
- Dense but breathable panel rhythm built from the same 4/8/16 spacing logic as the website

---

## Adaptation Scope

### Product Assumption

- **Primary app type**: desktop-first financial operations / payments management SaaS
- **Primary platforms**: web app first, mobile companion second
- **Primary use cases**: overview dashboards, object lists, transaction detail views, settings, workflow forms, reporting

### Confidence Split

| Layer | Confidence | Notes |
|-------|------------|-------|
| **Inherited from website evidence** | High | Color palette, typography family, spacing scale, radius scale, border language, shadow behavior, motion tone, badge color families |
| **Adapted for app usage** | Medium | Shell structure, page density, dashboard rhythm, table rows, form grouping, settings surfaces |
| **Inferred where product UI is not visible** | Lower | Sidebar behavior, mobile navigation, destructive flows, drawer patterns, advanced data-grid conventions |

---

## Website-to-App Translation

| Website Signal | App Translation |
|----------------|-----------------|
| **Quiet base, vivid accents** | The workspace stays mostly white and neutral. Purple and product accents appear in active nav, primary actions, status chips, and selected states rather than large decorative blocks. |
| **Dense but controlled information design** | Replace editorial marketing sections with repeatable app panels, summary metrics, tables, and two-column detail layouts that still preserve clean spacing and narrow text measures. |
| **Premium through polish, not ornament** | Use fine borders, tuned shadows, and exact typography instead of loud chrome. App UI should feel expensive because it is disciplined, not because it is visually busy. |
| **Gradient-led marketing drama** | Keep gradients for onboarding, charts, highlights, or empty-state accents. Do not use ribbon gradients as default app backgrounds. |

---

## Core Tokens to Preserve

### Color Roles

| Role | Color | Usage |
|------|-------|-------|
| **App Background** | `#F8FAFD` | Main workspace background outside cards |
| **Primary Surface** | `#FFFFFF` | Cards, tables, drawers, modal bodies |
| **Secondary Surface** | `#F8FAFD` | Nested panels, quiet sections, grouped controls |
| **Primary Text** | `#061B31` | Screen titles, metric values, active labels |
| **Secondary Text** | `#50617A` | Body copy, helper text, less critical metadata |
| **Muted Text** | `#64748D` | Table meta, placeholder copy, secondary timestamps |
| **Quiet Border** | `#E5EDF5` | Card edges, row dividers, input borders |
| **Primary Action** | `#533AFD` | Primary buttons, active tabs, active nav |
| **Primary Action Hover** | `#4032C8` | CTA hover / strong active state |
| **Focus Ring** | `#9A9AFE` | Focus halo and selected-field emphasis |
| **Success** | `#00B261` | Positive status and completion state |
| **Error** | `#F3432A` | Validation and destructive alerts |
| **Warning / Revenue Accent** | `#F9B900` | Warning chips, emphasized finance highlights |

### Product Accent Families

Use the existing marketing accent families as **semantic or categorical accents**, not as surface backgrounds:

| Family | Primary Use In App |
|--------|---------------------|
| **Default / Brand** | Primary actions, selected state, default category |
| **Payments** | Payments-related chips, charts, event categories |
| **Management** | Admin / operations highlights |
| **Connect** | Platform / partner states |
| **Revenue** | Revenue insights, warning-toned highlights |

### Typography

Primary stack:

```css
font-family: "sohne-var", "SF Pro Display", sans-serif;
```

Use `Source Code Pro` sparingly for technical IDs, short inline code, or machine-like metadata.

| Role | Size | Weight | Line Height | Usage |
|------|------|--------|-------------|-------|
| **Screen Title** | `32px` | `400` | `40px` | Top-level dashboard, detail, or settings titles |
| **Section Title** | `22px` | `400` | `30px` | Card groups, report section headers |
| **Panel Title** | `18px` | `400` | `26px` | Table cards, summary blocks, drawer headings |
| **Body Default** | `16px` | `300` | `22px` | Primary product copy |
| **Body Small** | `14px` | `300` | `20px` | Meta text, helper text, row annotations |
| **Label / Control** | `14px` | `400` | `20px` | Buttons, tabs, field labels |
| **KPI Value** | `28px` | `400` | `36px` | Summary metrics |
| **Tiny Meta** | `12px` | `400` | `16px` | Badges, eyebrow labels, dense meta rows |

### Spacing, Radius, and Elevation

| Token | Value | Usage |
|-------|-------|-------|
| **Page Padding** | `24px` desktop / `16px` mobile | Main shell padding |
| **Panel Padding** | `24px` | Standard cards, forms, drawers |
| **Dense Panel Padding** | `16px` | Small summary blocks, compact modules |
| **Tight Gap** | `8px` | Labels, icon/text pairs, segmented controls |
| **Standard Gap** | `16px` | Common layout spacing |
| **Loose Gap** | `24px` | Card content groups |
| **Section Gap** | `32px` | Major panel-to-panel rhythm |
| **Control Radius** | `4px` | Buttons, inputs, tabs |
| **Panel Radius** | `6px` or `8px` | Cards and elevated panels |
| **Primary Shadow** | `0 4px 8px 0 rgba(6,27,49,.06), 0 6px 22px 0 rgba(6,27,49,.08)` | Raised drawers, modals, key panels |

---

## App Shell

### Desktop Shell

| Element | Recommendation |
|---------|----------------|
| **Top bar height** | `64px` |
| **Sidebar width** | `264px` |
| **Content padding** | `24px` |
| **Default content mode** | Fluid layout within the viewport, but keep dense text blocks under `72ch` |
| **Primary panel gap** | `16px` |
| **Major section gap** | `24px` or `32px` |

### Mobile Shell

| Element | Recommendation |
|---------|----------------|
| **Header height** | `56px` |
| **Horizontal padding** | `16px` |
| **Primary nav model** | Bottom tabs for core destinations, top-level drilldown for object details |
| **Bottom safe spacing** | `16px` minimum beyond system insets |

### Navigation Model

- **Primary navigation**: left sidebar on desktop, 4-5 destination bottom tabs on mobile
- **Secondary navigation**: tabs or segmented controls inside the content area, not a second full-height rail unless the product is workspace-heavy
- **Breadcrumbs**: use only for deep operational views and settings hierarchies
- **Search placement**: global search in the top bar; table-local search inside list cards
- **Workspace switchers**: keep quiet, border-light, and compact

### Shell Behavior

- Sidebar and top bar should feel like part of one neutral frame, not separate visual brands.
- Primary nav active state can use a pale brand tint plus dark text or a solid purple indicator bar.
- Do not flood the shell with gradients. Keep it calm so tables and forms stay readable.

---

## Screen Types

### 1. Overview / Dashboard

- Start with a KPI row of 3-5 cards.
- Follow with one high-signal chart row and one operational row: recent activity, tasks, approvals, or recent transactions.
- KPI cards can use subtle product-family chips or tiny gradient accents, but the card base stays white.
- Large numeric values should use Stripe's calm hierarchy: large type, low decoration, strong spacing.

### 2. List / Table Views

- Default row height: `48px` comfortable, `44px` dense mode.
- Header row uses white or `#F8FAFD` background with `1px` bottom border.
- Numeric columns align right.
- Hover state: soft neutral tint or low-opacity brand tint, never loud fills.
- Selected rows use a brand-tinted background, not a full solid purple block.

### 3. Detail Views

- Header pattern: title, status, primary action cluster, quiet metadata.
- Use a `2`-column desktop split when the object has supporting metadata; collapse to single-column on mobile.
- Side metadata panels should reuse the same border and radius language as main content cards.

### 4. Form / Create / Edit Flows

- Group fields into labeled sections with `24px` internal spacing.
- Avoid giant single-column whitespace. Product forms should feel compact but breathable.
- Use one dominant primary action and one secondary path.
- Inline validation should be clear, color-coded, and text-first rather than icon-heavy.

### 5. Settings / Admin Screens

- Reduce accents even further here.
- Let the experience feel almost monochrome except for focus, success, danger, and the primary save action.
- Use grouped cards or categorized lists instead of long undifferentiated forms.

---

## Component Patterns

### Buttons

| Variant | Recommendation |
|---------|----------------|
| **Primary** | `#533AFD` background, white text, `4px` radius, `40px` height desktop, hover to `#4032C8` |
| **Secondary** | White or transparent fill, `1px solid #E5EDF5`, dark text, quiet hover tint |
| **Ghost / Tertiary** | Text-first action with hover opacity or pale neutral background |
| **Destructive** | Keep neutral structure, introduce `#F3432A` in text or fill only when the action is truly destructive |

### Inputs and Selects

- Height: `40px` default, `44px` on mobile, `32px` only for dense desktop filter bars
- Radius: `4px`
- Border: `1px solid #E5EDF5`
- Background: white
- Focus style: `2px` outline plus quiet offset or halo using `#9A9AFE`
- Error style: border and helper text in `#F3432A`, but keep layout calm

### Search, Filters, and Segmented Controls

- Filters should live in a quiet toolbar strip above tables or boards.
- Search inputs stay compact and neutral; avoid heavy inset shadows.
- Segmented controls can use a brand-tinted active pill within a neutral rail.

### Cards and Panels

- Background: `#FFFFFF`
- Border: `1px solid #E5EDF5`
- Radius: `6px` standard, `8px` for summary and feature-like panels
- Shadow: use selectively for hover or layered overlays, not every card
- Accent bars are allowed only for featured insights, not routine operational cards

### Tables and Data Blocks

- Header treatment: light neutral background or white with strong bottom divider
- Row divider style: `1px` quiet border
- Hover state: pale neutral or very soft brand tint
- Dense numeric alignment: right-align currency, counts, and rates
- Sticky table headers should feel like Stripe's sticky nav logic: calm surface, measured shadow, precise dividers

### Badges and Status

- Keep the existing badge DNA: tiny, compact, restrained
- Default form: pill or slightly softened rectangle
- Use product accent families for category badges
- Use semantic colors for system status:
  - success: `#00B261`
  - error: `#F3432A`
  - warning: `#F9B900`
  - info / neutral: brand or muted slate

### Charts and Metrics

- Use white cards with restrained axes and subtle grid lines
- Bring Stripe's accent families into series colors, but cap the number of vivid colors on one chart
- Favor line, bar, and compact area charts over glossy data visualizations
- Large gradients should stay inside chart fills or tiny highlight ribbons, not entire dashboards

### Modals, Drawers, and Overlays

- Use white surfaces with `6px` or `8px` radius
- Apply medium shadow tier, not black-heavy depth
- Backdrop should be dim, neutral, and unobtrusive
- Drawers work well for edits and side-detail views because they match Stripe's layered but quiet surface logic

### Empty, Loading, and Error States

- Empty states should use soft illustration or icon accents, not full marketing hero compositions
- Skeletons should be pale neutral blocks with subtle animation
- Error states should keep the surface calm and let message clarity do the work
- Success confirmations can use tiny color chips or a single success badge, not celebratory motion

---

## Platform Notes

### Desktop

- Optimize for information density and rapid scanning.
- Sidebar, table headers, and filter bars should feel exact and engineered.
- Multi-column detail views are appropriate when metadata matters.

### Mobile

- Collapse side metadata into accordion or stacked sections.
- Use `44px` minimum touch targets for major controls.
- Replace wide tables with stacked row cards or horizontally scrollable subviews only when necessary.
- Use fewer accent colors per screen than desktop.

---

## Design Tokens / CSS Mapping

```css
:root {
  --app-bg: #f8fafd;
  --app-surface: #ffffff;
  --app-surface-subtle: #f8fafd;
  --app-border: #e5edf5;
  --app-text: #061b31;
  --app-text-soft: #50617a;
  --app-text-muted: #64748d;
  --app-brand: #533afd;
  --app-brand-hover: #4032c8;
  --app-focus: #9a9afe;
  --app-success: #00b261;
  --app-error: #f3432a;
  --app-warning: #f9b900;
  --app-radius-control: 4px;
  --app-radius-panel: 6px;
  --app-radius-panel-soft: 8px;
  --app-shadow-panel: 0 4px 8px 0 rgba(6, 27, 49, 0.06), 0 6px 22px 0 rgba(6, 27, 49, 0.08);
}
```

---

## Example Screen Recipes

### Dashboard

```text
Top bar with global search and workspace context
Sidebar | KPI row (3-5 cards)
Sidebar | Revenue / payment chart + operational summary
Sidebar | Recent transactions table + activity feed
```

### Detail Screen

```text
Top bar
Object header: title + status + actions
Main column: timeline, attributes, notes
Side column: metadata, linked entities, audit info
```

### Settings Screen

```text
Settings nav
Page title and helper copy
Grouped cards: account, team, billing, notifications
Primary save action at section end or sticky footer
```

---

## Summary of Key App Design Rules

- Keep the neutral foundation dominant; color is an accent, not the base surface.
- Use `#533AFD` for primary action, active state, and focus-adjacent emphasis, not for broad page backgrounds.
- Preserve Stripe's fine-border discipline. Prefer `1px` structure over constant shadow.
- Let app hierarchy come from spacing, grouping, and type scale more than from heavy weight jumps.
- Reserve gradients for charts, category accents, onboarding, and occasional featured insights.
- Keep buttons and fields small, exact, and calm. Default control radius is `4px`.
- Most cards should be white with quiet borders; only elevated or interactive panels need stronger shadow.
- Product accent families should classify information, not decorate random surfaces.
- Dashboard screens should feel dense but never cramped: build with `8 / 16 / 24 / 32` spacing steps.
- Tables should be precise, right-align numbers, and use restrained hover/selection treatment.
- Mobile should simplify structure, not reinvent the visual language.
- If a pattern was not directly visible in Stripe's product UI, keep it conservative and say it was inferred.
