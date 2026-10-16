# Figma deep dive: Agentic workflows and the MCP

**Speaker:** Jake — Figma platform team (creative coder, stegasound project)
**Source:** `talks/figma-deep-dives/figma-deep-dive-agentic-workflows-and-the-mcp/transcript.md`

---

## A) Summary

Jake argues that AI accelerates execution but not clarity, and that the biggest risk in the AI era is "cognitive surrender" — adopting an LLM's judgment as your own and skipping the consideration work that produces a real point of view. Because we've been trained to trust "polish" as a signal of consideration, AI's polished-but-average output can seduce teams off the right path; the antidote is a "consideration imperative" — investing in clarified intent up front. He maps this to spec-driven development and to a Google white paper's finding that low-investment "vibe coding" creates high long-term maintenance friction, while upfront platform design (APIs, deterministic layers, structured agentic context) pays dividends. The technical heart of the talk: precise context (design tokens, Code Connect, and a proposed "hyper tokens" abstraction) lets agents write more of the code, write better code, and produce *less total code* — "leaner code and lower AI usage," with verbose context instead leaving behind tech debt. He demonstrates compiling a strongly-typed, form-agnostic schema from a single source of truth into libraries, docs, rules, skills, Code Connect, and code; using FigJam as a human-editable "source of contextual truth" that agents compile into per-agent skills; and a one-night build of a technical website (stegasound) by orchestrating Figma's design agent, MCP, Make, and FigJam — keeping his intent central throughout.

---

## B) Key points and tools

- **Cognitive surrender**: adopting an LLM's judgment as your own to avoid the burden of validation and the work of forming a distinct point of view.
- **AI accelerates execution, not clarity**: "AI can get in the way of clarity"; polished output is built on averages and is absent the context you haven't yet provided.
- **Consideration imperative**: deliberately prioritizing clarified intent at the front of the process to counter cognitive surrender. "Not having clarity upfront is at best multiplication by zero."
- **Spec-driven development**: framing design (and dev) work as a precise specification, not just a preview, improves LLM outcomes.
- **Google white paper reference**: low-investment vibe coding → high maintenance friction and a "dead end for complex systems"; alternative is upfront platform design — APIs, deterministic layers, structured agentic context. `[UNCLEAR IN TRANSCRIPT — specific paper not named, ~00:05:37]`
- **Figma MCP server**: provides LLMs context from Figma design, Make, and FigJam; combined with the plugin API to allow writing to Figma/FigJam.
- **Design tokens**: more precise than raw values; encode both light/dark mode, fitting more intent into less surface area.
- **Code Connect**: provides production component context via MCP — compiles concise code snippets (with literal labels, stubbed event handlers) that tell the agent exactly which code component to use and how data flows, instead of verbose React/Tailwind dumps.
- **Precise vs. verbose context outcome**: precise context (Code Connect) → agents write far more of the total code, *less total code overall*, lower AI usage; verbose context → agents write a majority but humans must fill gaps, leaving "tech debt."
- **Code Connect improvements shipped**: framework-agnostic template API; slots rendering for complex components; MCP tools for publishing Code Connect and understanding the Figma library; a Code Connect skill for agents.
- **Hyper tokens (proposed)**: named, reusable "semantic style fragments" (like CSS declaration blocks / Figma text styles) that bundle many style decisions into a single named value, reducing LLM inference. Applicable to shape, layout, typography, surface effects, transformation, motion.
- **Single source of truth schema**: a strongly-typed, form-agnostic JSON schema (leveraging the DTCG design-token spec + hyper-token structures + component "recipes") deterministically compiled into design libraries, icon libraries, Code Connect, base CSS, base Svelte, and functional components.
- **Skills**: "Skills don't replace your expertise, they deploy it." A skill supplements LLM understanding so agents execute more specifically; references are loaded only as needed.
- **Source-of-truth-for-skills pattern**: maintain one human-curated contextual source; let agents transform it into the latest skill (and into *per-agent* skills), rather than hand-editing agentic markdown (which is "like editing minified code").
- **FigJam as agentic interface / source of contextual truth**: encode expertise visually on a canvas; agents read prompt sections via MCP, do work in Figma and the codebase, and write results back. Includes onboarding sections, example code blocks (to reduce inference), a "homework assignment" (have the agent practice Code Connect against an "answer key" before writing the skill), and splitting big tasks into sub-agent plans written into FigJam for human review/correction.
- **Stegasound case study**: built an interactive technical website in one night by combining Figma design agent (fed his encoding library's source code), FigJam (prompt crafting + agent handoffs), MCP (retrieve design, create system in Figma + code), and Make (visualize complex algorithm behavior, even when the specific code wasn't reused). Demo at `stegasound.jake.fun`.

---

## C) Verified takeaways (with quotes)

**1. "Cognitive surrender" is the core risk — keep human intent and validation central in AI-assisted engineering.**

This is the talk's central, directly transferable warning. For our team, it means not accepting AI-generated code, schemas, or designs as correct because they look polished — the validation and point-of-view work remains ours.

> "Cognitive surrender is when we adopt an LLM's judgment as our own. This relieves ourselves of the burden of validation, and often the work required for a distinct point of view."

**2. Invest in clarity/intent up front — vibe coding creates long-term maintenance debt for complex systems.**

Directly applicable to backend/full-stack work: the white-paper framing (upfront platform design — APIs, deterministic layers, structured context) is exactly our world.

> "low investment vibe coding leads to high friction for long-term maintenance and a dead end for complex systems… The alternative? Upfront platform design. Invest in APIs, deterministic layers, and structured agentic context."

**3. Precise context makes agents write better, leaner code AND reduces AI usage/cost.**

The Code Connect result generalizes beyond design: giving agents precise, structured context (vs. verbose dumps) yields less total code, more agent-authored code, and lower token spend. For us, this argues for concise, structured API/schema context over dumping entire files.

> "When we provide agents with precise context like Code Connect snippets, agents write far more of the total code… There's less total code… This is what we would call leaner code and lower AI usage. We're doing more with less."

**4. Verbose/imprecise context leaves behind tech debt.**

> "what about all this code that we didn't write? Well, that's sitting in the agentic output from less precise context. We describe this as tech [debt]."

**5. Maintain a single source of truth, compile everything else from it deterministically.**

Jake compiles libraries, docs, rules, skills, Code Connect, CSS, and components from one schema. The backend analogue is strong: a single source of truth (e.g., schema/IDL/OpenAPI) deterministically generating clients, server stubs, docs, and validation — avoiding drift.

> "a strongly typed and form agnostic schema… that can be deterministically compiled from a single source of truth into all of the libraries, documentation, rules, skills, and context that your team and their tools need."

**6. "Skills don't replace your expertise, they deploy it" — and don't hand-edit agent-generated skills.**

Encode expertise in a human-friendly source of truth and let agents compile it into (per-agent) skills, because editing agentic markdown is like editing minified code.

> "Editing agentic markdown output is kind of like editing minified code… The easiest thing to do is to just leave it to the agent… instead, we can create a contextual source where we can provide the most relevant information."

**7. Validate an agent's understanding before trusting its output ("homework + answer key").**

The pattern of making an agent practice a task and compare against a known-good reference *before* it writes durable artifacts is a reusable quality technique for AI-assisted engineering.

> "the goal is not to get these agents to write perfect code connect. It's to get it to experience what could help an agent write code connect… look at the delta between what they wrote and what a good code connect doc looks like."

**8. Reduce agent inference by providing concrete examples and named abstractions.**

Both hyper tokens and his FigJam "example code blocks" exist to reduce how much the agent has to infer — a transferable prompting principle.

> "I provided example code blocks… This also reduces the amount of inference that the agent was going to have to do."

**9. Use agents to split large tasks into reviewable sub-agent plans, with a human checkpoint.**

> "The first thing it did was it split up this massive task into many plans for sub agents. It wrote these plans into Figjam for me to go in and read and correct."

---

## D) Role and team actions (including AI enhancements)

- **[INFERRED] Build a "precise context" layer for our services analogous to Code Connect.** Provide AI tools with concise, structured representations of our APIs and components — OpenAPI specs, well-typed DTOs, example request/response snippets, and "use this client/handler like so" stubs — instead of dumping entire files. Expect leaner, better AI output and lower token cost.
- **[INFERRED] Adopt spec-driven / intent-first AI workflows.** For non-trivial features, write the spec and clarify intent before prompting agents; treat "shipping the right thing" as the priority, not just generating code fast.
- **[INFERRED] Establish single sources of truth that compile deterministically.** Where we have schemas (Avro/Protobuf for Kafka, OpenAPI for REST), generate clients, server stubs, docs, and validation from one source to prevent drift — mirroring the schema-compilation approach.
- **[INFERRED] Create curated context/skills sources for our coding agents.** Maintain human-owned context (architecture decisions, conventions, integration patterns) as a source of truth and let agents compile it into agent-specific skills, rather than hand-editing generated agent instructions.
- **[INFERRED] Add an agent "homework + answer key" validation step.** For repeatable tasks (writing a Kafka consumer, scaffolding an endpoint), have agents attempt against known-good references and review the delta before relying on their output or codifying a skill.
- **[INFERRED] Guard against cognitive surrender in code review.** Treat AI output as a draft requiring real validation; don't let polish substitute for correctness, especially on shared/critical paths (global config, schemas).
- **[INFERRED] Use plan-then-execute orchestration with human checkpoints.** Have agents decompose large tasks into reviewable plans (and sub-agent tasks) that a human corrects before execution.

---

## E) Not applicable / unclear items

- The specific Google white paper on agentic coding is referenced but not named or linked `[UNCLEAR IN TRANSCRIPT — ~00:05:37]`.
- "Hyper tokens" and the form-agnostic schema are described as active explorations / not-yet-shipped Figma concepts, so their final form is uncertain `[RELEVANCE UNCERTAIN — NEEDS CONFIRMATION]` for direct adoption, though the underlying principle (named reusable abstractions reduce inference) transfers.
- Design-specific mechanics (text styles, Figma libraries, FigJam canvas manipulation, Make's React output, pencil-tool illustration) are tool-specific; only the patterns transfer to backend/full-stack work.
- Several demos are heavily visual (compiling design systems on canvas, FigJam sections filling in live, the stegasound waveform playback) and are onscreen actions not fully captured in text `[UNCLEAR IN TRANSCRIPT]` where exact steps matter.

---

## F) Key terms reference

| Term | Definition |
| --- | --- |
| Cognitive surrender | Adopting an LLM's judgment as your own to avoid the work of validation and forming a distinct point of view |
| Consideration imperative | Deliberately prioritizing clarified intent at the front of the process to counteract cognitive surrender |
| Spec-driven development | Treating the work as a precise specification (not just a preview), which improves outcomes when working with LLMs |
| MCP (Model Context Protocol) server | Figma's server that provides LLMs context from Figma design, Make, and FigJam (combined with the plugin API to also write back) |
| Code Connect | A Figma capability that provides concise, production-accurate component context to agents via MCP, telling them exactly which code component to use and how data flows |
| Design tokens | Named values (e.g., DTCG spec) encoding style decisions (including light/dark mode) more precisely and compactly than raw values |
| Hyper tokens | A proposed abstraction for named, reusable "semantic style fragments" (like CSS blocks / text styles) that bundle many style decisions to reduce LLM inference |
| Single source of truth (schema) | A strongly-typed, form-agnostic schema deterministically compiled into libraries, docs, rules, skills, Code Connect, and code |
| Skill | A bundle of codified expertise that supplements an LLM's understanding so agents execute more specifically; references loaded only as needed |
| Tech debt (agentic) | Lower-quality, human-must-fix code left behind when agents are given verbose/imprecise rather than precise context |
| Reference (in a skill) | A large block of context accessed only as needed rather than loaded every time the skill runs |
