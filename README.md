# Website Content System

A purpose-aware Agent Skill for writing useful website content without turning every page into a sales page.

## Write for the page's actual job

Ask an AI to “write website copy” and it will often reach for the same landing-page language, even when the website is an archive, guide, museum, public resource, or software interface.

Website Content System starts somewhere more useful: what should this page help the visitor understand or do?

It classifies the page before choosing a writing method:

| Page job | What the visitor needs |
|---|---|
| Inform | An accurate answer or explanation |
| Orient | A clear sense of where they are and where to go |
| Teach | Enough understanding to learn or complete a process |
| Enable | Clear interface language for taking an action or recovering from a problem |
| Establish trust | Specific evidence for deciding whether something is credible |
| Explore | Useful paths through related material |
| Persuade | Evidence and reasoning for reconsidering a view |
| Convert | The information needed to take a specific, voluntary action |

Hybrid pages get one primary job and one secondary job. When those goals conflict, the primary job wins.

## The difference in practice

For an informational page, the skill will not manufacture a hero such as:

> Discover local history like never before

It will identify the visitor's question, put the clearest answer first, and organize the evidence in the order needed to understand it.

For a service or product page, it can still use persuasive techniques. Those techniques activate only when persuasion or conversion is part of the brief, and every claim still needs evidence.

The workflow is:

```text
page job
  -> visitor questions
  -> information hierarchy
  -> appropriate content types
  -> draft
  -> usefulness and accuracy audit
```

## Install for Codex

Clone the repository:

```bash
git clone https://github.com/davemontore/website-content-system.git
```

Copy `skills/website-content` into your Codex skills directory.

macOS or Linux:

```bash
mkdir -p ~/.codex/skills
cp -R website-content-system/skills/website-content ~/.codex/skills/
```

Windows PowerShell:

```powershell
New-Item -ItemType Directory -Force "$env:USERPROFILE\.codex\skills" | Out-Null
Copy-Item -Recurse "website-content-system\skills\website-content" "$env:USERPROFILE\.codex\skills\website-content"
```

The portable skill entrypoint is [skills/website-content/SKILL.md](skills/website-content/SKILL.md).

## Use the skill

Invoke it directly with `$website-content`:

```text
Use $website-content to plan an informational page about the history of a railway station.
```

```text
Use $website-content to audit this onboarding flow for unclear labels and dead ends.
```

```text
Use $website-content to rewrite this service page. Establish trust first and treat conversion as the secondary job.
```

```text
Use $website-content to draft the title and description for this article after reviewing its content.
```

The skill supports planning, drafting, editing, and auditing. It asks only for missing information that would materially change the result. Unknown evidence remains an open question rather than becoming an invented claim, statistic, quote, credential, or deadline.

## What always applies

Whatever the page job, the skill keeps the same priority order:

1. Tell the truth and represent evidence accurately.
2. Help the visitor understand or complete the task.
3. Include information that serves the page's job.
4. Use personality where the situation can carry it.
5. Improve discoverability without weakening the first four priorities.

It also distinguishes between page content, navigation, interface language, reference material, instructions, editorial writing, and marketing copy. They may appear on the same website, but they should not all sound like advertising.

## How the skill is organized

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

The entrypoint contains the shared workflow and routes the agent to only the references needed for the current task.

## Source principles, not copied repositories

This project is an original synthesis informed by open-source UX writing, plain-language editing, SEO content, and conversion-copy projects. It does not bundle upstream swipe files, templates, brand voices, examples, or blocklists.

[THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) records each source, its license, the principle it informed, and the boundary used during adaptation. A CC BY-NC source reviewed during the original survey is credited there but was not adapted into this project.

## License

Website Content System is available under the [MIT License](LICENSE).
