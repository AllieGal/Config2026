# How structured thinking gives your AI superpowers

**Speaker:** Carola Pesch Canali, Design Lead, AI team (Rovo), Atlassian  
**Source:** `talks/how-structured-thinking-gives-your-ai-superpowers/transcript.md`

---

## A) Summary

Carola Pesch Canali argues that the biggest lever for improving AI output quality isn't the tool, the agent, or the workflow — it's the context you give your AI about yourself and your team. Drawing on Mike Cannon-Brookes's framing that "intelligence is the engine, context is the fuel," she presents three practical habits for externalizing personal thinking in ways that AI tools can reference: (1) recording end-of-day brain-dumps and having AI structure them into Confluence pages and a personal `thinking.md` file; (2) training AI to write in your voice using your existing emails, Slack messages, and recorded conversations; and (3) using your phone camera as a "prompt machine" — snapping photos and issuing three-word prompts to build a rich, ongoing context inventory. She closes with the team-level implication: a personal context graph is the starting point, but the real leverage comes when decision-making context is logged in shared, accessible tools — turning AI from a personal assistant into a team collaborator.

---

## B) Key points and tools

- **Mike Cannon-Brookes quote**: "In a world where intelligence is the engine, context is truly the fuel."
- **Personal context graph**: the accumulated, externalized record of your thinking, decisions, writing style, and observations — the raw material that makes AI responses personal and relevant to you
- **Team context graph**: the shared, team-accessible version of individual context logs — logged decisions, project opinions, and collaborative reasoning that enables AI to act as a team collaborator rather than a personal assistant
- **Three habits**:
  1. **Empty your brain (voice recording → structured doc)**: Record end-of-day rambling in Loom (or any recorder), transcribe, have AI make sense of it, convert to a Confluence page, and extract a `thinking.md` file capturing your reasoning patterns — 10 minutes/day max; compounds over time
  2. **Train your AI to write as you (voice/writing samples → writing skill)**: Use sent email folder, Slack messages, or recorded conversations with teammates to feed AI your writing style; ask it to build a "writing skill" from this material
  3. **Give your AI eyes (camera + 3-word prompts)**: Take photos of anything relevant (handwritten to-do lists, sketches, physical objects, environments) and issue short prompts; the photo provides the context that would otherwise take paragraphs to describe
- **Loom**: mentioned as the speaker's preferred recording tool; any recorder with a transcript export works
- **Confluence**: used as the destination for structured thinking documents; described as the tool for making context accessible to the team
- **Rovo**: Atlassian's AI product (the team Carola leads design for)
- **Skill (in Atlassian/Rovo context)**: a saved set of instructions or persona rules that govern AI output — created by prompting the AI to "build a skill" from your inputs; equivalent to a persistent system prompt
- **`thinking.md` file**: a structured document extracted from voice transcripts that captures reasoning patterns, opinions, and decision-making frameworks — referenced by AI when the user asks for help thinking through a problem
- **"Photo is worth 100 prompts"**: a practical observation that visual context collapses the gap between what you're thinking and what you want AI to do
- **Git merge for to-do lists**: the speaker's framing of using a photo of a physical notebook to sync handwritten tasks with digital task management tools

---

## C) Verified takeaways (with quotes)

**1. Context is the most underinvested lever for AI quality — and most of that context is already ours to give.**

The most actionable insight from this talk for our team is to check whether we are under-contextualizing our AI interactions. Teams typically have rich institutional knowledge: how we think about system design, what our architectural preferences are, what decisions we've made and why. That context often lives in people's heads, in ADRs, and in chat threads — not in a form AI tools can reference consistently. Investing in making that context explicit and accessible is a higher-leverage move than switching tools.

> "What really makes your AI personal to you is stuff about yourself. The glass doesn't know the shape of your mouth, or the dagger doesn't know the size of your hand — the AI that everyone uses doesn't know you."

**2. Externalizing thinking — even informally — makes AI more useful and creates a shareable record.**

The voice-recording habit is a lightweight version of something our team should already be doing more of: writing down reasoning, not just decisions. The `thinking.md` concept maps directly to how we could structure our team's architectural reasoning files — a living document that captures not just *what* we decided but *how we think* about problems in our domain (eCommerce discovery, catalog data, Kafka event design).

> "the more you ramble, the more you start to externalize and verbalize your thinking, the more your AI responses will be tailored to you."

**3. A team context graph — shared, logged, and AI-accessible — is the real leverage point.**

This is directly applicable to our team. Individual AI quality improves with personal context, but the real value comes when team-level context (architectural decisions, shared conventions, domain reasoning) is logged in a form that AI can reference. Our Confluence pages, ADRs, and technical design documents are the raw material for this — if they're well-structured and consistently maintained.

> "Your personal graph is a start, but the team graph is what turns AI from your personal assistant into a team collaborator."

**4. The photo-as-context shortcut has a software equivalent: provide visual/structural artifacts rather than lengthy descriptions.**

For engineers, the equivalent of "snap a photo and give a 3-word prompt" is: paste a code snippet, an error trace, a data schema, or a system diagram and give the AI a short directive. This is more efficient than describing the problem in prose and produces better AI responses.

> "A photo is really worth 100 prompts, and sometimes sketching something out by hand, taking a photo of it, and building it is the simplest workflow — it works like magic."

---

## D) Role and team actions (including AI enhancements)

- **Build a team `thinking.md` equivalent**: Create a shared document (in Confluence or a repo README) that captures our team's reasoning patterns — how we approach service design decisions, what our default architectural stances are, how we think about tradeoffs between consistency and flexibility. Reference this document explicitly when using AI for design or implementation tasks.
- **[INFERRED] Treat ADRs as AI context, not just decisions**: Our architectural decision records should be structured not just to record *what* was decided, but *why* — the reasoning process, alternatives considered, and tradeoffs accepted. AI tools that reference these will produce much more contextually appropriate suggestions.
- **[INFERRED] Build a "writing as us" context for our team's technical documentation**: Identify existing well-written technical docs (good READMEs, ADRs, design docs) and use them to calibrate AI writing style for new documentation tasks — so AI-assisted docs sound like our team, not like generic AI output.
- **[INFERRED] Use artifacts (code, schemas, traces) as prompts, not just descriptions**: When prompting AI tools, prefer attaching the actual artifact (schema, stack trace, existing code) over describing it in prose. Shorter, more specific prompts with attached context outperform long descriptive prompts without it.
- **[INFERRED] Experiment with end-of-sprint context capture**: At the end of each sprint, have team members record a brief voice note or write a short unstructured entry about what was built, what tradeoffs were made, and what they'd do differently. Have AI structure and archive these. Over time, this builds a searchable record of team reasoning that exceeds what retrospectives typically capture.

---

## E) Not applicable / unclear items

- The specific tools (Loom, Rovo, Atlassian's Confluence/Jira stack) are ecosystem-specific; the patterns are transferable to our team's tools (Confluence, Jira are already in use, per the Atlassian stack mentioned).
- The personal context examples (selling garden statues, tracking bird species, monitoring workouts) are illustrative of the habit pattern but not directly applicable.
- The "writing skill" training approach is demonstrated in a design/communication context; engineering-specific analogs would target technical writing, PR descriptions, and documentation style rather than marketing copy or social posts.
- [UNCLEAR IN TRANSCRIPT at 00:05:06–00:05:53] — the specific mechanics of how the speaker prompts the AI to "build a skill" from four bullet points are not fully detailed; the referenced UI appears to be Rovo-specific.

---

## F) Key terms reference

| Term | Definition |
| --- | --- |
| Personal context graph | The speaker's term for the accumulated, externalized record of an individual's thinking, decisions, writing style, and observations — used to make AI responses more personally relevant |
| Team context graph | The shared, team-accessible version of individual context logs — project decisions, opinions, and collaborative reasoning that allow AI to act as a team collaborator rather than a personal assistant |
| Skill (Atlassian/Rovo) | A saved set of instructions or persona rules that governs how an AI responds — created by prompting the AI to "build a skill" from user-provided input; functions as a persistent, reusable system prompt |
| `thinking.md` file | A structured document extracted from voice transcripts or free-form writing that captures reasoning patterns, opinions, and decision-making frameworks; referenced by AI when helping the user think through problems |
| Rovo | Atlassian's AI product (the speaker's team) — described as the AI tool that integrates with Loom, Confluence, and Jira to create a connected context-feeding stack |
