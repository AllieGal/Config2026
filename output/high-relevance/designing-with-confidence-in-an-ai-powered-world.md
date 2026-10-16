# Designing with confidence in an AI-powered world

**Source:** `talks/designing-with-confidence-in-an-ai-powered-world/transcript.md`
**Session:** [View session](https://config.figma.com/san-francisco/session/f9a5d27e-b1c3-4674-92ee-0545d7822fc0/)
**Speaker:** Bobby Meixner, VP, Solution Marketing, UserTesting

> **Transcript completeness:** **Survey numbers and core thesis are complete in text** (6:1 gap, reversibility factor, validate-more vs validate-less split, accountability %). **Watch the recording** for the live Figma Make + UserTesting demo (`~00:10:51`–`00:14:35`) and the closing AI-generated photo imperfections — both are visual and only partially narrated.

---

## A) Summary

Bobby Meixner presents findings from a UserTesting survey of 183 designers/design leaders on how AI affects speed, risk, and confidence — and reveals a troubling gap: 91% say work moves faster with AI, but only 15% feel *much more* confident in output quality, a 6:1 ratio. He frames this as the "reversibility factor" — confidence holds when decisions are cheap to undo, but collapses when they aren't. The key differentiator between teams that feel risk has decreased vs. increased is validation behavior: teams that validate more (research, usability tests, analytics) feel better about AI-assisted work. A live (fictional Skyline travel / seat-selection) demo of the UserTesting Figma plugin inside Figma Make shows AI-assisted design changes plus embedded user tests returning in hours without leaving the canvas. He closes by arguing human judgment is still scarce — and reveals every historical "first-time moment" photo in the deck was AI-generated with subtle errors only humans notice.

---

## B) Key points and tools

- **Survey findings** (183 designers / framed as design leaders):
  - 91% report work moves faster with AI
  - Only 15% feel *much more* confident in quality/output → 6:1 speed-to-confidence gap
  - Confidence at discovery/ideation: 4.1/5; confidence at final ship decision: 3.6–3.7/5
  - 65% can't confidently say their outcomes are *better* because of AI
  - 37% say results are the same; 19% say sometimes worse
  - Risk perception: 38% say risk decreased, 38% say risk increased — split evenly
  - Key differentiator: those who feel risk went DOWN validate more (research, usability tests, analytics); those who feel risk went UP skip validation or rely mainly on peer critique
- **Reversibility factor**: confidence holds when decisions are fast and cheap to undo; collapses as decisions become harder to reverse
- **UserTesting Figma plugin**: embeds user testing directly into the Figma canvas; an AI prompt defines what to learn, a test is launched, and insights return to the canvas
- **Figma Make integration**: demo shows the plugin working inside Figma Make — tests launched to a panel of 7M+ verified participants, AI-generated test plans, and results returned via Slack notification without leaving the working environment (demo summary used **eight participants**)
- **Accountability split** (when AI-assisted work misses the mark): 27% say design leaders, 20% PMs, 17% executives — no clear single owner
- **Protecting human judgment**: key leadership action — inform judgment with customer insights that are fast (hours), trusted (right participants), and embedded in everyday tools
- **Historical framing**: ATM (1967 / Reg Varney), iPhone (2007), Uber (2010), thumb-based dating / meetup — all required someone to deeply understand people and defend a vision before it existed; the job hasn't changed despite AI
- **Closing demo beat**: every first-time-moment photo in the talk was AI-generated with subtle errors; human judgment notices — booth #3 scavenger hunt offered as proof
- **Fictional Skyline demo result**: mid-funnel completion rate "up 79%" after validation loop — explicitly labeled fictional, with claim that real teams run similar workflows

---

## C) Verified takeaways (with quotes)

**1. The speed-to-confidence gap is the central risk of AI-assisted development — not just design.**

Our team likely experiences an analogous gap: AI tools generate code quickly, but confidence in correctness (especially for shared services, schema changes, or API contracts) may not scale with the speed. The survey finding that 65% can't confidently say outcomes are better is a warning sign worth internalizing.

> "That's a 6:1 gap between how fast we're moving and how sure we actually feel about where we're going."

**2. The reversibility factor directly maps to engineering decisions with high downstream cost.**

In backend services, irreversible decisions include: published Kafka topic schemas, released API contracts, database migrations, and data model changes. The finding that confidence collapses at high-stakes, hard-to-undo decision points should inform how much validation we do before finalizing these artifacts — regardless of how quickly AI helped draft them.

> "Confidence holds when decisions are fast and cheap to undo, and it collapses as we get further down the cycle when they're not."

**3. The same AI tools, used with more validation, produce meaningfully different outcomes.**

Teams that felt risk decreased with AI validate more — they cross-check with research, run tests, gather analytics. This is directly actionable: adopting AI tools is not sufficient; the team must pair AI assistance with a deliberate validation step to see the quality improvement.

> "Same tools, same AI, same speed, different outcomes — but it all varies depending on how folks validate and defend their work. Defensibility was definitely a key variable."

**4. Human judgment remains the scarce resource — and it requires active protection.**

The closing demo makes the case that embedding feedback signals directly into the development workflow (not as a separate step) is how teams protect the quality of their human judgment. For our team, this suggests integrating validation (testing, code review, integration feedback) as close to the point of generation as possible.

> "That is not something that AI can do for you. That part is still yours."

---

## D) Role and team actions (including AI enhancements)

- **[INFERRED] Audit team confidence in AI-generated output, not just speed**: Discuss as a team whether we feel the quality of AI-assisted code is genuinely better, or whether we're primarily experiencing speed gains with comparable quality. The 65% "can't say it's better" finding suggests this is worth examining honestly.
- **[INFERRED] Define validation checkpoints for irreversible decisions**: Identify our highest-stakes irreversible decisions (Kafka schema publication, shared API contract finalization, data migrations) and establish a non-skippable validation step before they are committed — independent of how quickly AI helped draft them.
- **[INFERRED] Embed feedback loops close to generation**: Following the "fast, embedded, trusted" insight, explore whether test outputs, integration feedback, or peer review can be surfaced in the same environment where code is generated (e.g., within Cursor, alongside the diff) rather than as a downstream step.
- **[INFERRED] Track quality signals alongside velocity metrics**: If the team starts reporting on AI adoption, pair velocity metrics (PRs/week, story points) with quality signals (bug escape rate, rework rate, integration failures) to detect the speed-to-confidence gap before it compounds.

---

## E) Not applicable / unclear items

### Watch the recording (visuals / demos missing from transcript)

| Timestamp | What’s missing | Why it matters |
| --- | --- | --- |
| `00:05:27`–`00:09:52` | Survey charts (speed vs confidence, stage confidence, accountability, risk split) | Numbers are spoken; charts show the full distribution |
| `00:09:52`–`00:10:51` | Leadership recommendations slide(s) he skips (“lots of details… not walking through all”) | Explicitly not covered verbally — **video + report needed** for the full list |
| `00:10:51`–`00:14:35` | Live Skyline / Diana demo in Figma Make: analytics, UserTesting prompts, seat UI changes, test plan, Slack notify, highlight reel | Workflow is step-narrated but UI state is on screen only |
| `00:14:35`–`00:15:06` | “Completion rate up 79%” analytics view | Claim is spoken; chart is visual; example is fictional |
| `00:16:31`–`00:16:56` | AI-generated historical photos with subtle errors | Closing proof that human judgment notices machine mistakes |

### Other notes

- UserTesting Figma plugin / Figma Make integration is design-workflow-specific.
- Accountability breakdown is about design org ownership, not eng ownership.
- **Speaker name:** not spoken in transcript; official listing is Bobby Meixner (header uses official).
- Survey wording mixes "design leaders" (framing) and "183 designers" (sample line) — both in transcript.

---

## F) Key terms reference

| Term | Definition |
| --- | --- |
| Reversibility factor | The speaker's term for the pattern where confidence in AI-assisted decisions holds when outcomes are easy to undo, but drops sharply when decisions are costly or impossible to reverse |
| Speed-to-confidence gap | The 6:1 disparity identified in the survey between the proportion of designers who feel faster with AI (91%) and those who feel much more confident in quality (15%) |
| Defensibility | The speaker's term for the ability to validate and stand behind a design or decision — identified as the key variable separating teams that feel AI reduced risk from those who feel it increased it |
| UserTesting Figma plugin | A Figma-native tool that allows designers to define a research question via AI prompt, launch a test to a panel of verified participants, and receive synthesized insights back into the canvas |
| AI sourcing / AI-generated test plan | UserTesting capabilities that automatically recruit participants and structure a test based on the designer's stated goal, without requiring manual test design |
