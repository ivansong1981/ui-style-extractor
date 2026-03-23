---
name: ui-style-extractor
description: Extract visual design systems from existing websites into reusable markdown style guides and optional validation pages. Use when Codex needs to analyze a live site, screenshots, or harvested CSS to document colors, typography, spacing, layout, components, motion, and design rules, or when generating new UI that should match a reference site's visual language without copying its content.
---

# UI Style Extractor

Extract a site's visual language into a reusable Markdown guide, then use that guide to build original pages that still feel native to the source system.

## Workflow

1. Decide the output first.
   - Produce only a style guide when the user wants documentation or prompt context.
   - Produce a style guide plus demo page when the user wants validation.
2. Build the evidence set before writing.
   - Prefer production CSS, design tokens, computed styles, and real DOM structure over screenshot-only guesses.
   - Inspect at least the homepage and one secondary page unless the user gives a tighter scope.
   - Use screenshots to capture composition, density, rhythm, imagery treatment, and overall mood.
3. Duplicate `assets/style-guide-template.md` and fill it section by section.
   - Use exact values where possible.
   - If a section is unsupported by evidence, write `Not observed` or `Not present` instead of inventing details.
4. Distill repeated patterns into system rules.
   - Promote only repeated values into palette, spacing, radius, shadow, or motion tokens.
   - Keep one-off values in component notes unless they clearly define the brand language.
5. Generate the demo only after the guide is stable.
   - Change the copy, product, and brand-specific content.
   - Preserve the design grammar: typography hierarchy, spacing rhythm, component treatment, and motion behavior.
6. Validate against the reference.
   - Compare screenshots side by side.
   - Tighten the guide if the generated page drifts from the source.

## Extraction Rules

- Prefer exact CSS values over visual estimation.
- Treat screenshots as supporting evidence, not the primary source of tokens.
- Record which pages were analyzed near the top of the guide.
- Separate global rules from component-local exceptions.
- Call out uncertainty explicitly when the source is ambiguous.
- If the site has multiple modes or contrasting sections, document each mode rather than averaging them together.
- Keep the final "Summary of Key Design Rules" strict enough that another model can follow it without re-reading the entire guide.

## Demo Rules

- Build original content in the extracted style; do not reproduce the reference site's copy wholesale.
- Reuse the extracted tokens faithfully before adding custom flourishes.
- Match the site's density and alignment logic, not just its colors and fonts.
- Include only enough interactivity to demonstrate the system.
- If fidelity depends on animation, gradients, or texture, implement them rather than omitting them.

## Output Conventions

- Prefer `<site>/<site>-ui-style.md` for guide files when working in a multi-example repo.
- Prefer `<site>/demo.html` for validation pages.
- Keep reference captures close to the example, such as `ref-viewport.png` or `ref-fullpage.png`.
- Keep guides in Markdown and keep component examples copyable.

## Resources

- Use `assets/style-guide-template.md` as the blank extraction template.
- Read `references/extraction-workflow.md` when you need the detailed page-selection and evidence-gathering workflow.
- Read `references/quality-bar.md` when deciding whether a guide or demo is complete enough to ship.
