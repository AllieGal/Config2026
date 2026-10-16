# Your best practices are trapped in your head—and your AI has no idea

**Source:** `talks/your-best-practices-are-trapped-in-your-head-and-your-ai-has-no-idea/transcript.md`
**Session:** [View session](https://config.figma.com/san-francisco/session/dbf85ddc-ab1f-41cf-8b33-e488f14b55a7/)
**Speaker:** Harald Kirschner, Principal Product Manager, Microsoft (VS Code / GitHub Copilot)

> **Transcript completeness:** The **framework is complete in text** (`agents.md` / skills / file instructions / `spec.md` / `design.md` / skills-as-infrastructure / browser dogfooding). **Watch the recording** for all live demos — Kanban “generic vs VS Code” before/after, on-screen `agents.md` contents, marketplace plugin walkthrough, and dogfooding screenshot/visual-summary output. Those UIs are narrated but not transcribed.

---

### A) Summary

Harald Kirschner, a Principal Product Manager at Microsoft working on VS Code, argues that the reason AI-generated prototypes and code feel generic is that teams fail to encode their existing knowledge, conventions, and "taste" into the agent. The talk walks through a practical system of three file types — `agents.md` (always-loaded context), skills (on-demand workflow instructions), and file-based instructions (area-specific guidance) — that together make an AI agent behave like a team member who already knows your standards. He demonstrates building a Kanban-style agent orchestration board that instantly resembles VS Code by grounding the agent in design tokens, icon libraries, and a prototyping-specific mindset file. He also covers closing the feedback loop by giving agents built-in browser or screenshot access to evaluate their own output. The system compounds over time: the richer the context repository, the faster and more on-brand every subsequent prototype or iteration becomes.

---

### B) Key points and tools

- **`agents.md`** — a root-level markdown file always in the agent's context window; defines the project's purpose and high-level principles
- **Skills** (markdown files) — loaded on demand when the agent detects a matching workflow; can be saved directly from a completed conversation ("create a skill for what we just did")
- **File-based instructions** — attached to specific directories or files; describe how the agent should work in that area of the codebase
- **`spec.md`** — a living document capturing the conversation, decisions made, and assumptions; used to seed a new prototype session or share context with teammates
- **`design.md`** — a per-prototype log of design decisions, user context, and iteration history; serves as a transmission log between sessions
- **VS Code Team Kit** — open-source plugin/extension published to the VS Code marketplace; distributes shared skills across a team or company and keeps them updated centrally
- **Copilot Plugins / VS Code marketplace** — used as a distribution mechanism for team-level skills
- **Built-in browser / screenshot agents** — agent can open a live app, take screenshots, and self-evaluate (VS Code's built-in browser, Xcode's built-in MCP, or an MCP/CLI equivalent)
- **Persona-based dogfooding** — giving the agent a user persona and a "brutally honest" mandate to produce higher-quality UX feedback
- **MCP (Model Context Protocol)** — mentioned as an option for extending agent eyes to platforms not natively supported
- Design tokens, typography hierarchies, icon libraries (VS Code's **Codicons**) embedded into skills for instant visual fidelity
- Shift from monthly → **weekly release cycle** on VS Code team attributed partly to daily prototype-driven check-ins

---

### C) Verified takeaways (with quotes)

**1. Encode team context once; every agent session inherits it automatically.**
> "Every session you do in these agents that don't have your design skills, they start from scratch for every person in your team."

Teams repeatedly re-explaining their stack, conventions, or domain model to an AI is waste. A shared `agents.md` eliminates that.

**2. Skills should be treated as infrastructure, not one-off prompts.**
> "Treating them like infrastructure, because those are prompts that agent harnesses and models need to interpret."

As models update, prompts that worked before may degrade. Skills need versioning, maintenance, and ideally evals to confirm they still behave correctly — the same discipline applied to any shared library or config.

**3. Capture conversation decisions into a transferable artifact, not just chat history.**
> "I saved it into a spec.md. And that's me not writing a spec, it's just me kind of saving the conversation and saving all the decisions we made into something I can transfer."

This is a low-friction way to preserve architectural or design intent across sessions and team members — directly applicable to API design discussions, service planning, or internal tooling work.

**4. Close the agent feedback loop by giving it eyes on the running application.**
> "Finding feedback loops that your agents can use the application... an agent running that takes multiple screenshots from VS Code because it's a web app and reports back on what changed and what got fixed."

For the team's expanding full-stack web apps, wiring an agent to take screenshots and self-evaluate post-build is a concrete CI enhancement.

**5. Static documentation fails to drive decisions — prototypes do.**
> "You enter a meeting, nobody read your spec... if you come into a meeting with a prototype and not a whole spec, you actually talk about something real."

The same dynamic applies to service design: architecture docs and API specs written before a meeting often go unread. The pattern suggests that a working spike, a rough OpenAPI mock, or even a rough UI scaffold produces better discussion than a written spec alone.

**6. Persona-based agent review surfaces better feedback than generic "does it work?" checks.**
> "Your user research that you've been doing can feed into these personas and you can get really good feedback from the agent."

`[RELEVANCE UNCERTAIN — NEEDS CONFIRMATION]` — More applicable to UX-facing features. Less obvious for backend services, but could apply to internal tool usability reviews.

---

### D) Role and team actions (including AI enhancements)

1. **Create a shared `agents.md` for the team's AI sessions.** Codify: Java/Spring Boot microservice patterns, Kafka topic/consumer conventions, REST API standards, naming conventions, and team norms. Start minimal — only what should be in every agent's context window. `[INFERRED]`

2. **Build a skill library for common team workflows.** Candidates: "write a Kafka consumer for X pattern," "scaffold a Spring Boot REST endpoint following team conventions," "add OpenAPI annotations." Save skills from successful agent sessions rather than writing from scratch.

3. **Adopt `spec.md` / decision logs for internal tooling work.** When building internal web app features via AI-assisted sessions, save the conversation decisions to a transferable doc. This preserves intent for code review and future sessions.

4. **Treat agent configuration files (agents.md, skills) like infrastructure.** Apply versioning, peer review (PR process), and ideally lightweight evals when models or agent harnesses are updated.

5. **For full-stack web app work, add a screenshot/browser review step to CI.** After a front-end build, trigger an agent to capture screenshots and diff against a baseline — the technique directly demonstrated on VS Code. Tools: VS Code's built-in browser agent or an MCP-connected browser. `[INFERRED]`

6. **Build a "product brain" repository for team knowledge.** Centralize all evidence in one place: architecture decision records, past AI session specs, API design decisions, user research, and prototype outputs. The idea is that every future agent session draws from a richer pool of context rather than starting from zero. This is the cumulative payoff of items 1–5 above. `[INFERRED]`

7. **Explore VS Code Team Kit (open source)** as a reference implementation for structuring a team plugin/skill distribution system.

---

### E) Not applicable / unclear items

### Watch the recording (visuals / demos missing from transcript)

| Timestamp | What’s missing | Why it matters |
| --- | --- | --- |
| `00:04:21`–`00:05:39` | Live Kanban agent-orchestration board (generic / “Opus” look) | Shows the “looks cool, not our product” failure mode |
| `00:06:07`–`00:06:39` | Same idea rebuilt with design skills → VS Code–looking prototype | Proof that encoding taste changes output |
| `00:09:08`–`00:10:22` | On-screen `agents.md` contents + prototyping principles | Exact wording of his root context file |
| `00:10:22`–`00:11:37` | Design-system skill contents (tokens, Codicons, type, depth) | What’s actually in the skill vs. paraphrased |
| `00:11:37`–`00:12:36` | `design.md` transmission-log UI | Structure of the per-prototype log |
| `00:13:04`–`00:14:05` | VS Code / Copilot plugin marketplace + VS Code Team Kit browse | How skills are distributed org-wide |
| `00:18:37`–`00:19:55` | Dogfooding skill run: screenshots, pass count, visual summary of feedback | What “brutally honest” agent feedback looks like |
| `00:19:55`–`00:20:37` | “Product brain” repo layout / link on slide | How evidence compounds in one place |

### Other notes

- **Design system skill / Codicons** — VS Code–specific; the *pattern* transfers to internal web apps.
- **Figma prototyping workflows** — not our primary context; API/service design is the analogue.
- `[UNCLEAR IN TRANSCRIPT]` `00:15:56` — “Xcode built-in CP”; likely MCP/agent tooling, but acronym is ambiguous — **confirm in video**.
- Monthly → weekly release: attributed partly to daily prototype check-ins; not causally proven from transcript alone.
- **Speaker name ASR:** transcript says "Hari Krishna"; official listing is Harald Kirschner (header uses official).

---

### F) Key terms reference

| Term | Definition |
| --- | --- |
| `agents.md` | Root markdown file always loaded into the agent's context window; defines project scope and working principles |
| Skills | Modular markdown files encoding specific workflows or knowledge; loaded on demand when agent detects a matching task |
| Instructions | File- or directory-scoped markdown files telling the agent how to work in a specific area of the codebase |
| `spec.md` | Artifact capturing conversation decisions, questions, and assumptions from an AI session; transferable to new sessions or teammates |
| `design.md` | Per-prototype log of design decisions, user context, and iteration history; serves as a transmission record between sessions |
| Product brain | A single repository centralizing all research evidence, prototypes, AI session outputs, and decisions — compounds in value over time |
| Dogfooding agent | An AI persona configured to critically evaluate the product like a real user; produces honest, structured UX feedback |
| Plugin marketplace | Distribution mechanism (e.g. VS Code marketplace) for sharing and updating team-level skills org-wide |
