# Designed to be read: making a system AI can actually use

**Source:** `talks/designed-to-be-read-making-a-system-ai-can-actually-use/transcript.md`
**Session:** [View session](https://config.figma.com/san-francisco/session/c856c21b-317e-482c-8a3f-f01280aeed56/)
**Speaker:** Harvey Whiting, Senior Designer, Monetization Design, Meta

> **Transcript completeness:** Spoken argument is largely complete (AI slop → three root causes → golden sets / 80% bar → 87% pilot → MCP + Figma Make → Context → Skills → Agents → three takeaways). **Watch the recording** for golden-set examples, the left/right “wobbly → target” iteration visuals, the multi-screen agent demo, and the multimodal “wobbly lines” closing visual — those are on screen only.

---

## A) Summary

Harvey Whiting (Meta Monetization Design) describes Meta’s journey from “AI slop” — fast but wrong AI-generated design — to design-system-aligned quality, via a Figma Make partnership. Early experiments on Ads products failed the same ways across models/tools: wrong type/color, missing components, low repeatability, and quality collapse on complex UIs (e.g. full Ads Manager). Three root causes: proprietary internal libraries the open-web model can’t bridge; design-system complexity (hundreds of primitives, do’s/don’ts); and unrealistic one-shot expectations. They got scientific with **golden sets** (repeated test cases + a metric), set an **80% “high accuracy” bar** (perfect / correct components / free of issues / production-ready), rebuilt components pixel-exact with in-session course-correction and strict guidelines in a **Figma Make template**, and hit **87%** on that pilot — above the bar. Manual feedback loops didn’t scale, so they pursued **MCP** for context delivery at Meta scale, partnered with Figma to integrate it into Make (net-new, codeveloped), and got design-system-aligned output **in one shot without a template**. He closes with a layered stack — Context → Skills → Agents — and three takeaways: audit context, embrace the feedback loop, prepare for agents.

---

## B) Key points and tools

- **AI slop / “fast, but wrong”**: plausible AI design that fails a real design-system bar (missing states, wrong components, guideline-breaking content)
- **Early failure modes** (before root causes): quality gaps vs the real system; low repeatability (same prompt → different results); context collapse on complex flows
- **Root causes**: (1) proprietary dependencies; (2) design-system complexity; (3) unrealistic one-shot expectations
- **Golden sets**: repeated test cases + a measurable accuracy metric; enables re-prompt / isolate / course-correct
- **Pilot bar**: ≥ **80%** high accuracy (= perfect / uses every component it should / free of issues / production-ready) → achieved **87%** with template + guidelines (not the MCP step)
- **Figma Make template**: pixel-exact components + strict agent usage guidelines from the iterative technique
- **MCP (Model Context Protocol)**: context-delivery infrastructure for color, type, spacing, components, docs, content standards, illustrations — so any AI tool gets the right context at the right moment; Meta started building it; **Make integration** was codeveloped with Figma
- **Post-MCP result**: design-system-aligned output **one-shot, without a template** (distinct from the 87% iterative pilot)
- **Figma connectors / MCP connections**: broadly available in Figma at talk time
- **Layered stack**: Context → Skills → Agents
  - *Context*: machine-consumable system knowledge (tokens, components, rules)
  - *Skills*: knowing when/why to apply context (speaker notes Figma launching skills natively — `[UNCLEAR IN TRANSCRIPT]` product detail)
  - *Agents*: multi-screen / multi-direction generation once context + skills exist
- **Three takeaways**: audit your context; embrace the feedback loop (collaborator, not one-shot); prepare for agents now
- **Multimodal design**: Swift / HTML / Figma design as “just code” LMs can translate between with little context loss

---

## C) Verified takeaways (with quotes)

**1. Undocumented systems are unusable by AI — and anything unspecified is randomized.**

Our services, APIs, schemas, and operational patterns are the engineering equivalent of a design system. If they aren’t structured for AI consumption, tools fill gaps with web conventions or hallucinations.

> "Anything that is not specified is randomized or aligns to some web convention that you didn't define or agree upon."

**2. Measure quality with a fixed bar before you trust the workflow — Meta’s 87% was a pilot pass-rate, not “each output is 87% clean.”**

They defined high accuracy as free of issues / production-ready, aimed for ≥80% of prototypes hitting that bar on golden sets, and hit 87%. MCP came *after* to scale context delivery.

> "That got us to the bar we'd set for our pilot. 87%… free of issues. It's production ready."

**3. The MCP pattern — structured context at the moment of need — is directly applicable to engineering tooling.**

Analogous move: OpenAPI, Kafka schemas, ADRs, shared conventions reachable by Cursor/Claude/Copilot (MCP or equivalent).

> "Could we capture all dimensions of our design system in this infrastructure? The color, the type, the spacing, the components — not just the components themselves, but the documentation around them."

**4. Treat AI as a collaborator with an onboarding process, not a one-shot oracle.**

> "If a new designer started on your team, you wouldn't just say, 'Hey, go do this.' You'd say, 'Hey, this is my customer… This is all the context you need…'"

**5. Teams with strong context (and skills) foundations will move fastest when agents are production-ready.**

> "The teams that have their context and their skills ready to go, you will be the ones that move the fastest when agents become production ready."

---

## D) Role and team actions (including AI enhancements)

- **[INFERRED] Audit our "context foundations"**: OpenAPI specs, Kafka schemas (Avro/Protobuf), Spring Boot READMEs, ADRs, runbooks — are they AI-consumable? Biggest gaps first.
- **[INFERRED] Explore MCP or equivalent context delivery**: Up-to-date internal contracts/conventions for Cursor/Claude/Copilot.
- **[INFERRED] Build "golden sets" for AI-assisted development**: Fixed representative tasks (Kafka consumer, REST endpoint, migration); score against an explicit pass bar repeatedly.
- **[INFERRED] Establish an iterative AI workflow**: Review-and-correct loops for shared/config/schema work — don’t expect one-shot perfection on complex tasks.

---

## E) Not applicable / unclear items

### Watch the recording (visuals / demos missing from transcript)


| Timestamp             | What’s missing                                                                | Why it matters                                              |
| --------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------- |
| `00:05:41`–`00:06:11` | Golden-set / metric examples (“I’ve got some examples here”)                  | How they actually scored “high accuracy”                    |
| `00:07:01`–`00:07:28` | Left = target design; right = iteration sequence (“starts off pretty wobbly”) | Visual proof of the 87% journey                             |
| `00:10:29`–`00:11:30` | Multi-screen agent / “six words → entire feature” demo                        | Agent layer is slide/demo-dependent                         |
| `00:13:54`–`00:15:07` | Multimodal / “wobbly lines → straight” production-as-clay visual              | Closing paradigm-shift image not in text                    |
| `00:09:53`–`00:10:29` | Figma “skills” product launch detail (“if this works… spoiler alert”)         | `[UNCLEAR IN TRANSCRIPT]` — product claim needs video/slide |


### Other notes

- Figma Make / connectors are design-tooling; the **context-delivery pattern** still transfers.
- Multimodal Swift/HTML/Figma translation is design-workflow-specific.
- ASR says “odds products” / “odds manager” — clearly **Ads** / Ads Manager from context and Config bio.
- **Speaker spelling:** transcript says “Harvey Whiteing”; official Config listing is **Harvey Whiting** (header uses official). Role: Senior Designer, Monetization Design, Meta — not a generic “Meta Design” org label.
- **Do not conflate 87% with MCP:** 87% = golden-set + Make **template** pilot; MCP enabled later one-shot-without-template results (no second % given in transcript).

---

## F) Key terms reference


| Term                         | Definition                                                                                                 |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------- |
| AI slop                      | AI-generated output that is fast and plausible-looking but fails a real system’s quality bar               |
| Golden sets                  | Curated test cases run repeatedly to measure and improve AI output quality                                 |
| High accuracy (Meta’s bar)   | Perfect / correct components / free of issues / production-ready — used as a pass criterion for prototypes |
| MCP (Model Context Protocol) | Protocol/infrastructure for delivering structured system context to AI tools at the moment of need         |
| Context foundations          | Machine-consumable documentation of system rules, tokens, components — prerequisite before skills/agents   |
| Skills (layered stack)       | Knowing when and why to apply context, not just what the context contains                                  |
| Agents (layered stack)       | Multi-task / multi-screen generation once context and skills are in place                                  |


