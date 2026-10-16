# Build like it's 2030. Listen like you mean it.

**Source:** `talks/build-like-its-2030-listen-like-you-mean-it/transcript.md`
**Session:** [View session](https://config.figma.com/san-francisco/session/24762e47-798d-47d7-83fd-7ae7c2d0d412/)
**Speaker:** Ned Dwyer, CEO & Co-founder, Great Question

> **Transcript completeness:** Thesis, permissive-by-design, and stats are spoken. **Watch the recording** for the Claude Code / deploy graphs and the prepared Figma Make → Great Question MCP research loop (feedback collected ahead of time).

---

### A) Summary

Ned Dwyer (CEO & Co-founder, Great Question) opens with an uncomfortable provocation from YC partner Nicolas Dessaigne: companies older than 2023 are treated as “legacy,” and without an AI-native team, product, and growth rates, customers leave, fundraising fails, and acquisition becomes unlikely. His central argument is that velocity without customer insight produces "slop" — fast-shipped features that don't solve real problems and ultimately destroy customer trust. The maxim is learn faster, not just ship faster; velocity combined with insight is required. He describes how Great Question rebuilt itself as an AI-native company by radically rethinking time expectations, making every team member a product builder, and replacing upfront approval gates with "permissive by design" structures backed by design system guardrails and review rituals. A prepared walkthrough shows a Figma Make → Great Question MCP loop that embeds user research directly into the prototype iteration workflow.

---

### B) Key points and tools

- "Velocity + insight" is the required combination — velocity alone = slop; insight alone = irrelevance; frame as **learn faster, not just ship faster**
- YC partner **Nicolas Dessaigne**: companies **older than 2023** treated as legacy; separately, missing AI-native team / product / growth rates → existential risk
- **Stats:** Claude Code output for Anthropic ↑ **8x** since 2023; ~**65%** of code deployed to production without human interaction, rising each quarter (`[UNCLEAR IN TRANSCRIPT]` for graph visuals at `00:05:07`)
- Rethinking time: tasks that took 3–5 days can now take a morning; a year-long initiative can take a quarter
- "Making everyone a product builder" — support team ships fixes directly; chief of staff automated end-of-month reporting; CEO ships features to production
- **Permissive by design**: remove *upfront* approval gates (elaborate PRDs, architecture diagrams), then let anyone build — but quality is still protected by (1) a design system that structurally enforces the quality bar (**Zeroheight**) and (2) a subject-matter-expert final sign-off **before release**. Explicitly *not* a "no gates / just trust people" model
- Customer signal baked into every release via **MCP** accessing all qualitative data (support tickets, sales calls, research, social media)
- **Figma Make** `[ASR: "Figma Mike"]` — used to build and iterate on prototype in the demo
- **Great Question MCP** — launches a UX research study from within Figma Make work surface; results feed back into the prototype (demo feedback was pre-collected)
- "The last 10% is what differentiates your product from a generic also-product" — AI gets to ~90%; human taste/craft holds the final 10%
- Closing: “listen at the speed you ship”; public MCP roadmap available

---

### C) Verified takeaways (with quotes)

**1. Velocity without insight is a trap — and a fast one.**
> "If we take velocity... but we deliver it without insight, all you're really doing is delivering slop."

Directly applicable to the team's AI-accelerated development. Shipping features quickly using AI agents without validating that the work solves the right problem accelerates the wrong work. The fix is making insight collection faster, not skipping it.

**2. Time expectations should be repriced by an order of magnitude.**
> "Everything that traditionally would have taken a year, we now need to reimagine... that could take a quarter, a month, a week, a day, an hour."

`[ANALOGOUS]` For engineering work: service scaffolding that took a sprint can take hours with agents. Architecture diagrams that took a day can take 30 minutes. The team should actively reprice effort estimates and use the recovered time to do more validation, not just more shipping.

**3. "Permissive by design" means moving quality gates, not removing them — the enforcement substrate is mandatory.**

This is the most easily misread point in the talk, and it matters for our team. Ned is *not* saying "trust people and skip quality checks." He is saying: remove the heavy *upfront* gates (mandatory PRDs, required architecture diagrams before anyone can start) and replace them with two things that still protect quality — (1) a shared design system that structurally prevents work from shipping in a way that "breaks our quality bar," and (2) a review ritual where a subject-matter expert does the final sign-off *before* it goes live. Later in the talk he also returns to standards: define the quality bar, "track the deviations and enforce them," and "everyone has to rise to that bar" — related, not the same move as permissive-by-design.

> "Rather than doing the gating and the guardrails up front... we'd empower people to take their own initiative... where we then have a system, a design system... to make sure that the things being shipped... could be done without breaking our quality bar. The second was establishing rituals of review where... the subject matter expert [does] the final sign-off before it went live."

`[ANALOGOUS]` For the team this is a *pro*-consistency model, but only if the substrate exists. The engineering equivalents: shared libraries/templates plus CI enforcement (linting, Checkstyle, contract tests, coverage gates) that make it hard to ship something off-standard, plus a required reviewer on the PR before merge. Without that enforced substrate, "permissive by design" would produce exactly the cross-app divergence and quality drift we want to avoid. The lesson is "remove *upfront bureaucratic* gates," not "remove quality control." Later (`00:16:39`) he also talks about tracking deviations and enforcing a quality bar as a job/standards point — thematically related, not the same paragraph as permissive-by-design.

**4. MCP as a bridge between data sources and decision-making.**
> "Accessing all of the qualitative data customers have ever told us via our MCP to understand what anyone ever said across support ticket, sales calls, research, social media."

`[ANALOGOUS]` Domain data that is only reachable through backend APIs is invisible to agents. Building an MCP that exposes this data to agents — for internal decision-making, debugging, or feature planning — is a direct parallel to what Great Question built for customer data.

---

### D) Role and team actions (including AI enhancements)

1. **Re-examine time estimates on engineering tasks with AI assistance.** If a service scaffold takes 2 hours instead of 2 days with an agent, reallocate the recovered time to validation, code review depth, or documentation — not just the next task.

2. **Move gates from upfront bureaucracy to structural enforcement + a fast final review — don't remove them.** Identify upfront friction (mandatory design docs / architecture diagrams before work can start) that could be replaced by guardrails that enforce the standard automatically (CI rules, linting, Checkstyle, contract tests, coverage thresholds, shared templates) *plus* a required subject-matter-expert sign-off before release. The goal is fewer upfront forms, not fewer quality checks — the enforced substrate is what makes permissiveness safe and keeps apps consistent. `[INFERRED]`

3. **Build an internal MCP exposing team-owned data for agent-assisted decision-making.** A read-only MCP over catalog, inventory, or configuration data would enable AI agents to answer questions like "what products are in this category state?" without manual API calls. `[INFERRED]`

4. **For internal web apps: embed lightweight feedback collection into each release.** Before shipping an internal web app feature, establish a quick signal loop — even a 5-minute check with an internal user — rather than waiting for feedback to emerge organically.

---

### E) Not applicable / unclear items

### Watch the recording (visuals / demos missing from transcript)

| Timestamp | What’s missing | Why it matters |
| --- | --- | --- |
| `00:05:07`–`00:06:05` | Claude Code 8x / ~65% no-human-deploy graphs | Only numeric stats in the talk |
| `00:11:39`–`00:14:52` | Figma Make reimbursement prototype → MCP study → pre-collected feedback → v3 | Research-in-the-loop demo (not fully live) |

### Other notes

- Great Question product specifics (UX research SaaS) — not applicable
- The B2B SaaS existential crisis framing applies to product companies, not internal engineering teams — the urgency is real but the stakes framing doesn't map 1:1
- Zeroheight (design system documentation tool) — not applicable to backend work

---

### F) Key terms reference

| Term | Definition |
| --- | --- |
| Slop | Fast-shipped features built without customer insight; looks productive but doesn't solve real problems |
| Velocity + insight | The required combination: shipping fast AND understanding whether you're solving the right problem |
| Permissive by design | Replacing *upfront* approval gates (PRDs, architecture diagrams) with structural enforcement (a design system / quality bar that work can't break) plus a subject-matter-expert final sign-off before release; explicitly not a removal of quality control |
| AI-native | Having an AI-native team, product, and growth rates (as framed by the YC partner) |
| The last 10% | The craft, taste, and customer understanding that separates a differentiated product from a generic one — the part AI cannot yet provide |
