# Designing in code

**Speakers:** Iris (designer), Nico (Figma), Ben (engineering manager), L (product manager) — all Figma
**Source:** `talks/figma-deep-dives/designing-in-code/transcript.md`

---

## A) Summary

This Figma Deep Dive argues that AI coding tools have given designers unprecedented speed to generate concepts, but speed alone creates new problems: vibe-coded solutions look polished yet may not match intent, work happens in isolation (causing divergence from the design system), and artifacts fragment across tools, breaking collaboration. The speakers' core claim is that bringing code *into the Figma canvas* — as "code layers" — plus turning Make into a production code editor restores the explorative, collaborative, system-aligned design process while preserving AI speed. They demo two modes: (1) lightweight "prototyping playground" code layers for fast, side-by-side, branchable exploration that anyone can prompt, and (2) working directly on cloned production code in Make with annotations, git branching, auto-commit, design-system variable detection, and PR creation. The stated value is letting designers explore many divergent ideas at once, keep design and code in sync, collaborate in the open instead of waiting on pull requests, and ship changes to production from within Figma.

---

## B) Key points and tools

- **Code layers**: code brought directly onto the Figma canvas; described as "windows into your repository" that multiple people can open from different places. Run interactively side by side without spinning up a dev box, git, or a terminal.
- **GitHub import / clone repository**: clone a connected repo straight into the canvas; an agent clones and makes it work.
- **Design-to-code via agent**: select design layers and "build this with code" — the agent analyzes the design and generates an interactive code layer.
- **Multi-layer agent operations**: one prompt can create multiple variations (e.g., "create three variations… expressive, animated, basic"), duplicating code layers as separate branches and sending individual prompts to each; one agent can also operate on multiple code layers at once.
- **Screen extraction**: deterministically click through a prototype to extract all screens into a static spec on the canvas — "no AI here. It's deterministic, free, and fast."
- **Prototyping playground vs. production**: playgrounds use real front-end components but no backend/deployment baggage, so LLMs run faster and cheaper. Use prototyping code for exploration; production code for implementation/shipping.
- **Make as a production code editor**: clone the repo locally via connected GitHub; build directly on production code so output reflects codebase patterns and changes feel safe (local).
- **Annotation tool**: visually point at an element and leave a comment for the agent instead of long, precise prompts; a shimmer effect shows the agent is working on the right element; a "ding" signals completion.
- **Git workflows made approachable**: branching (like Figma branching), checking out others' branches via link or dropdown, and **auto-commit after each prompt** (like Figma autosave) with revertible version history.
- **Figma MCP server built into Make**: works without manual setup; includes code-to-design tools and design-system sync tools.
- **Design panel in Make**: drag/drop and direct manipulation of agent-generated UI; "generate properties" detects component properties; detects **variables (color, spacing, text styles) from your codebase** so you can edit without prompting.
- **Design-system sync**: prompt the agent to update a Figma design-library component to reflect code changes, so teammates benefit in their design files.
- **Copy designs / copy to canvas**: send design layers from Make back to the canvas to explore, detect changes made there, and push them back to Make.
- **Create PR**: generate a pull request to the repo for engineers to review and ship.

---

## C) Verified takeaways (with quotes)

**1. Separate "exploration" tooling from "production" tooling — the same lesson applies to backend prototyping.**

The talk's strongest transferable idea: a prototyping playground keeps real front-end components but strips backend/deployment concerns so iteration (and the LLM) is faster and cheaper. The analogous move for our team is maintaining lightweight scaffolds/sandboxes (e.g., a stubbed service or local harness with realistic data but no full infra) for fast iteration, distinct from production code paths.

> "You want the screens, you want components, you want realistic looking data, but you don't actually need a back end… LMS can work so much faster on these code bases, saving you both time and tokens."

**2. Branch-per-experiment with auto-commit lowers the risk of AI-assisted change.**

Branching to protect main and auto-committing each agent change maps directly to how our team should structure AI-assisted work: isolate experiments on branches, keep every step revertible, and review before merge.

> "create a branch… so that my work is completely protected and I'm able to idate without being worried about being that one product manager who brought down prod."

**3. Annotation/visual pointing as a prompting method reduces ambiguity — analogous to precise, scoped instructions for coding agents.**

Pointing at the exact target beats long natural-language prompts. For engineers, the analogue is giving coding agents tightly scoped context (specific files, line ranges, failing test) rather than verbose descriptions.

> "No more really annoying long prompts where I have to write make a change in the top right on that image that looks like this and make sure you get it right and don't change anything else."

**4. A machine-generated map of "where does X appear" gives confidence that a change covers all surfaces.**

L used an MCP tool to generate a FigJam diagram of every page/surface where a sponsorship could appear. The backend analogue: tooling that maps all call sites / consumers / topics affected by a change so nothing is missed.

> "with this diagram, I can quickly understand all the surfaces where this badge needs to show up and it's visibility into production code that I never had before."

**5. Keeping the source of truth (design system) in sync with code is an explicit, prompt-driven step — not automatic.**

The team treats "design system diverged from code" as a known failure mode and provides an explicit sync action. The analogue for us is keeping schemas, API specs, and shared contracts in sync with implementation as a deliberate step.

> "my design system component in my design library file hasn't been updated. Well, all I have to do… is prompt the agent."

**6. The MCP server is built in and "just works" — lowering setup friction drives adoption.**

> "the Figma MCP server is built directly into make, which means you don't have to set it up manually. It'll just work."

---

## D) Role and team actions (including AI enhancements)

- **[INFERRED] Stand up a "prototyping playground" pattern for our services.** Maintain a lightweight harness (stubbed dependencies, realistic seed data, no full infra) so we and AI agents can iterate on features/UI for internal apps faster and cheaper, separate from production code.
- **[INFERRED] Adopt branch-per-AI-experiment with frequent commits.** Standardize on isolating AI-assisted changes to branches with small, revertible commits and PR review before merge — mirroring the auto-commit + branch + create-PR loop shown.
- **[INFERRED] Give coding agents scoped, "annotation-style" context.** Prefer pointing agents at specific files/lines/failing tests over long prose prompts to reduce unintended changes.
- **[INFERRED] Build "surface maps" for risky changes.** Use tooling (or an MCP/diagram step) to enumerate all consumers, call sites, Kafka topics, and downstream integrations affected by a change before implementing, so coverage is complete.
- **[INFERRED] Treat contract/schema sync as an explicit step.** When AI-assisted code changes a shared contract (REST spec, Kafka schema, shared library), add a deliberate step to update the source-of-truth artifact so the rest of the team benefits.
- **[INFERRED] Lower MCP setup friction for the team.** Where we expose internal context to AI tools, favor built-in / zero-config integration to drive adoption, as the built-in Figma MCP demonstrates.

---

## E) Not applicable / unclear items

- The demos are heavily visual (canvas manipulation, drag-and-drop, animations, shimmer/confetti effects, color changes). Many specifics are onscreen actions not fully captured in text and are marked here as `[UNCLEAR IN TRANSCRIPT]` (e.g., the exact behavior of code-layer variations around 00:12:18 and the design-panel variable editing around 00:35:02).
- Figma-specific UI features (code layers UI, Make design panel, "generate properties," copy designs) are design-tool features; only their underlying patterns (above) transfer to backend/full-stack engineering work.
- The "designing with code" canvas experience as a literal product does not apply to our Java/Kafka backend services; relevance is by analogy only.

---

## F) Key terms reference

| Term | Definition |
| --- | --- |
| Code layers | Code brought directly onto the Figma canvas as interactive "windows into a repository," runnable side by side without a dev box, git, or terminal |
| Prototyping playground | A code environment using real front-end components but stripped of backend/deployment concerns, so iteration and LLMs run faster and cheaper |
| Make (production code editor) | Figma's Make tool used to clone and edit a real production codebase locally, with git workflows, design-system detection, and PR creation |
| Annotation tool | A visual prompting method: point at an element and comment, instead of writing long precise prompts, with a shimmer indicating the agent is acting on the right target |
| Auto-commit | Make automatically commits changes after each prompt (like Figma autosave), giving revertible version history |
| Figma MCP server (in Make) | A built-in, zero-setup Model Context Protocol server providing code-to-design and design-system-sync tools to the agent |
| Generate properties | A Make feature that detects a component's properties (and codebase variables: color, spacing, text styles) so they can be edited directly without prompting |
| Copy designs | A Make action that sends design layers back to the Figma canvas for exploration, with changes detectable and pushable back into Make |
