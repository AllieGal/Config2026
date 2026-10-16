# The Metacognitive Design Loop

**Speakers:** Jenny Au (Team Lead, UX QA Engineering) and Mike Green (Team Lead, Product Design), Epsilon / Publicis Groupe  
**Source:** `talks/the-metacognitive-design-loop/transcript.md`  
**Session:** [View session](https://config.figma.com/san-francisco/session/6c44950a-077d-47bf-bad1-8cc71f995957/)

> **Note on names/titles:** Transcript self-intro uses first names only (“Jenny… lead of the UX QA engineering team”; “Mike, UI design lead”). Full names and official Config titles above.  
> **Transcript completeness:** Loop, IEU, stats, and tools are spoken. **Watch the recording** for the architecture diagram, table bug UI, Code Connect naming example, and QR prompt/templates.

---

### A) Summary

Jenny Au and Mike Green from Epsilon describe how they rebuilt their design-to-development workflow around a self-correcting AI system after manual QA became impossible at scale: 60+ applications, 50+ components, 30+ subcomponents, 200+ style tokens, 100+ rules/patterns, and 4 billion possible combinations. Their central claim is that the solution wasn't smarter AI — it was AI that audits itself, a capability they call metacognition. They built a six-step metacognitive design loop (ingest, plan, build, then self-check / loop-until-pass, then solidify via Git) powered by a custom MCP (Core UI MCP, giving the AI direct access to live Figma tokens and their rule engine) and a BRD agent (which interviews product owners and translates requirements to component-level specs). Every rule correction is committed to Git, making the system progressively smarter. The result: projects that used to take two months to build and QA now take two hours, with no loss of precision.

---

### B) Key Points and Tools

- **Scale framing:** small UX QA team outnumbered ~100:1 vs 20+ product designers and a dozen eng teams; apps include audience builder, campaign management, loyalty
- **The "pendulum of failure"**: Two failure modes in AI-assisted governance — *paralysis from over-governance* (checking every rule by hand slows everything to a halt) and *chaos from under-governance* (rules not enforced consistently; small inconsistencies stack until the experience fragments). The goal is equilibrium: move fast without losing precision.
- **Metacognition defined**: "Thinking about thinking. The ability to reflect on a mistake, diagnose it, and rewrite the rules to prevent it from happening again." Standard AI stops after the "build" step and throws output over the fence. Their system adds steps 4–6.
- **The six-step metacognitive design loop**:
  1. Ingest
  2. Plan
  3. Build
  4. Check — AI checks its own work against Core UI `[UNCLEAR IN TRANSCRIPT — step name likely from slides; spoken as “checks… its own work”]`
  5. Self-correct — loops automatically until every rule passes `[same caveat]`
  6. Solidify — every correction triggers a Git commit (“step six solidifies…”), making the process smarter after each use
- **Core UI MCP**: A custom MCP they built that gives the AI direct access to live Figma tokens — no approximation, no assumptions. It pulls from the latest component catalog, runs every rule the system has ever learned, and self-corrects before a human sees the first output. Includes a dedicated UX QA tool with an embedded Core UI knowledge base so the AI never drifts from the source of truth. (Protects **code** fidelity.)
- **BRD Agent (Business Requirements Document Agent)**: Interviews the product owner with structured questions (who are the users? what's out of scope?), translates plain English into exact Core UI components, flags gaps as "concept slots" for designers to review, and requires explicit PO approval before prototyping handoff. Spoken flow: **Set up → Generation → Review and approve**. (Protects **strategy**.)
- **Figma Code Connect**: Used to align naming between the coded library and the Figma/Storybook library. Building Code Connect files revealed a naming mismatch ("two-tier site header" vs. "double-tier site header") — the same component with two different names, which is a prompting failure waiting to happen.
- **The IEU Framework (Identify, Evaluate, Update)**:
  1. **Identify**: Ask the AI "Why did you do that?" — surface the heuristic it used.
  2. **Evaluate**: Compare that reasoning to exact design standards.
  3. **Update**: Encode a permanent rule so the same mistake never recurs.
  - "It's like mentoring your junior assistant, but the best part is you only have to tell them that they are wrong for exactly one time."
- **Concrete bug example**: AI treated a table header and data rows as two separate layout problems, breaking column alignment. Rather than fixing the design file manually, they used the IEU framework to encode "the table must be treated as one straight vertical grid" as a permanent rule — so the same bug will not recur.
- **Naming consistency is a prompting prerequisite**: "Consistent naming isn't just a style preference, it's what makes precision and predictability possible."
- **Result**: Projects that previously took 2 months to build and QA now take 2 hours.
- **Architects' challenge (three principles)**:
  1. Treat your design system as code, not static pages.
  2. Mentor your AI — ask *why* it made a decision, not just ask it to fix the outcome.
  3. Build an immutable system so you don't fix the same bug every sprint.
- **Tools mentioned**: Figma, Figma Code Connect, Core UI MCP (custom-built), BRD Agent (custom-built), Jira, Storybook, A2UI (referenced as a tool at the design–engineering boundary), Git.

---

### C) Verified Takeaways (with Quotes)

- **The self-correcting AI loop (build → check → correct → encode) is the key architectural shift — directly transferable to code generation pipelines.**
  > "Standard AI stops at step three. And it builds and then it throws the output across the fence for us to fix. We have eliminated that by building step four and five. Our AI checks against the Core UI its own work and then it loops automatically until it passes every single rule."

  The team can apply this pattern to AI-assisted code generation: rather than accepting the first AI output, build or configure a workflow where the AI checks its output against team conventions (naming standards, Spring Boot patterns, Kafka consumer conventions) before presenting it.

- **Custom MCPs as a grounded source of truth for AI — directly applicable to the team's systems.**
  > "The first is the Core UI MCP. It gives us direct access to our Figma live tokens, so no approximation, no assumptions. It builds strictly and pulls from the latest component catalog...runs every rule it's ever learned and self-corrects repeatedly before a human ever sees the first output."

  The team could build analogous MCPs exposing our own API schemas, OpenAPI specs, database models, or Kafka topic/event schemas. This would let AI tools reason about our actual system rather than approximating from training data — directly improving the quality of AI-generated integration code, test stubs, and documentation.

- **The IEU framework: stop fixing bugs, start mentoring logic.**
  > "We stopped fixing bugs and we started mentoring logic. First, we identify the heuristic by asking the AI, 'Why did you do that?'...we update the rules engine so the same mistake never happens again."

  `[INFERRED]` The team can apply IEU when using AI tools (Cursor, Claude) for coding tasks: when AI produces an incorrect pattern, don't just correct the output — ask why, compare to team standards, and encode the correction in a `.cursorrules` file, a system prompt, or an agent instruction set. The same bug stops recurring.

- **Every correction as a Git commit creates an auditable, improving ruleset.**
  > "Every correction triggers a Git commit that makes our process smarter and more reliable after each use, creating our desired equilibrium."

  The principle that governance improvements should be versioned and persistent — not just done in the moment — is directly applicable to managing AI coding conventions. Team-level prompt rules, linting configurations, and architecture decision records (ADRs) are the engineering equivalent.

- **Naming consistency between design and code is a prompting prerequisite — and a risk for any AI-assisted workflow.**
  > "Consistent naming isn't just a style preference, it's what makes precision and predictability possible."

  The team should audit whether AI tools are using consistent naming across our Java domain models, API contracts, OpenAPI specs, Kafka topic names, and documentation. Any mismatch is a "prompting failure waiting to happen."

- **The BRD agent pattern: translate requirements into component-level specs before design or development begins.**
  > "The worst moment to discover what you're actually building is wrong is when the design and the development work has already begun."

  `[INFERRED]` By analogy: a "requirements agent" that interviews a product owner and translates Jira story text into API contract drafts, data model proposals, or event schema suggestions — with explicit flags for ambiguous gaps — could reduce the cost of misaligned requirements in the team's delivery process.

- **Agentic workflows without governance don't just make mistakes — they set governance back.**
  > "When agentic workflows run without governance… They can set governance back further than where we started." `[ASR: earlier clause says “just don’t produce mistakes” — likely “don’t just”; meaning from context]`

  Directly applicable as a caution for the team's AI adoption. AI-generated code that violates team conventions compounds technical debt faster than manually written code, because it's generated at scale. Governance must be built in, not added after the fact.

---

### D) Role and Team Actions (Including AI Enhancements)

- **Build an MCP (or equivalent) exposing the team's actual system schemas.** Create a custom MCP or structured context file that gives AI tools direct access to our OpenAPI specs, Kafka event schemas, and key domain model definitions. This eliminates approximation and ensures AI-generated code uses our actual types and conventions. Start with the highest-volume integration surface (e.g., product catalog API or inventory events). `[INFERRED]`
- **Implement IEU as a team practice for AI corrections.** When an AI tool generates code that violates team conventions, don't just fix the output — document the correction as a rule. Encode it in `.cursorrules`, a shared agent system prompt, or an architectural decisions file. Make it a team habit: if you corrected it once, the rule should exist so you never correct it again. `[INFERRED]`
- **Audit naming consistency across design/code/documentation.** Conduct a lightweight audit comparing Java class names, API field names, OpenAPI spec names, Kafka topic names, and any internal documentation. Inconsistencies are prompting failures waiting to happen as AI tooling usage scales. `[INFERRED]`
- **Pilot a "check before handoff" step in AI-assisted code generation.** For any AI-generated code (controller stubs, Kafka consumers, service layer scaffolding), add an explicit review step where the output is checked against a defined checklist of team conventions before it enters a PR. Over time, automate this with a linter or AI reviewer. `[INFERRED]`
- **Apply the BRD agent concept to requirements intake.** For stories involving new API endpoints or event schemas, experiment with having an AI agent interview the product owner or team lead using structured questions, then produce a draft API contract or event schema with explicit gaps flagged. This brings QA to the front of the workflow. `[INFERRED]`
- **Reframe AI governance as architecture work, not QA gatekeeping.** The talk's central shift — from gatekeeper to architect — is directly applicable. Engineers who build AI-assisted workflows with self-correcting rules, encoded conventions, and grounded sources of truth are doing architecture work, not policing.

---

### E) Not Applicable / Unclear Items

### Watch the recording (visuals / demos missing from transcript)

| Timestamp | What’s missing | Why it matters |
| --- | --- | --- |
| `00:02:14`–`00:03:02` | Scale / pendulum slides (slide glitch acknowledged) | Visual scale of Core UI |
| `00:05:22` | Architecture diagram of the metacognitive loop | Step labels for 4–5 may be on-slide |
| `00:08:12`–`00:09:28` | BRD agent workflow slides | Set up → Generation → Review |
| `00:10:02` | Code Connect naming mismatch “up here” | two-tier vs double-tier example |
| `00:11:41`–`00:13:30` | Broken table UI + IEU applied | Primary bug-fix demo |
| `00:15:11` | Round-trip / browser-as-canvas claims | End-to-end output path |
| `00:18:59` | QR: prompts, templates, Jenny’s IEU tool | Not recoverable from transcript |

### Other notes

- Figma-specific tooling (Code Connect, live token access, Figma MCP) is not directly applicable — only the underlying principles transfer.
- UI-specific concerns (spacing, design tokens, visual layout, component hierarchy in Figma) are not applicable to the backend context.
- Do not adopt transcript ASR slips: one-off “PRD agent,” “Genie,” “butt modal,” “deck tech debt.”

---

### F) Key Terms Reference

| Term | Definition |
| --- | --- |
| Metacognition | "Thinking about thinking" — in this context, an AI system's ability to reflect on its own output, diagnose an error, and update its own rules to prevent the same mistake from recurring. |
| Metacognitive design loop | Epsilon's six-step workflow: Ingest → Plan → Build → Check (self-audit) → Self-correct (loop until rules pass) → Solidify (Git commit to encode the correction). |
| Pendulum of failure | The speaker's name for the two failure modes in governance: over-governance (paralysis from checking everything manually) and under-governance (chaos from inconsistent enforcement). |
| Core UI MCP | Epsilon's custom MCP that gives AI direct access to live Figma design tokens, the component catalog, and the accumulated rule engine — eliminating approximation. |
| BRD Agent | Business Requirements Document Agent — an AI agent that interviews product owners, translates plain-English requirements into component-level specifications, and flags gaps before design or development begins. |
| IEU Framework | Identify, Evaluate, Update — a three-step method for teaching AI a rule: ask why it made a decision, evaluate the reasoning against the design standard, then encode a permanent correction so the mistake never recurs. |
| Concept slot | A placeholder flagged by the BRD Agent when it cannot find an exact design system component match for a specified feature, indicating a gap that requires human designer review. |
| Figma Code Connect | A Figma feature that maps Figma component instances to their corresponding code implementations, enabling consistent naming and behavior between the design file and the codebase. |
