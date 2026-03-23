# ui-style-extractor

Extract a website's UI style into reusable Markdown guides and validation demos for AI-generated pages.

`ui-style-extractor` turns live sites, screenshots, and harvested CSS into AI-usable style guides. Instead of cloning a page, it extracts the visual system behind it: colors, typography, spacing, layout rules, components, motion, and the non-obvious design constraints that make new pages still feel native to the source.

This repository now also includes an installable skill in [ui-style-extractor/](./ui-style-extractor/) that works for both Codex and Claude Code.

## Why This Exists

You see a website with a design you love. You want that *feel* for your own project. Your options:

1. **Screenshot-to-code tools** — clone the exact page, but you can't build *new* pages in that style
2. **Hire a designer** — expensive and slow for a side project
3. **Wing it** — pick similar colors and fonts, end up with a pale imitation

`ui-style-extractor` takes a different path: extract the **design system**, not the page. Then use that system to generate original pages in the same visual language.

## How It Works

```
 Target Website          Style Guide (.md)           Your New Page
┌──────────────┐       ┌──────────────────┐       ┌──────────────────┐
│              │       │ Colors           │       │                  │
│  Analyze     │──────▶│ Typography       │──────▶│  AI generates    │
│  visuals     │       │ Spacing          │       │  new pages using │
│              │       │ Components       │       │  the style guide │
│              │       │ Shadows          │       │                  │
│              │       │ Tailwind mapping │       │                  │
└──────────────┘       └──────────────────┘       └──────────────────┘
```

### Three Steps

1. **Extract** — Analyze a target website and document its design system into a structured `.md` file using the [template](./style-guide-template.md)
2. **Generate** — Feed the style guide to an AI (Claude, GPT, etc.) and ask it to build a page in that style
3. **Validate** — Compare the generated page against the original to verify fidelity

## What You Get

- An installable cross-agent skill in [ui-style-extractor/](./ui-style-extractor/)
- A reusable style-guide template
- Two public end-to-end examples with reference vs generated screenshots
- Raw extraction assets for a more complex design-system case (`stripe/`)

## Skill Installation

The canonical skill lives in [ui-style-extractor/](./ui-style-extractor/).

### Codex

1. Copy `ui-style-extractor/` into `${CODEX_HOME:-$HOME/.codex}/skills/`
2. Invoke it with `$ui-style-extractor` or ask Codex to extract a site's design system into a Markdown style guide

### Claude Code

1. Copy `ui-style-extractor/` into your project `.claude/skills/` directory or into `~/.claude/skills/`
2. Invoke it from Claude Code as `/ui-style-extractor` or ask Claude to extract a site's design system into a Markdown style guide

This repository also includes a project-local wrapper at [`.claude/skills/ui-style-extractor/`](./.claude/skills/ui-style-extractor/) so the same skill is immediately discoverable when you open this repo in Claude Code.

### What the skill includes

- `SKILL.md` — trigger description and workflow for extraction + validation
- `assets/style-guide-template.md` — reusable blank template
- `references/extraction-workflow.md` — detailed extraction method
- `references/quality-bar.md` — shipping checklist for guides and demos
- `agents/openai.yaml` — Codex/OpenAI UI metadata for skill pickers

## Examples

### 99% Off Sale → Product Page

Extracted the extreme high-contrast design from Cards Against Humanity's [99percentoffsale.com](https://www.99percentoffsale.com/) — a two-color (`#FF0000` + `#FFFFFF`), zero-radius, zero-shadow, ultra-bold condensed style.

| Style Guide | Generated Page |
|-------------|----------------|
| [99percent-ui-style.md](./99percent/99percent-ui-style.md) (860 lines) | [demo.html](./99percent/demo.html) |

Reference vs generated:

<table>
  <tr>
    <td width="50%"><strong>Reference</strong></td>
    <td width="50%"><strong>Generated</strong></td>
  </tr>
  <tr>
    <td><img src="./99percent/ref-screenshot.png" alt="99percent reference screenshot" width="100%" /></td>
    <td><img src="./99percent/demo-top.png" alt="99percent generated screenshot" width="100%" /></td>
  </tr>
</table>

### Stripe Marketing UI → SaaS Landing Page

Extracted Stripe's neutral-first, gradient-accented marketing system from [stripe.com](https://stripe.com/) and documented the shared HDS tokens plus recurring marketing components.

| Style Guide | Generated Page |
|-------------|----------------|
| [stripe-ui-style.md](./stripe/stripe-ui-style.md) | [demo.html](./stripe/demo.html) |

Reference vs generated:

<table>
  <tr>
    <td width="50%"><strong>Reference</strong></td>
    <td width="50%"><strong>Generated</strong></td>
  </tr>
  <tr>
    <td><img src="./stripe/ref-viewport.png" alt="Stripe reference screenshot" width="100%" /></td>
    <td><img src="./stripe/demo-viewport.png" alt="Stripe generated screenshot" width="100%" /></td>
  </tr>
</table>

Full-page validation screenshot: [stripe/demo-fullpage.png](./stripe/demo-fullpage.png)

## Style Guide Structure

Every style guide follows the same skeleton (see [template](./style-guide-template.md)):

| Section | What it captures |
|---------|-----------------|
| **Overview** | Design philosophy, key characteristics, overall vibe |
| **Color Palette** | Primary, secondary, semantic colors with hex/RGB and usage context |
| **Typography** | Font families, pairing strategy, full type scale, weight usage |
| **Spacing System** | Base unit, spacing scale, gaps, margins, padding patterns |
| **Layout & Containers** | Max widths, page structure diagram, grid/flex patterns |
| **Component Styles** | Buttons, cards, inputs, navigation — with CSS code |
| **Shadows & Elevation** | Shadow style, offset values, elevation hierarchy |
| **Animations & Transitions** | Duration, easing, hover/focus behaviors |
| **Border Radius** | Radius scale and per-component values |
| **Borders** | Width, style, color, and where borders appear |
| **Tailwind CSS Mapping** | Ready-to-use Tailwind config or utility classes |
| **Example Component Code** | Copy-pastable reference implementations |
| **Summary of Key Design Rules** | 15-20 non-negotiable rules for staying on-brand |

## Getting Started

### Use an existing style guide

1. Pick a style guide from the [examples](#examples)
2. Open your AI assistant (Claude, ChatGPT, Cursor, etc.)
3. Paste the style guide as context
4. Ask it to build a page: *"Build a pricing page using this style guide"*

### Create your own style guide

1. Copy [style-guide-template.md](./style-guide-template.md)
2. Analyze your target website (DevTools → inspect colors, fonts, spacing, components)
3. Fill in each section of the template
4. Use the completed guide to generate pages

> **Tip**: You can also ask an AI to help fill the template. Give it screenshots of the target site plus the blank template, and ask it to extract the design system.

## Project Structure

```
ui-style-extractor/
├── README.md                          # Project overview and usage
├── LICENSE                            # MIT license
├── ui-style-extractor/                # Canonical shared skill (Codex + Claude)
│   ├── SKILL.md
│   ├── agents/openai.yaml
│   ├── assets/style-guide-template.md
│   └── references/
├── .claude/skills/ui-style-extractor/ # Project-local Claude discovery wrapper
├── style-guide-template.md            # Repo-level editable template source
├── 99percent/
│   ├── 99percent-ui-style.md          # Example: 99% Off Sale design system
│   └── demo.html                      # Example: generated product page
├── stripe/
│   ├── stripe-ui-style.md             # Example: Stripe marketing system
│   ├── demo.html                      # Example: generated validation page
│   └── demo-viewport.png              # Validation screenshot used in README
```

## FAQ

**Can I install this as a Codex or Claude Code skill?**

Yes. Copy [ui-style-extractor/](./ui-style-extractor/) into your Codex or Claude skills directory. The same canonical skill folder works for both; this repo's [`.claude/skills/ui-style-extractor/`](./.claude/skills/ui-style-extractor/) folder is only a local project wrapper for Claude discovery.

**Why only two public examples?**

Because the goal of the first release is to prove range, not exhaustiveness. `99percent` shows an extreme, minimal style; `Stripe` shows a tokenized, enterprise marketing system.

**Why Markdown files instead of Figma/JSON tokens?**

Markdown is the universal context format for LLMs. Every AI assistant can read it, no plugins needed. It's also human-readable and easy to version control.

**How accurate are the generated pages?**

With a thorough style guide (1000+ lines), AI can achieve very high fidelity — correct colors, typography, spacing, and component behaviors. The "Summary of Key Design Rules" section is especially important for catching subtle patterns.

**Can I use this with Tailwind / React / Vue / etc.?**

Yes. The style guides include Tailwind CSS mappings and framework-agnostic CSS. The AI can target any framework when generating pages.

**Is this for cloning websites?**

No. This extracts *design systems*, not content. You're learning the visual language — colors, typography, spacing patterns — and applying it to your own original content. Think of it like learning a band's musical style vs. covering their songs.

## License

[MIT](./LICENSE)
