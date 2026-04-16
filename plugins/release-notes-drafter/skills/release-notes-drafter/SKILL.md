---
name: release-notes-drafter
description: Turn git diffs, pull requests, issue lists, and rough notes into concise release notes, changelog entries, and stakeholder update bullets. Use when the user wants release notes, changelog copy, "what changed" summaries, or audience-specific product update messaging from engineering work.
license: MIT
metadata:
  author: Andrew Enns
  version: "0.1.0"
---

# Release Notes Drafter

Translate implementation detail into accurate user-facing update copy. The job is not to restate code changes. The job is to explain what changed, who it affects, and any meaningful caveats without inventing impact.

## Inputs

Use the strongest evidence available, in this order:

1. Merged PR description, issue, or ticket
2. Git diff and changed-file list
3. Test results, screenshots, or QA notes
4. User-provided rough notes

If important details are missing, state the uncertainty plainly instead of guessing.

## Workflow

1. Identify the audience.
   Customer-facing notes should emphasize outcomes and visible behavior.
   Internal notes can mention rollout details, migration steps, or operational risk.
   Technical notes can mention APIs, configuration, or dependency changes.

2. Extract only meaningful changes.
   Include features, fixes, behavior changes, migrations, deprecations, and notable performance or reliability improvements.
   Exclude pure refactors, renames, formatting, or dependency churn unless they materially affect users or operators.

3. Separate signal from implementation detail.
   Replace file names, function names, and framework jargon with product language unless the audience is explicitly technical.

4. Group changes into a clean structure.
   Prefer `Added`, `Improved`, `Fixed`, `Deprecated`, and `Internal`.
   Omit empty sections.

5. Tighten the copy.
   One bullet should describe one change.
   Lead with the effect, not the implementation.
   Keep caveats concrete and verifiable.

## Style Rules

- Do not claim impact that is not supported by the evidence.
- Do not say a change is "faster", "more reliable", or "more secure" unless the source material supports that claim.
- Do not expose internal filenames, class names, or branch names in customer-facing notes.
- Prefer plain language over marketing language.
- Use consistent verb tense within one output.
- If a change is invisible to end users, either omit it or place it under `Internal`.

## Output Patterns

Choose the lightest format that fits the request.

### Changelog Bullets

Use short bullets for release notes, version history, or app-store style updates.

Example:

- Added CSV export for filtered reports.
- Fixed an issue where session timeouts could interrupt large uploads.
- Improved admin search results when filtering by status and assignee.

### Summary Paragraph

Use a short paragraph when the user wants one block of copy for a release post, email intro, or handoff note.

Example:

This release improves reporting and admin workflows. Teams can now export filtered reports to CSV, admins should see more consistent search results, and a timeout issue affecting large uploads has been fixed.

### Stakeholder Update

Use three parts:

1. What changed
2. Who is affected
3. Anything to watch

Example:

What changed: Reporting exports are now available for filtered views, and the admin search flow has been cleaned up.
Who is affected: Operations and support teams using the admin dashboard.
Anything to watch: No migration is required, but support should expect questions about the new CSV option.

## Quality Check

Before finalizing, verify:

- Every claim traces back to the diff, PR, or notes.
- The output matches the intended audience.
- Each bullet is understandable without reading the code.
- The most important user-visible change appears first.
