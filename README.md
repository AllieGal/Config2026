# Config 2026 Notes

Local workspace for compiling and organizing Config 2026 talk takeaways against your Microsoft Notebook notes and attached transcripts.

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

## Reusing this structure elsewhere

[`SETUP.md`](./SETUP.md) is a self-contained bootstrap prompt: hand it to Cursor in a fresh empty folder (e.g. for next year's conference) and it recreates the folder structure, slash commands, and grounding rule from scratch — no cloning or git history required. The only file to customize afterward is `templates/role-profile.md`.

## Grounding rules

- Transcript is the source of truth; Notebook notes are candidates to verify, not to assert from directly.
- Every takeaway must cite the talk and include a supporting quote (≤25 words) or the marker `[no direct quote available]`.
- Use these markers (defined in `.cursor/rules/grounding.mdc`) instead of guessing:
  - `[UNCLEAR IN TRANSCRIPT]` (with timestamp) — the transcript is unclear/incomplete, or references an onscreen visual/demo not captured in text
  - `[RELEVANCE UNCERTAIN — NEEDS CONFIRMATION]` — relevance to the role/team isn't certain
  - `[INFERRED]` — a reasonable action not directly stated in the transcript
  - `[NOT APPLICABLE]` — doesn't apply to the role/team
