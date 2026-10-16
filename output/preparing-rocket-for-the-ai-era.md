# Preparing Rocket for the AI era

**Speakers:** Emily (Design Leader) and Will Haavik (Design Engineering Lead), Rocket Companies  
**Source:** `talks/preparing-rocket-for-the-ai-era/transcript.md`

---

## A) Summary

Emily and Will from Rocket Companies (Rocket Mortgage, Redfin, Rocket Money) describe how they embedded Figma's ecosystem into every stage of their product development lifecycle to handle the complexity of an end-to-end home ownership platform at massive scale — 800K AI chat interactions, 1.8M text messages, and 160M calls per year. The core argument is that going AI-native isn't primarily about getting access to tools; it's about ensuring those tools have something solid to build on. They walk through a live demo showing how a single component (a pre-approval letter) travels from PRD through design, research, design-system drift checking, AI-annotated implementation planning, VS Code generation using their Nova design system, and final visual verification via Playwright. The business result they cite: $1B in incremental monthly origination volume in Q1 2026, attributed to being able to test and implement new experience experiments significantly faster.

---

## B) Key points and tools

- **Nova**: Rocket's design system; every component traces back to semantic tokens (named for *why* they exist, not the value they hold); components annotated for intent, development requirements, interaction states, and content guidelines; implementation code attached via Code Connect
- **Semantic tokens**: token names encode *why* they exist ("text-primary-action") rather than *what* they are ("#0047AB"); this semantic meaning is what makes them portable across platforms, themes, and AI agents
- **Figma MCP**: used in the demo to read component metadata, retrieve token relationships, auto-annotate layers with questions about accessibility and asset export, and pass full documentation context to a coding agent in a single chat message
- **Figma Make**: used to build and share a live prototype of the AI chat experience for user research; teams can preview the chat flow without engineering help
- **Code Connect**: the mechanism that attaches each Nova component's production implementation code to the Figma component, so AI agents receive both the visual spec and the correct implementation snippet
- **Design system drift check**: Figma feature used post-design to detect hard-coded colors, detached dimensions, and accessibility contrast failures before handoff
- **Storybook**: used in the demo as the preview target for the AI-generated component implementation
- **Playwright**: used in a custom skill to take a screenshot of the Storybook component and compare it against the Figma design file — the automated visual verification step
- **Three-pass AI implementation approach**: (1) generate initial draft from component metadata; (2) review annotations and make adjustments; (3) final pass to replace any utilities with design system tokens — structured to avoid asking the agent to do everything at once
- **Airtable**: mentioned as one option for storing research variants (blue vs. green component) for research panel distribution
- **Scale**: Rocket was shipping 5x faster than 2 years earlier at time of talk; acquisition of Mr. Cooper grew servicing book from 2M to 10M homes overnight; Redfin added millions of monthly active users

---

## C) Verified takeaways (with quotes)

**1. The hardest part of going AI-native is ensuring the tools have something solid to build on — foundations first.**

This is the central message and the most broadly applicable insight. For our team, the equivalent of "semantic tokens" and annotated components is: well-named configuration keys, consistently documented API contracts, semantic Kafka topic/event naming, and ADRs that capture *why* decisions were made. Without these foundations, AI-generated code will fill gaps with defaults that don't match our standards.

> "The hardest part of going AI native isn't getting access to the tools. It's making sure the tools have something solid to build on. It starts in the small foundational moments — the naming, the structure, the components, the decisions, the context. Those details are what gives AI something trustworthy to amplify."

**2. Name things for why they exist, not just the value they hold — this is what makes systems portable across contexts and AI agents.**

"Semantic naming" is directly applicable to our team. Configuration keys like `INVENTORY_SYNC_RETRY_INTERVAL_MS` tell both humans and AI tools what the config does and why it exists. Values like `CONFIG_VAR_47` do not. The same applies to Kafka topic names, bean names, and REST endpoint paths.

> "The token name tells you why it exists, not just the value it holds right now."

**3. Annotate for intent — document the things that don't survive a screenshot but absolutely matter in production.**

This maps directly to our JavaDoc practices, PR descriptions, and ADRs. Development requirements, interaction/edge-case states, and content guidelines that are implicit in a design or code file should be made explicit. This is what gets passed to AI agents during implementation and what prevents AI-generated code from missing non-obvious production requirements.

> "We annotate for intent. Development requirements, interaction states, content guidelines — the things that don't survive a screenshot, but absolutely matter in production."

**4. Structure AI implementation tasks in passes, not one shots — avoid asking the agent to do everything at once.**

The three-pass approach (initial draft → review annotations → replace with design system tokens) reflects the same lesson as previous talks: AI produces better results when given structured, sequential instructions that build on each other, rather than a single all-encompassing request.

> "We instruct it to first start by implementing an initial draft... then take a look at the annotations and make adjustments... then do one last pass to replace any classes, utilities, etc. with our design system. That way we're taking a more structured approach versus trying to have the agent do everything all at once."

**5. Automated visual/code verification closes the loop on AI-generated implementation.**

Using Playwright to screenshot the generated component and compare it against the Figma design is the equivalent of our team writing integration tests that verify AI-generated code against a behavioral contract. The verification step cannot be skipped.

> "This skill uses Playwright to pull up Storybook, take a screenshot of the component, and then we also do the same with Figma, and compare the code and the visual representation to see if we have a match throughout."

---

## D) Role and team actions (including AI enhancements)

- **[INFERRED] Audit our naming conventions for semantic intent**: Review key naming across our services — Kafka topics, Spring Boot bean names, configuration keys, REST endpoint paths, shared library module names — and assess whether names convey *why* they exist or just *what* they are. Prioritize renaming or documenting the highest-traffic interfaces.
- **[INFERRED] Adopt the three-pass approach for complex AI-generated code**: When using AI to generate non-trivial code (a new Kafka consumer, a complex service integration, a data transformation), structure the request in three passes: initial draft → review against our standards → replace ad-hoc patterns with shared library components. Don't one-shot complex implementations.
- **[INFERRED] Close the loop on AI-generated code with automated verification**: For any AI-assisted implementation, define what "correct" means before generation, then verify against it automatically — functional tests, integration tests, or contract tests — analogous to the Playwright screenshot comparison. The verification step is the quality gate, not the generation step.
- **[INFERRED] Annotate shared service interfaces for intent**: For the APIs, Kafka schemas, and configuration structures our team owns and other teams consume, add intent-level documentation — why this field exists, what edge cases it handles, what happens when a value falls outside expected bounds. This is the data that AI agents need to implement correctly against our contracts.

---

## E) Not applicable / unclear items

- The Figma design system-specific tooling (Nova components, Figma MCP, Code Connect, Figma Make) is design-workflow-specific; the underlying patterns (semantic naming, intent annotation, structured passes, automated verification) are applicable but the tools are not.
- The home ownership domain (pre-approval letters, mortgage origination, AI chat for homebuyers) is not relevant to our team's context.
- [UNCLEAR IN TRANSCRIPT at 00:09:13–00:16:54] — the live demo section involves significant onscreen interaction with Figma, Figma Make, and VS Code that cannot be fully assessed from the transcript. The steps are described verbally but the visual output is not captured.
- The $1B origination volume metric is a Rocket-specific business outcome and is not directly applicable; the methodology (faster experimentation → measurable business impact) is the transferable insight.

---

## F) Key terms reference

| Term | Definition |
| --- | --- |
| Nova | Rocket's design system; all components trace back to semantic tokens, include intent annotations, and have production implementation code attached via Code Connect |
| Semantic tokens | Design tokens named for *why* they exist rather than the value they hold — enabling portability across platforms, themes, and AI agents |
| Code Connect | A Figma feature that attaches a component's production implementation code to its Figma component, so AI agents can retrieve both the visual spec and the correct code snippet |
| Design system drift | Deviation from the design system in a completed design — hard-coded colors, detached dimensions, accessibility failures; Figma's drift-check feature surfaces these before implementation |
| Three-pass AI implementation | The team's structured approach to AI-assisted component implementation: (1) initial draft from metadata, (2) annotation review and adjustments, (3) final replacement of ad-hoc patterns with design system tokens |
| Playwright (in this context) | Automated browser tool used in a custom skill to screenshot a Storybook component and compare it visually against the Figma design — the verification step in Rocket's AI implementation workflow |
