# Bootstrap prompt

This file is meant to be handed to Cursor (e.g. `@SETUP.md` in chat, or "follow SETUP.md") to
scaffold this repo's structure, slash commands, and grounding rule from scratch — for example
when starting this same workflow in a fresh empty folder for a future conference.

## Instructions for the agent

Create the following folders and files **exactly as specified below**, only if they don't
already exist. Do not touch or overwrite any existing content under `talks/`, `output/`, or an
already-customized `templates/role-profile.md` — this is idempotent scaffolding, not a reset.

### Folders

```
talks/
output/
templates/
.cursor/commands/
.cursor/rules/
```

### `README.md`

```markdown
# Config 2026 Notes

Local workspace for compiling and organizing conference talk takeaways against transcripts (and optional Notebook/OneNote notes).

## Folder structure

| Folder | Purpose |
|--------|---------|
| `talks/` | One subfolder per talk with `transcript.md` (+ optional `metadata.md`, slides/links). Figma-hosted "deep dive" sessions live under `talks/figma-deep-dives/<slug>/` instead of `talks/<slug>/`. |
| `output/` | Synthesized, role/team-specific summaries, one file per talk. Figma deep dive summaries are saved under `output/figma-deep-dive/<slug>.md`. |
| `templates/` | The output format reference (`synthesis-prompt.md`) and the per-engineer role profile (`role-profile.md`) |
| `.cursor/commands/` | Slash commands that drive the workflow (`/add-talk`, `/synthesize-talk`) |
| `.cursor/rules/` | Grounding/citation guardrails (`grounding.mdc`) applied automatically when editing `output/` |

## Workflow (run inside Cursor)

1. `/add-talk` — scaffold a new `talks/<slug>/` folder with `transcript.md` + `metadata.md`.
2. Paste the transcript into `talks/<slug>/transcript.md`.
3. `/synthesize-talk <slug>` — produce a role-tailored, transcript-grounded summary and save it to `output/<slug>.md` (or `output/figma-deep-dive/<slug>.md` for Figma Deep Dive sessions).

Each summary opens with a short header (talk title, source transcript path, and speakers/session link when known from `metadata.md`), followed by the lettered sections (A–F) defined in `templates/synthesis-prompt.md`.

The synthesis is tailored to whoever is described in `templates/role-profile.md`, and the grounding rule in `.cursor/rules/grounding.mdc` enforces the citation/labeling guardrails automatically.

## Grounding rules

- Transcript is the source of truth; Notebook notes are candidates to verify, not to assert from directly.
- Every takeaway must cite the talk and include a supporting quote (≤25 words) or the marker `[no direct quote available]`.
- Use these markers (defined in `.cursor/rules/grounding.mdc`) instead of guessing:
  - `[UNCLEAR IN TRANSCRIPT]` (with timestamp) — the transcript is unclear/incomplete, or references an onscreen visual/demo not captured in text
  - `[RELEVANCE UNCERTAIN — NEEDS CONFIRMATION]` — relevance to the role/team isn't certain
  - `[INFERRED]` — a reasonable action not directly stated in the transcript
  - `[NOT APPLICABLE]` — doesn't apply to the role/team
```

### `templates/role-profile.md`

```markdown
# Role profile

> This is the one file to customize. Describe who you are so synthesis
> is tailored to your role and team. Everything else in this repo stays the same.

## Role

<Describe your role, your team, what systems/domains you work in, and what you're
especially interested in getting out of these talks (e.g. AI workflows, specific
technical areas). This is the context every talk synthesis will be filtered through.>
```

### `templates/synthesis-prompt.md`

````markdown
# Synthesis prompt template

> Superseded by the `/synthesize-talk` slash command (`.cursor/commands/synthesize-talk.md`),
> which is the recommended way to run this. This file is kept as a readable, copy-pasteable
> reference of the same prompt. Both pull the role from `templates/role-profile.md`.

Use this in Cursor for each talk, one at a time.

---

## Role

You are compiling takeaways for my role and team. Read my role and team from `templates/role-profile.md` and tailor all relevance judgments and actions to it.

## Sources (only use these)

1. Transcript (source of truth): `talks/<talk-slug>/transcript.md`
   - Figma Deep Dive sessions are nested one level deeper: `talks/figma-deep-dives/<talk-slug>/transcript.md`
2. Metadata, if present (`talks/<talk-slug>/metadata.md`) — use only for the title, speakers, and session link in the output header. Never use it as a source of takeaways.

Do not use outside knowledge, prior context, or assumptions beyond what is explicitly stated in the transcript.

## Rules

- Do NOT assert facts not present in the transcript.
- If a takeaway's relevance to my role or team is uncertain, mark it: `[RELEVANCE UNCERTAIN — NEEDS CONFIRMATION]`.
- If the transcript is unclear, incomplete, or appears to reference onscreen visuals or demos not captured in text, mark it: `[UNCLEAR IN TRANSCRIPT]` and provide the relevant timestamp.
- Every takeaway must include a supporting quote (≤25 words) or `[no direct quote available]`.
- If the talk does not apply to my role or team, say so explicitly under **Not applicable** and stop there.

## Output format

Save the result to `output/<talk-slug>.md` (or `output/figma-deep-dive/<talk-slug>.md` for Figma Deep Dive sessions).

Start the file with a short header, then a `---` divider, then sections A–F:

```markdown
# <Talk title>

**Source:** `talks/<talk-slug>/transcript.md`
**Session:** [View session](<url>)   <!-- omit if not linked in metadata.md -->
**Speakers:** <names/roles>          <!-- omit if not listed in metadata.md -->

---
```

### A) Summary

A 3–5 sentence overview of what the talk covered, grounded only in the transcript. Include:
- The speaker's central argument or problem framing (what problem are they solving, and what is their core claim?)
- If applicable, the value this brought for the speaker (metrics, reduced pain points, improvements, etc.)

### B) Key points and tools

A bulleted list of the main points made. Call out any specific tools, frameworks, or products mentioned by name.

### C) Verified takeaways (with quotes)

Takeaways directly relevant to my role or team, each with a supporting quote or `[no direct quote available]`.

Look beyond surface-level matches. If a concept applies by analogy (e.g. a design pattern that maps to a backend or tooling pattern), include it, mark it `[ANALOGOUS]`, and explicitly state the analogous context for the team.

### D) Role and team actions (including AI enhancements)

Concrete follow-up items for my team. Only include if clearly supported by the transcript, or explicitly labeled `[INFERRED]`. 

### E) Not applicable / unclear items

Anything that does not apply to my role, could not be verified from the transcript, or was marked `[UNCLEAR IN TRANSCRIPT]`.

### F) Key terms reference

A table of any domain-specific terms, tools, or frameworks introduced in the talk that would be unfamiliar to a teammate who didn't attend. Format:

| Term | Definition |
| --- | --- |
| Example term | One-sentence definition grounded in how the speaker used it |

Omit this section if the talk introduced no terminology that needs explanation.
````

### `talks/README.md`

```markdown
# Talks

Create one folder per talk:

```
talks/
  designing-with-ai/
    transcript.md      # required
    metadata.md        # optional: title, speakers, date, session link
    slides/            # optional
```

Use a short slug for the folder name (lowercase, hyphens).
```

### `output/README.md`

```markdown
# Output

Save synthesized, verified takeaways here (one file per talk or themed roll-ups).
```

### `.cursor/rules/grounding.mdc`

````markdown
---
description: Grounding and citation guardrails for synthesizing talk transcripts into output/
globs: output/**/*.md
alwaysApply: false
---

# Grounding rules for talk synthesis

When producing or editing anything under `output/`, the talk transcript is the **only** source of truth.

- Do NOT assert facts that are not present in `talks/<slug>/transcript.md`. No outside knowledge, prior context, or assumptions.
- Every takeaway must include a supporting quote (≤25 words) or the literal marker `[no direct quote available]`.
- Tailor relevance and actions to the reader described in `templates/role-profile.md`.

## Required markers

Use these exact labels instead of guessing:

- `[UNCLEAR IN TRANSCRIPT]` — transcript is unclear/incomplete or references onscreen visuals/demos not in the text. Include the timestamp.
- `[RELEVANCE UNCERTAIN — NEEDS CONFIRMATION]` — relevance to the role/team is not certain.
- `[INFERRED]` — a reasonable action not directly stated in the transcript.
- `[NOT APPLICABLE]` — does not apply to the role/team.

If a talk does not apply to the role at all, say so under **Not applicable** and stop there.
````

### `.cursor/commands/add-talk.md`

````markdown
# Add a talk

Scaffold a new talk folder so every talk has a consistent structure.

## Input

A talk title and (optionally) a session link or transcript text. If I only paste a title, derive the slug.

## Steps

1. Derive a slug: lowercase, words separated by hyphens, no punctuation (e.g. "Dense by Design" → `dense-by-design`).
2. Pick the base folder:
   - Default: `talks/<slug>/`
   - If this is a Figma Deep Dive session, nest it instead: `talks/figma-deep-dives/<slug>/`
3. Create that folder if it does not exist.
4. Create `<base folder>/transcript.md`. If I pasted transcript text, put it here; otherwise leave a `<!-- Paste transcript here -->` placeholder.
5. Create `<base folder>/metadata.md` using the template below, filling in what I provided and marking the rest.
6. Tell me the slug (and folder, if nested under `figma-deep-dives/`) and remind me I can run `/synthesize-talk <slug>` once the transcript is in place.

## metadata.md template

```markdown
# <Talk title>

## Session link

- Official Config page: <session URL or [NOT YET LINKED]>

## Transcript

- File: `transcript.md`

## OneNote notes

- `[NOT YET LINKED]` — add your page notes here after export.
```
````

### `.cursor/commands/synthesize-talk.md`

```markdown
# Synthesize a talk

Synthesize one talk into a role-tailored, transcript-grounded summary.

## Input

The talk slug to process (e.g. `dense-by-design`). If I did not provide one, ask me which talk, or infer it from the file I have open under `talks/`.

## Steps

1. Read my role from `templates/role-profile.md`. Tailor all relevance judgments and actions to that role and team.
2. Read the transcript. This is the ONLY source of truth.
   - Default location: `talks/<slug>/transcript.md`
   - Figma Deep Dive sessions are nested: `talks/figma-deep-dives/<slug>/transcript.md`
3. If a `metadata.md` exists alongside the transcript, use it only for the title, speakers, and session link.
4. Produce the output in the format below and save it to `output/<slug>.md`.
   - If the talk is a Figma Deep Dive, save to `output/figma-deep-dive/<slug>.md` instead.

## Rules (the grounding rule in `.cursor/rules/grounding.mdc` also applies)

- Do NOT assert facts not present in the transcript. No outside knowledge or assumptions.
- If a takeaway's relevance to my role/team is uncertain, mark it `[RELEVANCE UNCERTAIN — NEEDS CONFIRMATION]`.
- If the transcript is unclear, incomplete, or references onscreen visuals/demos not captured in text, mark it `[UNCLEAR IN TRANSCRIPT]` with the timestamp.
- Every takeaway must include a supporting quote (≤25 words) or `[no direct quote available]`.
- If the talk does not apply to my role/team, say so under **Not applicable** and stop.

## Output format

Start the file with a header (title, `**Source:**` transcript path, and `**Session:**`/`**Speakers:**` from metadata.md if known), then `---`, then the sections below.

### A) Summary
A 3–5 sentence overview grounded only in the transcript. Include the speaker's central argument/problem framing, and any value they reported (metrics, reduced pain, improvements).

### B) Key points and tools
Bulleted main points. Call out any specific tools, frameworks, or products by name.

### C) Verified takeaways (with quotes)
Takeaways directly relevant to my role/team, each with a supporting quote or `[no direct quote available]`. Look beyond surface-level matches: if a concept applies by analogy (e.g. a design pattern that maps to a backend/tooling pattern), include it, mark it `[ANALOGOUS]`, and state the analogous context.

### D) Role and team actions (including AI enhancements)
Concrete follow-up items for my team. Only include if clearly supported by the transcript, or label `[INFERRED]`.

### E) Not applicable / unclear items
Anything that doesn't apply, couldn't be verified, or was marked `[UNCLEAR IN TRANSCRIPT]`.

### F) Key terms reference
A table of domain-specific terms/tools/frameworks unfamiliar to a teammate who didn't attend:

| Term | Definition |
| --- | --- |
| Example term | One-sentence definition grounded in how the speaker used it |

Omit section F if the talk introduced no terminology that needs explaining.
```

## After scaffolding

1. Fill in `templates/role-profile.md` with the real role/team (skip if it's already customized).
2. Confirm `/add-talk` and `/synthesize-talk` show up when typing `/` in Cursor chat (requires this folder to be open as the workspace root).
3. Run `/add-talk` to create the first talk.
