# v0.1.0 - Initial public release

`ui-style-extractor` extracts a website's visual system into reusable Markdown guides and optional validation demos for AI-generated pages.

## What is included

- Canonical shared skill for Codex and Claude Code
- Public style-guide template
- Two public examples:
  - `99percent`: extreme, high-contrast minimal system
  - `stripe`: tokenized enterprise marketing system
- Branding assets for open-source release
- English and Chinese README

## Why this exists

Most screenshot-to-code tools can copy a page, but they do not help you build new pages in the same style. This project focuses on extracting the design rules behind a site so an AI can keep generating original pages in that visual language.

## Repo structure

- `ui-style-extractor/`: canonical skill
- `.claude/skills/ui-style-extractor/`: project-local Claude discovery wrapper
- `99percent/`: public example and validation demo
- `stripe/`: public example, validation demo, and extraction assets
- `style-guide-template.md`: reusable blank template

## Notes

- Public v1 intentionally ships with two examples only.
- Private examples are not included in this repository.
- The skill is designed to document systems, not clone copyrighted site content.
