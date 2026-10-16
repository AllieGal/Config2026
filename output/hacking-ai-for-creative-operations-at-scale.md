# Hacking AI for creative operations at scale

**Speaker:** Rory Flynn, founder, Systematic AI  
**Source:** `talks/hacking-ai-for-creative-operations-at-scale/transcript.md`

---

## A) Summary

Rory Flynn, founder of an operational AI agency, presents three core skills for building scalable, multi-tool AI workflows — primarily in the context of creative asset production. The central problem he calls "creative inflation": the never-ending demand for new creative assets across multiple channels, formats, and variants at a pace that individual effort cannot sustain. His framework — deconstruction, system prompts, and workflow development — is presented as a tool-agnostic approach to thinking in systems rather than one-off generations. He demonstrates the framework using Figma Weave (a node-based workflow builder with 300+ integrated AI tools) through real client examples with BarkBox (composite product photography) and Shark Ninja (product localization across 35 markets). The closing principle: if only you can operate a workflow, it isn't a system — build for everyone, and design so the workflow stays the same while only the input changes.

---

## B) Key points and tools

- **Figma Weave**: a node-based AI workflow builder with access to 300+ AI tools in one workspace; enables chaining AI actions on an infinite canvas where one generation feeds the next; replaces the copy-paste-between-tools workflow
- **Systematic AI**: Flynn's operational AI agency, which embeds AI workflows inside client organizations to solve creative operations problems at scale
- **Creative inflation**: the compounding demand for more creative assets at faster pace across more channels, formats, and variants — the structural pressure that makes ad-hoc AI generation insufficient
- **Three core skills**:
  1. **Deconstruction**: reverse engineer a piece of media into its core components ("non-negotiables"); use these components to build prompt formulas; example — a photo has lighting, subject, composition, etc. as non-negotiables
  2. **System prompts**: write rules once that govern an LLM's behavior; the LLM follows them consistently without being re-prompted; especially useful in node-based tools where information passes automatically between nodes; structure: who it's acting as → what it receives → what to do with it → how to output → what not to do
  3. **Workflow development**: stringing nodes together into a repeatable pipeline; the workflow stays fixed, only the input changes
- **Text iterator node**: splits multiple LLM outputs (e.g., 4 prompts) into individual inputs for parallel generation
- **Router node**: takes one input and sends it to multiple outputs simultaneously
- **BarkBox example**: two workflows — (1) monthly composite product photography automated in Weave: inputs (toys, treats) change each month, compositor node + lighting system prompt generates 3D-feeling composite shots; (2) sales presentation pipeline for pitching new licensing partners: 4-click, four-system-prompt chain from 2D vector toy design → 3D image → 9 angles (with seam logic, texture, mapping) → scale reference (toy size vs. dog size) → studio shots
- **Shark Ninja example**: a large-scale localization workflow across 25 product categories and 35 global markets; started with localizing creative assets (different markets need different visuals) and expanded into retouching, environment/product fixes, traditional compositing, asset depth, and video localization; illustrates how one workflow bleeds into an entire organization
- **Scale reference**: an intermediate image that establishes size context (e.g., toy vs. dog size) to prevent proportional inconsistencies in downstream generations
- **"Screw the models"**: build structured workflows so specific model choices can be swapped out as tools change; structure > specific tool
- **"If only you can operate it, it's not a system"**: workflows should be handoff-ready and operable by others

---

## C) Verified takeaways (with quotes)

**1. Build structured, reusable workflows rather than one-off AI interactions — the same principle applies to any repeatable AI-assisted task.**

The creative operations context (image generation, product photography) is domain-specific, but the underlying framework is directly applicable to our team. Any AI-assisted process we use repeatedly — code scaffolding, documentation generation, schema migration planning — should be designed as a workflow with stable structure and interchangeable inputs, not as a series of ad-hoc prompts.

> "You only have to change the input... And when these workflows are built scalable and structured appropriately, 95% of the time they don't have to change."

**2. Deconstruction — understanding what makes something good before prompting — produces consistently better results than prompt-and-pray.**

For our team, this applies to how we write prompts for AI coding assistants. Before prompting for a Spring Boot service, a Kafka consumer, or a REST endpoint, decomposing what a "good" implementation looks like (error handling patterns, logging conventions, configuration structure) and encoding that into a system prompt or prompt template produces more repeatable, on-standard results.

> "Deconstruction... is how do we take a piece of media, break it down into its core components, and that will teach us how to prompt. It will also teach us how to write formulas."

**3. System prompts are the mechanism for removing yourself from repetitive AI loops — and they're especially powerful in automated pipelines.**

A system prompt written once and attached to a node governs LLM behavior consistently without manual re-prompting. The engineering equivalent is a well-crafted context file (e.g., a `CLAUDE.md` or Cursor rules file) that captures team conventions once and applies them consistently across all AI-assisted sessions.

> "System prompts [are] specific rules that govern the LLM. You write it once, the model follows it, takes you out of the loop."

**4. Design workflows for delegation, not personal use — if only you can operate it, it isn't a system.**

This is directly applicable to any AI tooling our team builds internally (test generators, migration helpers, documentation tools). If the workflow requires deep knowledge of how it was built to operate it, it won't get used by the team.

> "If only you can operate it, then it's not really a system, right? If it's built for everyone, then they can take it and run with it."

---

## D) Role and team actions (including AI enhancements)

- **[INFERRED] Build reusable prompt templates (system prompts) for our most common AI-assisted tasks**: Identify the top 5 repeated AI-assisted activities on the team (e.g., scaffolding a Spring Boot controller, writing a Kafka consumer, generating unit test skeletons, drafting ADRs) and write a system prompt or context document for each — capturing the non-negotiables (patterns, conventions, error handling standards) so the AI produces on-standard output without repeated manual correction.
- **[INFERRED] Document AI workflows for delegation**: When building any AI-assisted process, document it in a way that a teammate who didn't build it can operate it independently. Include: what the inputs are, what the system prompt governs, what to do when it fails, and how to update it as conventions change.
- **[INFERRED] Decouple workflows from specific model choices**: Design any AI-assisted tooling so that the underlying model or tool can be swapped (e.g., Claude → GPT → Gemini) without restructuring the workflow — the stable interface is the system prompt and the data format, not the specific model vendor.

---

## E) Not applicable / unclear items

The majority of this talk is not directly applicable to the team's work:

- Figma Weave, image-to-image models, composite product photography, font generation from images, 2D vector-to-3D workflows, and video localization are creative operations tools and techniques with no backend engineering analog.
- BarkBox and Shark Ninja case studies are creative production contexts (product photography, marketing assets) not relevant to our domain.
- The specific node types (compositor node, router, text iterator) are Figma Weave-specific.
- [UNCLEAR IN TRANSCRIPT at 00:07:16–00:08:08] — references to on-screen demos of workflow building in Figma Weave involve visual interactions that cannot be fully assessed from the transcript.

The three core skills (deconstruction, system prompts, workflow development) are the transferable framework; the implementations shown are creative-domain-specific.

---

## F) Key terms reference

| Term | Definition |
| --- | --- |
| Figma Weave | A node-based AI workflow builder within Figma that gives access to 300+ AI tools on an infinite canvas, allowing AI actions to be chained together into reusable pipelines |
| Creative inflation | The speaker's term for the compounding demand for more creative assets at faster pace and across more channels and formats — the structural pressure driving the need for scalable AI workflows |
| Deconstruction | The process of breaking a piece of media or output into its core components ("non-negotiables") to build reusable prompt formulas; the speaker's first and favorite skill for AI workflow design |
| System prompt | A set of rules written once that governs how an LLM behaves in a workflow — it specifies who the model is acting as, what it receives, what to do with it, and how to output — and persists without re-prompting |
| Text iterator node | A Figma Weave node that splits a multi-output LLM response (e.g., four prompts) into individual inputs for parallel downstream processing |
| Scale reference | An intermediate image generated to establish size context (e.g., toy vs. dog proportions) that prevents proportional inconsistency in downstream AI image generations |
| Workflow development | The skill of designing and sequencing a chain of AI tool nodes from input to output — the stable structure that only requires input changes between uses |
