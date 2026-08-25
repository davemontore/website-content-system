# Website Content System

A purpose-aware writing skill for websites.

Most website-writing systems assume every page should sell. This one starts by asking what the page must help a visitor do. It then applies the right rules for informational content, orientation, instructions, interface language, trust-building, exploration, persuasion, or conversion.

The project is designed as a portable Agent Skill for Codex and other tools that support `SKILL.md` packages.

## What it changes

The skill routes work through this sequence:

`page job -> visitor questions -> information hierarchy -> content type -> draft -> usefulness and accuracy audit`

Its default priorities are:

1. Truth
2. Understanding and task completion
3. Usefulness
4. Appropriate personality
5. Discoverability
6. Persuasion, only when the page actually needs it

## Project structure

```text
skills/website-content/
|-- SKILL.md
|-- agents/openai.yaml
`-- references/
    |-- audit.md
    |-- informational-content.md
    |-- page-jobs.md
    |-- search-and-metadata.md
    |-- trust-and-persuasion.md
    |-- universal-standards.md
    `-- ux-and-instructions.md
```

The entrypoint stays compact. It loads only the reference files relevant to the current page.

## Use locally

Copy `skills/website-content` into the skills directory used by your agent. For Codex, the usual destination is:

```text
~/.codex/skills/website-content
```

Then invoke it directly with `$website-content`, or ask for website content work in ordinary language.

Example requests:

- Use `$website-content` to plan an informational page about Hua Hin's railway history.
- Audit this onboarding flow for unclear labels and dead ends.
- Rewrite this service page, but keep trust ahead of conversion pressure.
- Draft metadata for this article after the page content is settled.

## Design choices

- Page purpose controls the writing method.
- Content, navigation, interface language, reference material, instructions, editorial writing, and marketing copy are distinct surfaces.
- Claims need evidence. Missing proof becomes a question or a clearly marked placeholder, never an invented fact.
- Search optimization cannot overrule accuracy, clarity, or the page's real job.
- Conversion frameworks are optional tools, not universal templates.

## Sources and license

This is an original synthesis informed by several open-source writing projects. See [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) for source links, licenses, and the boundaries used during adaptation.

The Website Content System is released under the MIT License. See [LICENSE](LICENSE).
