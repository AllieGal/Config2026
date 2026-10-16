# Figma deep dive: Agent-built plugins

**Speakers:** Georgia (product team), Avery (software engineer — APIs, plugins, generative plugins), Jason (product designer) — all Figma
**Source:** `talks/figma-deep-dives/figma-deep-dive-agent-built-plugins/transcript.md`

---

## A) Summary

The team introduces "generative plugins" — Figma plugins you build by describing what you want to a design agent, without writing code, opening an editor, or learning a framework. The problem they're solving: designers have clear ideas for small tools that would save them minutes a day, but building plugins has historically required engineers or vibe-coding outside Figma. Their core claim is "if you can describe the tool, you can build the tool," and that many useful tools are lightweight, even disposable ("useful this week, maybe next week, and then maybe never again"). The agent identifies the plugin type, asks clarifying questions about controls/UI up front to get alignment on the first try, and defaults to a new native UI component library called Props Kit so plugins look and feel like Figma. Key value points demonstrated: plugins become part of the file and the layers they create (settings remembered, traveling with the work when copied/duplicated), running a built plugin is free (no recurring token cost), iteration is seamless (edit via agent chat, slash commands, recently-run rail), and plugins can compose with shader fills/effects and pull external context via connectors (e.g., a Notion connector to feed a PRD into the agent).

---

## B) Key points and tools

- **Generative plugins**: plugins built by prompting a design agent. They use the existing plugin API, create artifacts in Figma, and "run like plugins because they are plugins." No coding, editor, or new framework required.
- **Origin / pace**: the project went from idea to Config stage in ~45 days; the team operates "like a mini company within Figma," sharing prototypes in a Slack channel and shipping relentlessly.
- **Agent clarification step**: the agent identifies the plugin type and asks follow-up questions about controls/UI when unclear, ensuring alignment "on the very first try." Shows ETA in chat so you can run it without losing your place.
- **Props Kit**: a new native UI component library for plugins; the agent uses it by default so plugins look professional and Figma-native. Can also bring in custom controls or a different UI on request.
- **Advanced/creative controls**: beyond sliders, number inputs, and dropdowns, you can ask for easing, joysticks, 3D controls, and **on-canvas handles** mapped to properties (e.g., move a gradient, a "chaos" joystick, light position).
- **Plugins attach to file and layers**: a run plugin becomes part of the file and the specific layer it created; settings are remembered for relaunch. The "tool always travels with the work" — duplicate/copy a layer or file and the plugin comes with it. No publishing/installing needed for collaborators in the file.
- **Tools rail / discovery**: left-rail "tools" houses weave tools, shader effects, shader fills, classic plugins, and generative plugins; recently-run tools surface for quick relaunch; filter by source/creator/category.
- **Iteration paths**: edit via the `...` menu (reopens agent chat with plugin context), rename, or invoke via **slash commands** once created.
- **Cost model**: "You create it once, and then it no longer costs you to run it… running plugins is free." Built once, reused indefinitely — explicitly framed against a more cost-conscious, post-"token maxing" era.
- **Composition**: generative plugins compose with shader fills and shader effects (e.g., the "Fig Nail Studio" example pulling shaders onto generated nails).
- **External context via connectors**: a teammate used the **Figma Notion connector** to author a PRD and feed it into the agent to build a complex two-part game terrain builder.
- **Examples shown**: 3D-to-2D perspective tool, Bento grid builder (with reshuffle), live weather data plugin (one-shot, with temperature control + icon), vector blend-path tool (blend between nodes, follow a path), gradient grid generator (on-canvas handles, radial option, chaos joystick), frame-navigation helper, game terrain builder (frame slicer → tile sets → map with elevation levels), nail studio, and a webcam face-outline/keyframe plugin.
- **Roadmap**: Props Kit + on-canvas handles available today for generative plugins and coming to classic plugins; generative plugins will be publishable to community/org soon; first-party plugins browsable today; current sharing is via file invite/copy.

---

## C) Verified takeaways (with quotes)

**1. Disposable, single-purpose internal tooling is now cheap to create — a strong analogy for our team's internal utilities and scripts.**

The central reframe: not every need is a product; sometimes it's a small tool that saves minutes. For our team, this maps to building throwaway internal utilities (data-shaping scripts, one-off admin helpers, debugging aids for Kafka/REST work) via AI rather than treating every tool as a project.

> "Sometimes the thing that you need isn't an entire product… something that saves you 10 minutes every day… useful this week, maybe next week, and then maybe never again. And that's completely okay."

**2. "If you can describe the tool, you can build the tool" lowers the barrier for non-specialists — relevant as our team expands into full-stack delivery.**

The democratization angle (designers building their own tools) parallels enabling our Java-centric team to spin up front-end/internal-app tooling via AI without deep specialization.

> "if you can describe the tool, you can build the tool."

**3. An agent that asks clarifying questions about requirements up front improves first-shot accuracy.**

The agent explicitly asks about controls/UI before generating, to "ensure that you're aligned on what it's creating on the very first try." For our AI-assisted coding workflows, prompting agents to confirm requirements/interfaces before generating reduces rework.

> "If it's unclear… it will ask you follow-up questions to clarify controls or UI components… This ensures that you're aligned on what it's creating on the very first try."

**4. Feeding structured specs (a PRD) and external context via connectors yields far more capable AI output.**

Yuchen's complex terrain builder came from a carefully authored PRD fed in through the Notion connector — contrasted with the one-or-two-sentence prompts used elsewhere. The analogue for us: invest in structured specs/context (design docs, API contracts) when prompting agents for non-trivial builds.

> "Yuchen used the Figma Notion connector to create a PRD, spent a ton of time working on that… and fed that into the agent with the Notion connector to build out this tool."

**5. "Build once, run free" — generative artifacts have one-time creation cost, then zero marginal run cost.**

A useful mental model for AI economics: spend tokens to generate a reusable tool, then run it deterministically for free, rather than paying per invocation.

> "You create it once, and then it no longer costs you to run it… Build it once, and then you can use it time and time again."

**6. Start small and iterate — build incrementally on top of a working base.**

> "start small and then build on top of that… Start small, ask the agent to create something really, really simple."

**7. Use a shared standard UI library so generated artifacts look consistent and native.**

Props Kit as a default component library ensures plugins are consistent without extra effort. The analogue: a shared component library / design system so AI-generated internal apps stay consistent with our standards.

> "we've introduced a new UI library for plugins called Props Kit… you're able to make plugins that look and feel like Figma and super professional at the same time."

---

## D) Role and team actions (including AI enhancements)

- **[INFERRED] Encourage building small, disposable internal tools with AI.** Normalize using AI to create throwaway utilities for recurring annoyances (log/data parsers, Kafka message inspectors, scaffolding helpers) rather than reserving effort only for "products."
- **[INFERRED] Make agents confirm requirements before generating.** Adopt a prompting pattern where the coding agent asks clarifying questions about interfaces, edge cases, and controls before producing code, to improve first-shot accuracy.
- **[INFERRED] Invest in structured specs + context connectors for complex AI builds.** For non-trivial AI-assisted work, author a proper spec (PRD/design doc) and connect relevant context sources (docs, schemas, tickets) instead of relying on short prompts.
- **[INFERRED] Adopt "build once, run free" thinking for AI cost management.** Prefer generating reusable, deterministic tools/scripts over repeatedly invoking paid AI for the same task, aligning with cost-conscious guidance.
- **[INFERRED] Standardize on a shared component library for internal apps.** As the team ships internal web apps, use a shared UI/component library so AI-generated screens stay native and consistent.
- **[INFERRED] Make tools travel with the work / be discoverable.** Favor approaches where utilities are embedded with the artifact or easily discoverable/relaunchable by collaborators (no manual install), analogous to in-repo scripts/tasks with remembered config.

---

## E) Not applicable / unclear items

- The entire talk is design-canvas-specific (shaders, nails, gradients, Bento grids, vector blends, game terrain tiles). These concrete features do not apply to backend Java/Kafka/REST work; relevance is by analogy only.
- Many demos are heavily visual (on-canvas handle manipulation, shader effects, live previews, webcam face-tracking). Specific visual behaviors are onscreen actions not fully captured in text and are treated as `[UNCLEAR IN TRANSCRIPT]` where details matter (e.g., gradient "chaos" joystick behavior ~00:22:35, face keyframing ~00:29:12).
- Figma-specific products — Props Kit, shader fills/effects, the plugin API, generative plugin publishing — are Figma platform features with no direct backend equivalent.
- The one-shot live weather plugin pulling web data is demoed but its implementation details are not described `[UNCLEAR IN TRANSCRIPT — 00:17:23]`.

---

## F) Key terms reference

| Term | Definition |
| --- | --- |
| Generative plugin | A Figma plugin built by describing it to a design agent (no coding/editor/framework); uses the existing plugin API and runs like a normal plugin |
| Props Kit | A new native UI component library for plugins, used by the agent by default so plugins look and feel like Figma |
| On-canvas handles | Interactive controls placed directly on the canvas (mapped to plugin properties) for manipulating output, e.g., moving a gradient or light position |
| Plugin API | Figma's existing programmatic interface that generative plugins use to create and manipulate artifacts in a file |
| Shader fills / shader effects | Generative visual effects that can be composed with plugins (e.g., applying shader styles onto generated shapes) |
| Figma Notion connector | A connector used to pull external context (e.g., a PRD authored in Notion) into the design agent to build more complex plugins |
| Slash commands | A way to run or iterate on a created plugin by typing `/` and selecting it within the agent |
| One-shot plugin | A plugin produced from a single prompt/generation pass, run as-is (e.g., the live weather data plugin) |
