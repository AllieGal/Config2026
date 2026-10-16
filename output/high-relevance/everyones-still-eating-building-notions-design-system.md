# Everyone's still eating: building Notion's design system

**Source:** `talks/everyones-still-eating-building-notions-design-system/transcript.md`
**Session:** [View session](https://config.figma.com/san-francisco/session/9bbf68e9-0644-48df-9b6c-f4ad1827a146/)
**Speakers:** Tamara Chu, Design Engineer, Notion; Shauna Sapper, Software Engineer, Notion (design system team established July 2025)

> **Transcript completeness:** Spoken argument is largely complete (meatball → foundations → AI migration → enforcement spectrum → “make the right way the easy way”). **Watch the recording** for almost all visuals — before/after UI bugs, the meatball graph, color/icon diffs, Meticulous before/after/diff, the front-end commit chart, and the enforcement-spectrum slide. Those screens are referenced as “this / that” in the transcript and are not recoverable from text alone.

---

## A) Summary

Tamara Chu and Shauna Sapper describe the year-long journey of building Notion's first formal design system — after CEO Ivan had publicly said Notion didn't have one — starting from a tangled, undifferentiated codebase they call "the meatball," while migrating the live product without stopping development. They liken it to "whipping off a tablecloth at a dinner party while everyone is still eating and putting a new tablecloth on at the same time." Foundations (color, type, icons — including Paul Verlu's hand-drawn icon set) moved into code via sync scripts; mechanical migrations used Claude Code + Notion MCP + Meticulous visual regression, while humans kept nuanced visual/judgment work. The talk's most transferable insight is enforcement: a spectrum from "easily ignorable" (docs, announcements, agent instruction files) to "completely unavoidable" (ratcheting + PR-blocking bot Doug), because agents take the path of least resistance — so make the right way the easy way.

---

## B) Key points and tools

- **The meatball**: Notion's term for their legacy codebase — a single, undifferentiated dependency graph with no isolated home for shared components, no CSS (inline JavaScript style objects everywhere), and duplicate components with no clear ownership
- **`use styles`**: Notion's legacy styling approach — plain JavaScript objects set as inline styles everywhere; no CSS, no pseudo-classes
- **Design system as "a set of shared decisions"**: the team's framing — not a component library or commandments, but accumulated, agreed-upon decisions about how a product expresses its identity
- **Color system migration**: moved from multiple cohabitating color systems (hard-coded → light/dark mode values → early semantic tokens → new semantic tokens) to a unified OKLCH-based token system with CSS variables; migrated over a 56-part run
- **Custom sync scripts**: scripts that sync Figma token definitions into code; automate SVG optimization, RGBA→OKLCH conversion, text→rem transformation
- **Paul's icon factory**: a single Figma file in which one person (Paul Verlu) drew thousands of standardized icons by hand
- **Claude Code + Notion MCP**: used together to introspect the codebase, create deprecation trackers in Notion, provide metadata on migration targets (e.g. 529 single-use icons), and generate PRs for mechanical icon replacements
- **Meticulous**: a visual regression testing tool that runs silently in developers' local environments, records clicks/scrolls/user activity, and replays that activity against code changes — alerting on PR diffs of any visual regression; used to automate verification of AI-generated migration PRs (not sponsored; speakers emphasize they just like the tool)
- **Migration pipeline**: Claude auto-creates PRs for icon replacements → Meticulous checks each PR for visual regressions → team reviews diffs → informed decision on manual verification
- **Agents struggle where judgment ≠ matching numbers**: color perception matching and icon view-box drawing intent; those stay human
- **Ratcheting**: a "mega linting" technique where all usages of a deprecated pattern are tracked in a file, and that number can only decrease over time — any increase triggers loud warnings and PR-blocking via a bot named Doug (system existed before the design system team; reused for migration)
- **Doug**: their PR-blocking bot (named after computing pioneer Doug Engelbart) enforcing the ratchet
- **Enforcement spectrum**: easily ignorable (docs, JSDoc, announcement posts, agent instruction files / skills) → middle (deprecate tags, lint warnings with yellow squiggles) → completely unavoidable (end-to-end tests, unit tests, ratcheting / PR blockers)
- **Front-end commit growth**: sharply increasing since 2022, exponentially in the past year with AI agents; design system eng headcount is a tiny blue line (speakers + Irat, formerly part-time)
- **Key lesson on AI**: agents take the path of least resistance — when Notion linted against style props, an agent worked around it using a ref; "Our job is to make sure that path is the right one" / "make the right way the easy way"
- **Closing philosophy**: a design system is shared decisions expressing the company's "heart and soul," not putting everything in the system; Christopher Alexander / *How Buildings Learn* quote on continuous adaptation; Slack lore of a 70-message debate ending in 1.5px checkbox border-radius

---

## C) Verified takeaways (with quotes)

**1. Ratcheting is a powerful enforcement pattern for large-scale codebase migrations — applicable directly to our Java/Spring Boot services.**

Ratcheting (tracking all violations of a deprecated pattern in a file, allowing only the number to decrease, blocking PRs if it goes up) is applicable to our team's deprecation of legacy patterns in shared libraries, deprecated API endpoints, or outdated configuration patterns in Spring Boot. Our team could apply this via Checkstyle, SpotBugs, or custom Gradle/Maven enforcement.

> "If there's a pattern we want to deprecate, we can add it to a file where all usages of the pattern are tracked and that number can only go down like a ratchet strap. If the number of lint errors goes up, you get loud warnings and you can even block PRs from merging."

**2. AI agents will take the path of least resistance — make the right path easy, not just the wrong path hard.**

This is a direct warning for any team using AI-assisted code generation. Agents will bypass lint warnings, work around soft guidelines, and find indirect ways to accomplish their goal. The only reliable enforcement is hard, unavoidable constraints (CI checks, PR blockers, type errors). Soft guidance — comments, documentation, announcements — is insufficient for AI agents.

> "You have to assume that it's going to try to do anything it can to get around the rules that you've set... Our job is to make sure that that path is the right one. Basically: make the right way the easy way."

**3. Break down migration work into explicit steps; AI can own mechanical steps, humans must own nuanced ones.**

The team found AI struggled with work that seemed like "just matching numbers" but was actually about subtle visual and semantic judgment (color perception, icon drawing intent). The lesson for our team: be explicit about which migration steps are mechanical (safe for AI delegation) vs. which require human judgment (schema semantics, API behavior preservation).

> "A lot of the work is actually a long chain of small steps that is implicit — not just how the work gets done, but which work should get done and in what order and at what level of risk. If you make that thinking explicit... you get to decide if AI takes it on, your teammate takes it on, or if you believe it's important enough for you to invest your own blood and sweat in."

**4. An AI + automated testing pipeline (generate PR → visual/functional regression check → review diff) is a practical, repeatable pattern.**

The Notion pipeline (Claude creates PR → Meticulous checks for regressions → team reviews diffs → informed merge decision) is a directly adoptable pattern for our team's refactoring or migration work. The equivalent in our stack would be: AI generates a refactor PR → existing unit/integration tests run → diff is reviewed by a human before merge.

> "We can create a pipeline where Claude auto creates a PR for all of these rows, and we wait for Meticulous to check each of them. We can review the diffs, approve differences, and then make informed decisions about whether we actually need to manually verify ourselves."

**5. Coding agents don't read Slack — enforcement must live in the toolchain, not in documentation.**

> "This coding agent doesn't read Slack, maybe, or knows that your editor is showing a little yellow squiggle under the prop. You have to assume that it's going to try to do anything it can to get around the rules that you've set. Leaning into the far end of the spectrum — that unavoidable end — gets more and more important."

---

## D) Role and team actions (including AI enhancements)

- **Implement ratcheting for deprecated patterns in shared services**: Identify high-priority deprecated patterns in our codebase (e.g., legacy API clients, deprecated Spring Boot configurations, old Kafka producer/consumer patterns) and implement ratchet-style enforcement via Checkstyle or a custom CI check — allowing the count to only go down over time, blocking PRs that increase it.
- **[INFERRED] Classify migration work by AI-ownership readiness**: For any large-scale refactoring (e.g., moving to a new shared library, migrating Kafka schema formats, updating Spring Boot versions), explicitly categorize each task: mechanical (AI can own), nuanced (AI assists, human verifies), or high-risk (human owns, AI may draft). Document this classification before starting.
- **[INFERRED] Build an AI-assisted migration pipeline with hard regression gates**: Adopt the Notion pattern — AI generates PR → automated tests (unit, integration, contract) validate → human reviews diff — as a standard workflow for AI-assisted refactoring. Ensure the automated gate is non-bypassable (CI must pass before merge is allowed).
- **[INFERRED] Audit our enforcement spectrum**: Evaluate the current state of shared coding standards enforcement on the team. Map what currently lives in docs/wikis (easily ignorable), what shows as lint warnings (middle), and what hard-blocks PRs (unavoidable). Identify gaps and move high-priority patterns toward unavoidable enforcement — especially given increasing AI-generated code volume.
- **[INFERRED] Use an MCP or codebase introspection tool to generate migration metadata**: Following the Notion MCP + Claude pattern, explore using AI to introspect our codebase and generate migration tracking documents (e.g., "which services still use the deprecated config pattern, ranked by risk and usage frequency").

---

## E) Not applicable / unclear items

### Watch the recording (visuals / demos missing from transcript)

| Timestamp | What’s missing | Why it matters |
| --- | --- | --- |
| `00:01:40`–`00:02:29` | “Pixel perfect becomes this / and this” — broken UI examples (tooltip, cut-off focus ring, confusing props) | Concrete proof of the “no design system” problem |
| `00:02:29`–`00:03:19` | “Meatball” codebase dependency visualization | Core metaphor; graph is on screen only |
| `00:05:07`–`00:06:10` | Color-system mishaps (layered pinks, cohabitating token generations) | Hard to judge severity from narration alone |
| `00:07:07`–`00:07:52` | Paul’s icon factory / icon set visuals | Quality of the icon system is visual |
| `00:09:34`–`00:09:55` | Side-by-side color matching + icon view-box “this vs this” | Why agents failed “delicate” work |
| `00:10:56`–`00:11:18` | Meticulous before / after / diff screenshots + migration table rows | How the AI→PR→diff pipeline actually looks |
| `00:13:11`–`00:13:36` | Front-end commit growth chart vs tiny design-system eng line | Scale argument is chart-dependent |
| `00:14:24`–`00:15:38` | Enforcement spectrum slide (ignorable → unavoidable) | Structure is clear in speech; examples on slide help |
| `00:16:57`–`00:17:19` | Agent bypassing style-prop lint via a `ref` | “Earned our respect” demo — code not shown in text |

### Other notes

- Icon standardization, color system design, and Figma-to-code sync scripts are design-system-specific.
- The visual regression specifics of Meticulous are frontend-specific; our equivalent would be integration/contract tests — pipeline pattern still applies.
- The "use styles" (JavaScript inline styles) legacy and CSS variables migration are frontend-specific.
- The specific token format (OKLCH) is a CSS/design concern.
- Closing Christopher Alexander quote and 1.5px checkbox Slack lore are fully in the transcript (no video required for those beats).

---

## F) Key terms reference

| Term | Definition |
| --- | --- |
| The meatball | Notion's informal term for their legacy codebase — a tangled, undifferentiated dependency graph where everything depends on everything else and there is no isolated home for shared components |
| Ratcheting | An enforcement technique where all usages of a deprecated pattern are tracked in a file; the count can only decrease over time, and any increase blocks PRs — described as "mega linting" |
| Meticulous | A visual regression testing tool that silently records user activity in developers' local environments and replays it against code changes, alerting teams to any visual regressions on PRs |
| Claude Code | Anthropic's coding agent (Claude) used in agentic mode to write code, create PRs, and execute migration tasks; used here alongside Notion MCP for codebase introspection |
| Notion MCP | A Model Context Protocol integration giving Claude access to Notion's codebase metadata, allowing it to create deprecation trackers, migration plans, and prioritize work |
| Doug | Notion's PR-blocking bot (named after computing pioneer Doug Engelbart) that enforces ratchet rules and prevents PRs from merging when deprecated pattern usage increases |
| Enforcement spectrum | The range from "easily ignorable" (docs, announcements) to "completely unavoidable" (PR blockers, ratcheting) — the team argues that as AI agents proliferate, investment must shift toward the unavoidable end |
| `use styles` | Notion's legacy styling system — plain JavaScript objects set as inline styles everywhere, with no CSS, no pseudo-classes, and no `hover` states — a significant technical debt they migrated away from |
