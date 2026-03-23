# App Adaptation Workflow

Use this workflow when the user wants the extracted website style to continue into an app UI.

## Positioning

An app guide is a **derived design artifact**, not a pure extraction artifact, unless the source also includes real product UI.

That distinction matters:

- Website tokens such as color, typography, spacing, radius, border, shadow, and motion can usually be inherited with high confidence.
- App shell decisions such as sidebar width, table density, mobile navigation, empty states, and form behavior are often adaptations.
- If the source does not expose product screens, say so clearly near the top of the document.

## Recommended Output Choices

Pick one of these before writing:

1. Website style guide only
2. Website style guide + website demo page
3. Website style guide + app UI style guide
4. Website style guide + website demo page + app UI style guide

Do not start the app guide before the website guide is stable.

## Adaptation Sequence

1. Finish the website guide first.
   - Lock the token layer: palette, typography, spacing, radius, border, shadow, motion, icon tone.
2. Define the product assumption.
   - Example: B2B dashboard, consumer utility, admin panel, collaboration tool.
   - Do not invent a highly specific business domain if the user did not ask for one.
3. Split rules into three buckets.
   - **Inherited**: directly carried over from evidence.
   - **Adapted**: tuned for app density and workflows.
   - **Inferred**: required product patterns that were not directly observed.
4. Choose the canonical screen set.
   - Prefer three to five: dashboard, list/table, detail, form, settings.
5. Reduce marketing-only styling.
   - Keep the brand tone.
   - Reduce oversized hero behavior, decorative gradients, and low-information whitespace unless they still support product clarity.
6. Write specific interaction rules.
   - Focus, selection, hover, loading, empty, success, warning, error, destructive.
7. End with strict app rules.
   - Another model should be able to generate a coherent app shell without guessing the visual system from scratch.

## Adaptation Heuristics

### Typography

- Keep the same type family when possible.
- Usually reduce the gap between marketing heading sizes and product heading sizes.
- Let hierarchy come from scale, spacing, and weight discipline rather than promotional drama.

### Color

- Preserve the source neutral system exactly if possible.
- Use the brand accent more sparingly than in marketing surfaces.
- Reserve gradients for onboarding, hero-like panels, charts, or highlights unless the source product UI proves heavier gradient usage.

### Layout

- Convert wide editorial layouts into operational shells.
- App surfaces need repeatable panel rhythms, tighter spacing, clearer dividers, and predictable scroll behavior.

### Components

- Prefer small radii and precise borders when the website already leans structured.
- Prefer app components that feel like a continuation of the website's token system, not a random SaaS kit.

### States

- If the source did not expose empty/loading/error patterns, create them conservatively.
- State styling should look native to the system, but the document must note that the exact behavior was inferred.

## Failure Modes

Do not ship the app guide yet if any of these are true:

- The app guide pretends inferred product patterns were directly extracted.
- The shell looks like a generic dashboard with only the source colors pasted on top.
- Marketing gradients and oversized type are copied into dense product contexts without adaptation.
- There is no explicit product assumption, so the guide drifts between admin, consumer, and analytics patterns.
- The summary rules are too generic to constrain another model.
