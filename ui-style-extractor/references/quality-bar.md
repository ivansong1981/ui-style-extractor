# UI Style Extractor Quality Bar

Ship a guide only when it meets this bar.

## Style Guide Checklist

- The top block names the source URL and the pages analyzed.
- Every major section is either populated or explicitly marked `Not observed` or `Not present`.
- Core colors, typography, spacing, layout, radius, borders, shadows, and motion are covered if visible in the source.
- Repeated values are promoted into system tokens; one-offs stay in component notes.
- Tailwind mapping is usable rather than purely decorative.
- Example component code is short enough to reuse directly.
- The final design-rules summary is specific, strict, and actionable.

## Evidence Checklist

- Token values come from CSS or computed styles whenever possible.
- Screenshot-only judgments are clearly framed as inference.
- The guide avoids pretending to know unavailable data.
- Secondary pages were checked when the homepage alone was insufficient.

## Demo Checklist

- The content is original even if the visual language is borrowed.
- The page reuses the extracted system instead of loosely "inspired by" styling.
- Responsive behavior is plausible for the source system.
- Major states such as hover, active, or inverted sections are represented when they matter.
- A side-by-side screenshot comparison would show family resemblance immediately.

## Failure Modes

Do not ship the guide yet if any of these are true:

- Colors are approximate even though inspectable CSS exists.
- The guide mixes multiple visual modes into one flattened palette.
- Typography notes describe mood but omit actual sizes, weights, or spacing patterns.
- The summary rules are too generic to constrain another model.
- The demo looks like a generic landing page with borrowed colors.
