# Synthesis prompt template

> Superseded by the `/synthesize-talk` slash command (`.cursor/commands/synthesize-talk.md`),
> which is the recommended way to run this. This file is kept as a readable, copy-pasteable
> reference of the same prompt. Both pull the role from `templates/role-profile.md`.

Use this in Cursor (Sonnet 4.6 recommended) for each talk, one at a time.

---

## Role

You are compiling Config 2026 takeaways for my role and team. Read my role and team from `templates/role-profile.md` and tailor all relevance judgments and actions to it.

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
