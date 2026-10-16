# Designing in the age of the 10x engineer

**Speaker:** Andy Zhang, Design Engineering Lead, Google Anti-Gravity  
**Source:** `talks/designing-in-the-age-of-the-10x-engineer/transcript.md`
**Session:** [View session](https://config.figma.com/san-francisco/session/49406317-eda9-427a-84f6-c88b24857ed8/)

> **Transcript completeness:** Thesis, three starting points, and recycling framework are complete in text. **Watch the recording** for the time×cost tool quadrant slide, FigJam diagram sync, typing-rhythm prototype, and abandoned interactive-graph demo.

---

## A) Summary

Andy Zhang argues that the real value of AI-powered speed isn't shipping faster — it's using that speed to gather more feedback and iterate more deeply before shipping. Pre-AI, a green-lit prototype could still be thrown away and rebuilt from scratch, losing embedded learnings; agents can now **recycle prototypes** by referencing past work so those learnings aren't lost. Zhang introduces three prototyping starting points (from scratch, isolated playground, forking production), each suited to different questions about design quality. The core thesis is that quality doesn't come from one brilliant idea or a one-shot agent output — it comes from recycling hundreds of previous prototypes, each informed by real feedback. The talk closes with a clear filter: design quality isn't measured by how much you ship or how close you are to production code — it's measured by which version you said yes to and which versions you said no to.

---

## B) Key points and tools

- **Google Anti-Gravity**: an agentic development platform for managing agents, building software, automating workflows; includes an IDE and CLI for terminal-based agent management (`[ASR: "a genetic" → agentic; "ID" → IDE]`)
- **Time × cost framing**: AI-assisted tools land in the “quick” quadrant of design tools — use that speed to answer many micro design questions, not only to ship earlier
- **Recycling prototypes**: having agents reference previous prototype code and embedded learnings so each new iteration builds on — rather than discards — prior work
- **Three prototyping starting points**:
  1. *From scratch*: best for blue-sky conceptual questions and novel interaction ideas
  2. *Isolated playground*: a safe environment with pre-built building blocks for exploring ideas without touching production; allocated time (every 2 weeks at Anti-Gravity) for structured exploration
  3. *Forking production*: starting from the ceiling of the actual product, gated for internal use, to produce iterations that can be directly handed off or gradually promoted
- **Dogfooding + gradual promotion**: active internal testing before promotion (team → larger Google groups → external); feedback confirmation at each stage
- **Feel a flow vs visualize a flow**: interactive prototypes unlock different feedback than static mockups
- **Curation / abandonment**: most agent-generated code should not reach users — e.g. an interactive agent graph that worked but he wouldn't personally use → don't ship
- **Brian Lovin / Notion prototype playground**: cited example of a deploy skill, brainstorm skill, and a sub-agent that syncs work to Figma to verify design match
- **FigJam integration prototype**: example of prototyping agents displaying output as visual diagrams rather than text (built in minutes as a proof of concept)
- **Key quality metric**: not volume of output or proximity to production code, but conviction — earned by gathering enough feedback to confidently say yes or no to a direction
- **AI ≠ users**: can't let AI decide what it can't verify with real people

---

## C) Verified takeaways (with quotes)

**1. Use AI speed to increase iteration depth, not just to ship earlier.**

This directly applies to our team's internal tool development. The ability to spin up working prototypes quickly should be used to validate concepts with stakeholders before committing to implementation, not simply to compress delivery timelines.

> "If your goal is to create high-quality experiences, this is a really good opportunity to figure out: how can we use speed to elevate quality instead of launching earlier?"

**2. Recycle prior work so agent-assisted iteration accumulates knowledge rather than resets it.**

When we build features or tools iteratively, having agents reference the codebase history, decisions, and rationale prevents context loss across iterations. This is analogous to maintaining good ADRs and code comments — but extended to the agent's working context.

> "You can recycle by reading the same agent now and have the agents reference your past work and understand all of the learnings embedded inside of the code — that way you'll never have to start from scratch again."

**3. Invest in a structured prototyping or experimentation environment, not just ad hoc experimentation.**

An isolated playground with pre-built building blocks and defined skills (deploy, brainstorm, sync) makes AI-assisted exploration faster and safer. For our team, this maps to having a well-configured local dev environment, a sandbox data layer, and reusable scaffolding that agents can work within.

> "If you don't have a prototyping playground, I'd highly encourage investing in one… to maximize the number of iterations on your product."

**4. Gatekeeping production via structured feedback loops is the quality bar — not the code itself.**

The point that most agent-generated code should never reach users — that it exists to gather feedback, build conviction, and inform a human yes/no — is directly applicable to AI-assisted code generation on our team. More agent-generated drafts should be treated as signal-gathering tools, not production candidates.

> "Agents have also made code really cheap, but that should not be a reason to ship more. Instead, we should be thinking about how to use that as an accelerant to gather more feedback, and then graduating them to the world once they've reached that bar."

**5. Quality comes from understanding who you're building for, validated repeatedly — not from a single brilliant idea.**

> "It never came from one brilliant idea, or because I managed to get an agent to one-shot it, but instead it was because I really understood who I was building for, and I got there because I repeatedly gathered a lot of feedback before sharing it with the world."

---

## D) Role and team actions (including AI enhancements)

- **[INFERRED] Define and document our team's "isolated playground"**: Establish a local development environment configuration (dev credentials, sandbox data, safe flag gates) that any team member — or agent — can spin up reliably, reducing the friction of prototyping new capabilities in internal web apps.
- **[INFERRED] Adopt a "recycle, don't reset" habit for agent-assisted development**: When using Cursor or Claude for iterative feature work, keep agents in context across sessions (via project context files, README summaries, or persistent chat history) so each iteration builds on prior learnings rather than starting cold.
- **[INFERRED] Apply staged validation before shipping**: Before promoting a new feature or API to production, establish a lightweight internal dogfooding step (team usage → broader review → release) with an explicit feedback-collection mechanism.
- **[INFERRED] Treat agent output as a draft for feedback, not a production candidate**: Normalize using AI-generated code as a starting point for rapid internal review rather than as code ready to merge — especially for complex service interactions or schema changes.

---

## E) Not applicable / unclear items

### Watch the recording (visuals / demos missing from transcript)

| Timestamp | What’s missing | Why it matters |
| --- | --- | --- |
| `00:02:17`–`00:03:18` | Time × cost tool quadrant slide | Frames where AI tools sit relative to traditional design tools |
| `00:10:12`–`00:10:53` | FigJam agent diagram sync | Visual-output prototyping example |
| `00:10:53`–`00:11:53` | Typing-rhythm / texting prototype | Rapid creative exploration demo |
| `00:12:15`–`00:12:32` | Other companies’ playground logos slide | Industry examples “over here” |
| `00:15:22`–`00:15:56` | Interactive agent graph (then abandoned) | Curation / don’t-ship lesson |

### Other notes

- The FigJam / visual diagram prototype examples are design-tool-specific and don't apply to the team's backend work.
- The Figma sync sub-agent (matching prototype to Figma design) is design-workflow-specific.
- Details about Google Anti-Gravity's specific agent orchestration platform are not transferable without access to the platform.
- The "texting prototype with typing rhythm" example is a creative exploration example — interesting as a demonstration of rapid prototyping but not applicable to the team's domain.

---

## F) Key terms reference

| Term | Definition |
| --- | --- |
| Google Anti-Gravity | Google's agentic development platform for managing agents, building software, and automating workflows; includes an IDE and a terminal CLI |
| Recycling prototypes | The practice of having agents reference past prototype code and embedded design learnings so future iterations build on — rather than discard — prior work |
| Isolated playground | A sandboxed prototyping environment with pre-built building blocks that allows exploration of ideas without risk of affecting production systems |
| Dogfooding | Internal-first testing where a team uses their own product actively, gathering feedback before any external release |
| Gradual promotion / internal gating | A structured promotion process where a feature moves through progressively larger internal audiences (team → org → all users) based on feedback at each stage |
| Deploy skill / Brainstorm skill | Agent "skills" (task-specific instructions or tools) that accelerate specific steps in the prototyping workflow — cited from Brian Lovin's Notion prototype playground |
