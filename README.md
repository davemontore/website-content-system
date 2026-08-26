# Website Content System

Website Content System is a Codex Agent Skill that decides what a webpage must help a visitor understand or do before it starts writing.

It can plan, draft, edit, and audit informational pages, navigation, documentation, instructions, interface text, editorial content, SEO metadata, trust content, landing pages, and conversion copy. It uses different writing rules for different jobs instead of treating every web page as a sales page.

## What problem it solves

A generic request to “write website copy” often produces the same pattern: a dramatic headline, a vague promise, several promotional sections, and a call to action. That structure can be useful for a genuine offer, but it is a poor fit for a museum page, public guide, archive, help article, navigation label, form error, or setup instruction.

Website Content System starts by asking four practical questions:

1. What kind of surface is this?
2. What is the page's primary job?
3. What does the visitor need to know or do?
4. What verified facts and constraints are available?

The answers determine the hierarchy, content types, tone, and review criteria.

## The eight page jobs

| Page job | What the visitor should leave able to do |
|---|---|
| Inform | Know an accurate fact, explanation, or state of affairs |
| Orient | Understand where they are and where relevant material lives |
| Teach | Understand a concept or carry out a process |
| Enable | Complete an action and recover from a problem |
| Establish trust | Judge credibility from specific evidence |
| Explore | Discover related material without being pushed toward one outcome |
| Persuade | Reconsider a view on the strength of evidence and reasoning |
| Convert | Make an informed decision and take a specific, voluntary action |

A page can have a secondary job, but one job remains primary. If a public-service eligibility page must both inform and enable an application, eligibility information cannot be buried to make the application button more prominent.

## See the difference in the output

Suppose the verified source material says:

- Cedar Junction station opened in 1887.
- Passenger service ended in 1964.
- The station building now houses the municipal archive.
- The archive contains railway maps, photographs, and timetables.

A generic landing-page treatment might open with:

> Discover local history like never before
>
> Step into the past and uncover the stories that shaped our community.

That copy sounds enthusiastic, but it does not tell the visitor what the place is, why the date matters, or what they can find there.

For an informational page, Website Content System would produce something closer to:

> # Cedar Junction station and municipal archive
>
> Cedar Junction station opened in 1887 and served passenger trains until 1964. The station building now houses the municipal archive.
>
> ## What the archive contains
>
> The collection includes railway maps, photographs, and timetables documenting the station and local rail service.

The improvement is not merely a less promotional tone. The rewritten version answers the visitor's likely question, establishes the relevant dates, and creates a useful route into the collection.

The same decision model changes other kinds of content:

| Situation | Generic copy | Purpose-aware copy |
|---|---|---|
| A failed upload when the local file is safe | “Oops! Something went wrong.” | “Upload failed. Your file is still on this device. Check your connection and try again.” |
| A service whose verified facts are U.S. expatriate tax preparation, a licensed CPA, and a $200 initial consultation | “Unlock your financial freedom today.” | “U.S. tax preparation for Americans living abroad. Meet with a licensed CPA for a $200 initial consultation.” |
| A page audit | “Make the copy punchier.” | Identify the affected text, explain the visitor consequence, and show a concrete revision grounded in the available facts. |

The skill can still write persuasive or conversion-focused content. It activates those methods only when persuasion or conversion is part of the brief, and it does not invent proof, urgency, testimonials, credentials, or guarantees.

## What the skill actually does

For a typical page, the skill:

1. Writes a one-sentence brief naming the page, audience, primary job, and useful outcome.
2. Lists the visitor's questions in the order they need answers.
3. Turns those questions into the information hierarchy.
4. Chooses the right content type for each answer, such as a definition, label, instruction, comparison, example, source note, proof point, or call to action.
5. Drafts from verified material and marks evidence gaps instead of filling them with plausible-sounding claims.
6. Audits accuracy, coverage, hierarchy, clarity, and the criteria specific to the page's job.

The requested deliverable controls the output. A full page may include a brief, hierarchy, draft, and open evidence questions. A button-label request may need only the label and one sentence of context. An audit leads with prioritized findings and concrete fixes rather than silently replacing the whole page.

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

The portable entrypoint is [skills/website-content/SKILL.md](skills/website-content/SKILL.md).

## Use the skill

Invoke it directly with `$website-content`:

```text
Use $website-content to plan an informational page about the history of a railway station.
```

```text
Use $website-content to audit this onboarding flow. Prioritize task failures and show a concrete revision for every finding.
```

```text
Use $website-content to rewrite this service page. Establish trust first and treat conversion as the secondary job.
```

```text
Use $website-content to draft the title and description for this article after reviewing its content.
```

The skill asks only for missing information that would materially change the result. When a reasonable assumption is safe, it states the assumption and proceeds.

## Standards that always apply

Whatever the page job, the skill uses this priority order:

1. Tell the truth and represent evidence accurately.
2. Help the visitor understand or complete the task.
3. Include information that serves the page's job.
4. Use personality where the situation can carry it.
5. Improve discoverability without weakening the first four priorities.

It preserves meaningful voice, but removes writing that only announces importance, makes unsupported quality claims, creates fake urgency, or delays the answer. It also keeps qualifications beside the claims they limit and warnings before the actions they govern.

## How the skill is organized

The entrypoint contains the shared workflow and loads only the references relevant to the current task:

| File | Responsibility |
|---|---|
| [`SKILL.md`](skills/website-content/SKILL.md) | Classifies the request, routes to the relevant guidance, and defines the drafting workflow |
| [`page-jobs.md`](skills/website-content/references/page-jobs.md) | Distinguishes the eight jobs and resolves conflicts on hybrid pages |
| [`universal-standards.md`](skills/website-content/references/universal-standards.md) | Sets the evidence, hierarchy, language, voice, and accessibility rules used everywhere |
| [`informational-content.md`](skills/website-content/references/informational-content.md) | Guides informational, orienting, and exploratory pages |
| [`ux-and-instructions.md`](skills/website-content/references/ux-and-instructions.md) | Guides labels, buttons, errors, recovery messages, and procedural instructions |
| [`trust-and-persuasion.md`](skills/website-content/references/trust-and-persuasion.md) | Adds evidence-led trust, persuasion, and conversion methods when the page actually needs them |
| [`search-and-metadata.md`](skills/website-content/references/search-and-metadata.md) | Handles search intent, titles, descriptions, internal links, and structured discoverability |
| [`audit.md`](skills/website-content/references/audit.md) | Reviews accuracy and task coverage before hierarchy, sentence clarity, and purpose-specific quality |

## Boundaries

The skill does not:

- invent facts, numbers, quotations, testimonials, credentials, deadlines, or scarcity
- force informational or interface content into a landing-page template
- optimize for keywords at the expense of accuracy or usefulness
- treat every stylistic preference as a universal writing law
- present criticism without showing what a better result looks like

Missing evidence remains an explicit question or placeholder for the author to resolve.

## Source principles, not copied repositories

This project is an original synthesis informed by open-source UX writing, plain-language editing, SEO content, and conversion-copy projects. It does not bundle upstream swipe files, templates, brand voices, examples, or blocklists.

[THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) records each source, its license, the principle it informed, and the boundary used during adaptation. A CC BY-NC source reviewed during the original survey is credited there but was not adapted into this project.

## License

Website Content System is available under the [MIT License](LICENSE).
