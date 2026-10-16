# AI will upend your process—for the better

**Source:** `talks/ai-will-upend-your-process-for-the-better/transcript.md`
**Session:** [View session](https://config.figma.com/san-francisco/session/b751e092-79d1-4082-9c8f-aeeba6ec3b0e/)
**Speaker:** Justin Meyer, CEO, Bitovi (self-intro: leading Bitovi’s AI enablement practice)

> **Transcript completeness:** Core journey, skills, and tooling are spoken. **Watch the recording** for live demos (Convey, React→Figma visual diff, design-review questions in Figma, cloud Copilot / Bitovi agent).

---

### A) Summary

Justin Meyer (CEO, Bitovi; leading Bitovi’s AI enablement practice) argues that AI's most transformative impact on software development is not making engineers faster in isolation — it's collapsing the weeks-long design→dev→test cycle by enabling product owners and designers to build and validate prototypes in hours, so that by the time work reaches an engineer, risk has already been smoked out. He describes a team journey with three stages: individual vibe coding (unnamed as a formal phase), **local agent orchestrators**, and **cloud agent orchestrating teams**. Using a task-management feature as a running example, Justin walks through concrete skills, tools, and integrations (Figma, Jira, GitHub, Mock Service Worker, Playwright, Storybook, Claude Code, GitHub Copilot) that support each stage. The central lesson is that the team that invests in reusable agent skills and context management infrastructure eventually earns the ability to assign a Jira ticket to an AI agent and have it implemented end-to-end in the cloud.

---

### B) Key points and tools

- **Three-stage AI team journey** (phases 2–3 are named aloud; phase 1 is descriptive):
  1. **Individual vibe coding** — a PO/designer clones a repo, uses **Claude Code** `[ASR: "cloud code"]`, vibe-codes a prototype, pushes to GitHub
  2. **Local agent orchestrators** — whole team has agent skills; workflows move between GitHub, Jira, Figma
  3. **Cloud agent orchestrating teams** — well-worn local workflows are promoted to cloud automation; humans review results and decide next steps
- **Four needs for successful vibe coding:** (1) agent can build what you want → Mock Service Worker; (2) consistency → skills; (3) visual communication → Convey / Figma Make Local; (4) easy sharing → branch/PR builds
- **Mock Service Worker** — mocking layer that lets an agent focus purely on front-end UI without needing to understand backend/service architecture
- **Three core agent skills:** brand skill (colors, padding, spacing), component skill (reuse existing components, don't rebuild), data model skill (keep data model consistent across the prototype)
- **Convey** — open source visual drag-and-drop tool the speaker built; similar purpose to Figma Make Local (released after his slides/tool were prepared)
- **Branch builds / PR builds / shareable cloud preview** — spin up a live environment per branch; enables vibe-coded prototypes to be shared with stakeholders for feedback with one click (`[ASR: "code space"]`)
- **React-to-Figma skill** — custom skill that uses Figma's MCP `use_figma` tool plus Storybook visual diffing to reconstruct a running React app in Figma with high accuracy
- **Figma MCP `get_design_context`** — tool that gives an agent a structured representation of Figma component styles and HTML for implementation
- **Figma Code Connect** — maps Figma components to their actual React/Angular code; speaker says it "might triple the likelihood you'll one-shot a Figma design"
- **Storybook + Playwright** — used for visual validation of component consistency during the Figma build step
- **Jira + GitHub Copilot automation** — skill that reads a Jira ticket + linked Figma files and writes a full user story; triggered by posting a GitHub issue assigned to Copilot
- **Cloud caveat:** technical limitations still prevent a cloud agent from *building a design in Figma*; other cloud automations (review/story/implementation) are shown
- **Bitovi AI agent** — assigned to Jira tickets put In Progress to handle full implementation; pushes a branch and launches a shareable cloud preview for review
- Context placement principle: "Where do you put your context?" — deliberately choosing Figma (not Jira) as the source of truth for design QA questions and answers
- **Open source:** demo app, skills, and techniques are available OSS; QR at end for MCP / AWS / Jira setup docs

---

### C) Verified takeaways (with quotes)

**1. The biggest process win is risk reduction before work reaches engineers — not engineering speed alone.**
> "By the time it gets to me, I only have to build it once."

Any design→review→dev handoff that validates late carries rework risk. The pattern here — prototype early, validate with stakeholders before writing production code — is directly applicable to the team's internal web app work and worth advocating for as a team norm.

**2. A mocking layer lets agents (and engineers) focus on one layer at a time.**
> "This allows the agent to just focus on building the front end."

`[ANALOGOUS]` For backend work: when building a new Spring Boot microservice or Kafka consumer, mocking upstream and downstream dependencies (using WireMock, Testcontainers stubs, or an in-memory broker) lets the agent (or engineer) focus on the service logic without navigating the full microservice ecosystem. The same principle applies.

**3. Three core skills prevent the most common agent consistency failures.**
> "A brand skill… a component skill… a data model skill." `[paraphrase of three skills named separately]`

`[ANALOGOUS]` For the team's backend and full-stack work, the equivalent trio would be: a **service template skill** (Spring Boot conventions, package structure, error handling patterns), a **schema/contract skill** (keep API request/response models and Kafka message schemas consistent), and an **integration pattern skill** (how this team connects to upstream/downstream systems). These would prevent agents from inventing new patterns that break consistency.

**4. Deliberate context placement is a design decision for agentic workflows.**
> "You really want to take care of where people are putting information so that your agents can go get it."

When the team uses AI in its workflow, the question of *where* context lives matters enormously — is it in Jira ticket descriptions? Confluence? Code comments? OpenAPI specs? The team should make this an explicit choice rather than letting it be accidental.

**5. Cloud agent orchestration is the logical destination of maturing local skills.**
> "Why do I have to run this on my local computer… Can I just… click a button and move this to the cloud?"

Assigning a Jira ticket to an AI agent for end-to-end implementation is not science fiction — it's the third stage of a journey that starts with individual vibe coding. The team's current AI practices (wherever they fall) can be mapped to this model to understand what to invest in next.

---

### D) Role and team actions (including AI enhancements)

1. **Assess where the team currently sits in the three-phase maturity model.** Are individuals vibe coding independently (phase 1)? Are shared skills and agent practices being developed across the team (phase 2)? Is any of that being promoted to cloud automation (phase 3)? Use this as a conversation starter for the team's AI strategy.

2. **Define the team's three core agent skills for backend/full-stack work.** Modeled on Justin's brand/component/data model trio: service template skill (Spring Boot conventions), API/schema contract skill, and integration pattern skill. These prevent agents from drifting from team standards. `[INFERRED]`

3. **Adopt explicit context placement as a team norm.** Decide: for AI-assisted development, where is the canonical context? OpenAPI specs, Jira acceptance criteria, Confluence architecture docs, or `agents.md` files in repos? Make the choice intentional and consistent so agents can reliably find what they need.

4. **Verify whether the team has branch builds / PR preview environments.** If not, GitHub Codespaces + a properly configured app is a low-infrastructure path to shareable branch previews for stakeholder feedback — directly applicable to internal web apps. `[INFERRED]`

5. **Explore Jira → GitHub Copilot story writing automation.** The pattern of linking a Jira ticket to design artifacts and having an agent draft the full user story is immediately applicable to the team's sprint workflow, replacing a manual, often-skipped step. `[INFERRED]`

---

### E) Not applicable / unclear items

### Watch the recording (visuals / demos missing from transcript)

| Timestamp | What’s missing | Why it matters |
| --- | --- | --- |
| `00:06:28`–`00:07:27` | Convey / visual drag-drop edit | Shows the non-technical communication path |
| `00:07:49`–`00:08:43` | GitHub shareable preview / “code space” | Sharing vibe-coded work with one click |
| `00:09:59`–`00:11:50` | React→Figma + Storybook visual diff | Accuracy of the rebuild path |
| `00:12:16`–`00:13:41` | Design-review questions posted in Figma | Context-placement demo |
| `00:16:10`–`00:18:20` | Cloud Copilot automation + Bitovi AI agent | End-to-end cloud orchestration |

### Other notes

- Figma-specific tooling (React-to-Figma skill, Code Connect, Figma MCP) — applicable only to the team's full-stack/frontend work, not backend services
- Convey — not applicable unless the team has non-technical contributors making UI changes
- Bitovi AI agent — Bitovi-specific agent shown in the demo; concept transfers, implementation does not

---

### F) Key terms reference

| Term | Definition |
| --- | --- |
| Vibe coding | Informal term for using an AI agent to rapidly prototype or build features without following a formal specification process |
| Local agent orchestrators | Teams where every member uses agents and has developed shared skills for moving work between tools (GitHub, Jira, Figma) |
| Cloud agent orchestrating teams | Teams that have promoted their local agent workflows to cloud automation; humans click a button and review results |
| Mock Service Worker (MSW) | Mocking layer the speaker uses so the agent can focus on front-end UI without building backend/service plumbing |
| Branch build / PR build | A CI/CD feature that spins up a live environment for every branch or PR so work can be shared and reviewed before merging |
| Code Connect | A Figma feature that maps a Figma component to its corresponding code implementation, enabling agents to one-shot accurate implementations |
| Agent skill | A file that tells an agent how to behave in a specific circumstance; reusable across sessions and shareable across a team |
| Context placement | The deliberate decision of where in the toolchain (Jira, Figma, GitHub, code files) to store information that agents will need to retrieve |
