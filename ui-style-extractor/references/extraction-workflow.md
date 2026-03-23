# UI Style Extraction Workflow

Use this workflow when creating a new site style guide from scratch.

## 1. Choose Scope

- Start with the homepage plus one or two secondary pages that show different component families.
- Expand scope only if the site visibly changes across product, pricing, docs, dashboard, or footer surfaces.
- If the user wants only one area, keep the guide honest about that narrower sample.

## 2. Build Evidence in the Right Order

Use this priority order:

1. Real CSS source or design-token files
2. Computed styles from rendered elements
3. DOM structure and layout behavior
4. Screenshots and visual comparison
5. Inference

Inference is acceptable for mood, art direction, and texture, but not for exact tokens when inspectable data exists.

## 3. Capture the Repeated System, Not Every Isolated Value

- Promote a value into the system only when it appears repeatedly or clearly anchors the brand.
- Keep rare values in the relevant component section.
- Distinguish between foundational tokens and page-specific flourishes.

Good examples of system material:

- Core text and background colors
- Accent colors used across sections
- Repeated radius values
- Shared shadow recipes
- Breakpoints and fluid sizing patterns
- Recurring button, card, and navigation treatments

Good examples of component-only notes:

- A single hero-only offset
- One decorative blend mode
- A one-off illustration size

## 4. Fill the Template Section by Section

For each section in `assets/style-guide-template.md`:

- Write exact values where the source supports them.
- Include short interpretation only after the hard data.
- Remove obviously irrelevant placeholder rows if they add noise.
- Write `Not observed` for missing categories instead of leaving blanks.

## 5. What to Extract by Section

### Overview and Philosophy

- Summarize the visual identity in plain language.
- Tie each high-level design principle back to visible implementation choices.

### Color

- Capture exact hex or RGB values.
- Document role, not just value: background, text, accent, border, semantic state.
- If the site uses dark sections or mode variants, document the swap explicitly.

### Typography

- Record actual rendered font families and fallbacks.
- Note where weights, letter-spacing, uppercase, or fluid sizing create hierarchy.
- Prefer actual heading and body patterns over abstract "looks modern" language.

### Spacing and Layout

- Identify whether spacing is tokenized, loose, or fluid.
- Document common gaps, padding pairs, max widths, and grid logic.
- Note whether the layout is mobile-first, desktop-first, or clamp-heavy.

### Components

- Focus on repeated component families: buttons, cards, links, nav, inputs, footers.
- Include concise CSS snippets only when they help another model reproduce the pattern.
- Capture hover, focus, and disabled states when present.

### Surface Details

- Radius, border width, shadow, opacity, texture, gradients, and z-index all matter if they shape the feel of the interface.
- Do not skip these sections for minimalist sites; "none" is still a rule.

### Tailwind Mapping and Example Code

- Write these after the system is stable.
- Map to the closest usable tokens rather than mirroring every raw value mechanically.

### Summary Rules

- End with non-negotiable design rules.
- Favor blunt guidance such as "Do not use blurred shadows" over vague style language.

## 6. Handle Uncertainty Explicitly

When the source is incomplete:

- State the observed range instead of guessing a single canonical token.
- Mark a value as inferred if it comes from screenshots rather than code.
- Say that a feature was not observed if you did not inspect a page type where it would normally appear.

## 7. Generate the Demo Page

Only start once the guide is good enough that another model could use it.

- Change product names, copy, and business context.
- Keep the extracted structure, hierarchy, and styling logic.
- Aim for a validation demo, not a production clone.

## 8. Validate the Result

Use direct screenshot comparison and answer these questions:

- Do the proportions feel the same?
- Is the type hierarchy correct?
- Are spacing and card density in the right range?
- Are radius, borders, and shadows faithful?
- Are motion and hover states materially similar?
- Does the page feel like it belongs to the same product family?

If the answer is no, update the guide first, then the demo.
