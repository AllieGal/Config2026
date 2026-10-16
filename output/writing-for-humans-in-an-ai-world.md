# Writing for Humans in an AI World

**Speaker:** Chelsea, Content Design Lead at Anthropic
**Source:** `talks/writing-for-humans-in-an-ai-world/transcript.md`

---

### A) Summary

Chelsea, content design lead at Anthropic, describes the professional and philosophical adjustments she has made after joining an AI company as a writer — the role she thought AI was eliminating. Her central argument is built around three shifts she has had to make: (1) recognizing that language is now a primary design medium, not just a communication layer on top of design; (2) accepting that the pace of AI change is relentless and that designers and builders must act as the "translation layer" helping people understand what is possible; and (3) confronting the responsibility of designing a future that is being set right now, before anyone knows what it will look like. She illustrates each with concrete examples from Anthropic — a memory export prompt reframed around data portability, surfacing hidden MCP connectors through conversational affordances, and choosing "co-work" over "agent mode" as naming that shapes a mental model for millions. She argues that human thriving must be the deliberate design goal, not an emergent byproduct of getting capabilities right.

---

### B) Key Points and Tools

- **The role of language has fundamentally changed**: It used to be the medium for *communicating about* design; now it is often the medium that *shapes* the experience itself. LLMs are built on language, and language is used to tell them what to build.
- **String changes → production in 20 minutes**: What used to take two weeks (string updates through Figma files, PM, engineering, localization) now takes 20 minutes — Chelsea tells Claude what she wants, it updates the repo, sends a PR, and she stamps it. "The part of my job where I was painstakingly shaping strings is mostly gone."
- **Memory export prompt case study**:
  - First attempt: prompt used phrases like "it is my right, it is an imperative" — pattern-matched to a demand letter or jailbreak attempt; model hedged and produced a thin result.
  - Reframe as "data portability" — models understand this as a legitimate user right and pattern-match to account migration. Result: dramatically more complete memory export.
  - An engineer then rewrote it as a checklist and got even more memories.
  - Lesson: "Language is design. We changed the words, the product experience changed. That is all we changed."
- **System prompts and training are the foundational design layer**: Claude's character (e.g., "diplomatically honest rather than dishonestly diplomatic") is programmed via system prompt and training before Claude ever meets a user. Everything in the product experience sits on top of this layer. Adding "sarcastic, witty, and dry" to a vibe description turned Claude into "a bit of a creep" — engineers had to ask it to be nice again.
- **The capability gap**: The gap between what people think AI can do and what it can actually do — and this gap is growing, not shrinking. Designers and builders must close it.
  - Connectors (Anthropic's term for MCPs): 3–4 clicks deep, 1–2% of users found them. Users were asking Claude for capabilities (schedule management, project management) that connectors could fulfill, but Claude didn't know to suggest them. A prompt-based affordance brought connectors into the conversation — adoption increased significantly.
- **"Agent mode" vs. "co-work" naming case study**:
  - Feature was internally called "Claude Code for knowledge workers" → became "agent mode."
  - Research showed knowledge workers didn't want to manage "uninhabited task loops" — they wanted a tool that expanded their capabilities and made them feel more skilled.
  - After significant internal pushback and UXR validation, the feature was named "co-work."
  - "Co-work" became category-shaping language: Microsoft adopted it directly for "co-pilot co-work powered by Anthropic."
  - Lesson: naming shapes mental models, and mental models shape product trajectories. Calling it "agent mode" would have severely limited how people perceived it.
- **The "Content" agent**: Chelsea's team built an AI agent named "Content" that does 90% of their UX writing. Human-in-the-loop mechanism: a weekly ballot system where the team votes on whether changes go into the agent's memory. The agent knows to ping a human for anything important (especially naming — "we do not let Content name things"). Result: expanded team reach and scope, not replacement.
- **Designing the future (the existential adjustment)**:
  - Comparison to cars: when cars arrived, design defaults favored bigger roads and smaller sidewalks. No one set out to hurt pedestrians, but values encoded in the design (making it easier for cars to get around) shaped the city for generations.
  - Comparison to social media: endless scroll, likes, engagement-weighted algorithms — no one set out to hurt teenagers' attention spans, but those patterns proliferated and became defaults.
  - "Design encodes values. The values that we have today and the values that we encode in our designs are going to shape the next 10 years at least."
  - "Give your agent legs" flyer — framing that makes a human a sub-agent of an AI. Chelsea asks: is that a value you want to proliferate?
- **Design principles stated**:
  - "Human thriving has to be the goal that we design around. It can't be this thing that just emerges if we get the capabilities right."
  - "Give users a meaningful role" — if anything, when designing AI experiences, ask: "Did I leave room for the person?"
  - Design against addictive patterns. Eval against sycophancy.
  - Don't stop doing what you do best — specialized craft skills still matter.
- **CPO Ami Vora quote**: "Technology is changing at a rate that is hard for anyone to understand."
- **Tools/concepts mentioned**: Claude, Claude Code, system prompts, evals, MCPs (called "connectors" at Anthropic), Figma, Git/PRs, co-work feature.

---

### C) Verified Takeaways (with Quotes)

- **Language is now a primary engineering medium — prompt quality directly determines output quality.**
  > "Language is now a primary design medium...we changed the words, the product experience changed. That is all we changed in the design to get different outcomes."

  Directly applicable to the team's use of AI coding tools. How an engineer frames a prompt — the vocabulary, the framing, the level of specificity — determines the quality of AI-generated code, test stubs, or documentation. This is a skill the team should deliberately develop, not treat as incidental.

- **Understand the system prompt / tool description layer — it is the actual experience.**
  > "Get under the hood, read your system prompts, understand your tool descriptions, write your own evals, and shape that layer because that is actually the experience."

  Directly applicable. If the team builds or uses AI-powered features (in internal tools, in Claude-integrated workflows, or in future eCommerce AI features), the system prompt and tool descriptions are the actual product — not just configuration. Engineers who understand this layer have architectural leverage that those who treat it as a black box do not.

- **The capability gap must be actively closed by design — users don't find what they don't know exists.**
  > "We know from our research that people expect AI to tell them what it can do. But if you don't design the AI to do that, then that gap is going to remain."

  Applicable to internal tooling. If the team's internal web apps have capabilities that users don't discover, the problem is likely not the UI — it may be a mental model or affordance gap. AI-powered features in particular need to announce their own capabilities contextually.

- **Naming shapes mental models and can become category-defining — naming decisions are architecture decisions.**
  > "I really think if we had called it co-work agent mode, we would have severely limited the way people perceive it. And co-work is now becoming category-shaping language."

  Applicable to the team's API naming, Kafka topic naming, internal tool naming, and any new concepts introduced in the codebase or documentation. Names that accurately frame the mental model of what something does are not just style — they shape how engineers, consumers, and future team members build on them.

- **The "Content" agent model: human-in-the-loop with a ballot system is a concrete, transferable pattern.**
  > "Somebody on my team set it up so that it creates a ballot system every week that we vote on. So if it made a change, we vote whether or not that's going to go into its memory. And it also knows to ping one of us if something like really important happens."

  `[INFERRED]` The team could apply this pattern to an AI coding agent: let the agent handle boilerplate generation and routine refactors, but require team review for any output that touches conventions, naming, or critical system logic before it is encoded as a permanent rule. The ballot/vote mechanism is a lightweight human-in-the-loop that scales.

- **Evals are a design tool, not just a testing tool.**
  > "Write your own evals, and shape that layer because that is actually the experience."

  `[INFERRED]` If the team builds AI-powered features or workflows, evaluations (evals) that test for desired behavior — not just correctness — are a first-class design responsibility. This is especially relevant for any AI that generates user-facing content, recommendations, or decisions in the eCommerce context.

- **Design against addictive patterns and sycophancy — these are concrete, actionable principles.**
  > "We know what addictive design looks like. We've all felt it in our devices. Design against that. We also know that models that just tell you what you want to hear are sycophantic. Eval against that."

  Applicable to any AI feature the team builds: an AI that always returns results, always agrees with inputs, or never surfaces uncertainty is a sycophantic system. Build in honest uncertainty signaling and design for meaningful human decision-making.

---

### D) Role and Team Actions (Including AI Enhancements)

- **Invest in prompt engineering as a team skill.** Treat prompt quality the same way the team treats code quality: review it, version it, improve it. Document prompt patterns that produce reliable results for common tasks (generating Kafka consumer stubs, scaffolding Spring Boot services, writing OpenAPI specs) and share them as team assets. `[INFERRED]`
- **Read and understand the system prompts and tool descriptions for AI tools the team uses.** Don't treat Cursor, Claude, or any AI tool as a black box. Understanding the system-level instructions shaping those tools' behavior lets the team configure them more precisely and anticipate failure modes. `[INFERRED]`
- **Apply the "capability gap" lens to internal tooling.** For any internal app: map the gap between what the tool can do and what users think it can do. If key capabilities have low adoption, the fix is likely an affordance or mental model problem — not a feature problem.  `[INFERRED]`
- **Write your own evals for any AI-assisted workflow or feature.** Define what "good" looks like, what "sycophantic" looks like, and what "harmful" looks like in the context of whatever the AI is doing. Then test for it explicitly. This is a prerequisite for deploying AI-powered features with confidence. `[INFERRED]`
- **Apply the "give users a meaningful role" principle to internal AI tools.** When building AI-augmented internal workflows (e.g., an AI that drafts configuration changes, suggests schema migrations, or generates test data), ensure the human has a clear, meaningful decision point — not just a rubber-stamp step. The ballot mechanism from the "Content" agent is a concrete model. `[INFERRED]`
- **Name things with the mental model in mind.** Before finalizing names for new APIs, events, internal tools, or features, ask: does this name accurately frame what the thing does and how it should be used? A name that encodes the wrong mental model creates confusion that compounds as the team, the codebase, and the consumer base grow.  `[INFERRED]`

---

### E) Not Applicable / Unclear Items

- The speaker's personal experience as a content/UX writer is specific to her role and not directly applicable to Java backend engineering.
- The memory export prompt case study is specific to AI product design at Anthropic. The underlying language-shapes-outcome principle transfers; the specific Claude memory system mechanics do not.
- The social media / car / city-design historical framing is motivational and contextual. The design responsibility principles are extractable (and included above), but the historical analysis itself is not actionable for the team.
- The "existential dread" framing and the broader "we are building the future" narrative is most relevant to product designers and those making product-level decisions about AI features. Individual contributors on the backend services team may have less direct exposure to these decisions.
- The slide that references an AI capability metrics chart (00:14:06) appears to show a significant metric uplift from the connectors affordance work, but the specific number is not stated in the transcript. `[UNCLEAR IN TRANSCRIPT]` at approximately 00:14:06.

---

### F) Key Terms Reference

| Term | Definition |
| --- | --- |
| Language as design | The shift in which language — specifically, how something is prompted, named, or framed — directly shapes the product experience, rather than serving only as a communication layer on top of a visual design. |
| System prompt | Instructions encoded at the foundational level of an AI model's behavior, determining its character, tone, and constraints before any user interaction occurs; distinct from product-level or user-level prompts. |
| Capability gap | The gap between what users think an AI (or any product) can do and what it actually can do; a growing design problem as AI capabilities advance faster than user mental models. |
| Connectors | Anthropic's term for MCPs (Model Context Protocol integrations) that extend Claude's capabilities by connecting to external tools such as calendars, project management systems, etc. |
| Co-work | The name Anthropic shipped for what was internally called "agent mode" — an agentic working paradigm for knowledge workers framed around collaborative human-AI working rather than delegating tasks to autonomous agents. Became category-shaping language adopted by Microsoft. |
| Evals | Short for "evaluations" — structured tests of an AI model or AI-powered system's outputs against defined quality criteria, used to catch sycophancy, harmful behavior, or capability regressions before users encounter them. |
| Sycophancy (AI context) | The behavior of an AI model that tells users what they want to hear rather than what is accurate or genuinely helpful; a failure mode that the speaker advocates explicitly testing against. |
| Human-in-the-loop | A workflow design pattern where an AI handles routine tasks autonomously, but a human is required to review, approve, or veto specific categories of decision before they are finalized or committed. |
| Diplomatically honest rather than dishonestly diplomatic | A character principle encoded into Claude via system prompt and training; instructs Claude to push back respectfully when it disagrees, rather than agreeing to avoid discomfort. |
