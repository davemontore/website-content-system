---
title: Pair content criticism with concrete alternatives
date: 2026-08-27
category: documentation-gaps
module: Website Content System
problem_type: documentation_gap
component: documentation
severity: medium
applies_when:
  - Demonstrating a writing or content-design principle with a weak counterexample
  - Auditing content and explaining why an existing passage fails
  - Teaching a recommendation whose practical effect is not obvious from prose alone
tags: [before-and-after, content-audit, documentation, examples, fact-grounding]
---

# Pair content criticism with concrete alternatives

## Context

A negative example can establish what a writing system rejects, but it does not show the result the system should produce. Readers are left to infer whether the desired change is structural, factual, tonal, or merely a matter of taste.

For a purpose-aware content system, that ambiguity is especially damaging. The system is meant to turn a page's job, visitor questions, and verified facts into an information hierarchy. Its documentation should make that transformation visible.

The repository README now supplies a verified fact set, shows a generic promotional treatment, explains the visitor information it withholds, and follows it with a purpose-aware rewrite ([README.md](../../../README.md)). The behavioral rule is also encoded in the skill entrypoint and audit contract, not left only in explanatory prose.

## Guidance

When teaching or reviewing content quality:

1. State the facts the proposed improvement is allowed to use. A before-and-after comparison is trustworthy only when the “after” can be traced to supplied evidence.
2. Show the weak version, then name its visitor-facing defect precisely: missing identity, missing dates, an unclear next action, hidden limits, or another failure tied to the page's job.
3. Pair the diagnosis with a publishable alternative. The replacement should demonstrate the intended hierarchy and content type, not merely use a different tone.
4. If the better version requires unavailable evidence, use a clearly marked placeholder or ask an evidence question instead of inventing the answer.
5. Keep the correction proportional to the request. A narrow audit finding may need one corrected heading, sentence, label, or recovery message rather than a silent full-page rewrite.

Apply this rule at both workflow and audit levels. The skill entrypoint requires a concrete improved alternative when it explains or audits a writing problem ([SKILL.md](../../../skills/website-content/SKILL.md)); the audit reference requires findings to include a concrete fix or rewritten example ([audit.md](../../../skills/website-content/references/audit.md)).

## Why This Matters

Criticism without a better version leaves the transformation untested. A concrete alternative exposes whether the recommendation actually answers the visitor's question, represents the evidence accurately, and fits the page's primary job.

This also prevents “less promotional,” “clearer,” or “punchier” from becoming vague style instructions. A useful revision demonstrates an observable improvement: it supplies the missing fact, places a qualification beside the claim it limits, gives the next safe action, or changes the hierarchy to match the visitor's needs.

Fact-grounded alternatives also protect credibility. They make it harder to smuggle invented proof, urgency, credentials, or certainty into an example simply because the replacement sounds more polished.

## When to Apply

- Documentation contrasts good and bad writing.
- An audit calls content vague, promotional, confusing, poorly ordered, or mismatched to its page job.
- Editorial feedback asks for a structural change whose intended result is not obvious.
- A proposed rewrite depends on incomplete source material.

The pattern does not require a full-page rewrite. Match the size of the improved example to the size of the criticism.

## Examples

### Informational page

Given verified dates, current use, and collection contents for a railway station, replace a promotional invitation with an opening that names the station, states the relevant chronology, and tells visitors what the archive contains. The revised README demonstrates this transformation using the same fact set for both the diagnosis and the replacement.

### Interface recovery message

When a failed upload leaves the local file safe:

- Weak: “Oops! Something went wrong.”
- Better: “Upload failed. Your file is still on this device. Check your connection and try again.”

The improved version identifies the failure, states what was preserved, and gives a recovery action.

### Audit finding

Do not write only “Make the copy punchier.” Identify the affected text, connect the defect to the visitor's task, explain the consequence, and provide a concrete fact-grounded revision. If the correct revision depends on missing evidence, state the evidence question and use a marked placeholder.

## Related

- [Website Content System README](../../../README.md)
- [Website Content skill entrypoint](../../../skills/website-content/SKILL.md)
- [Content audit guidance](../../../skills/website-content/references/audit.md)
