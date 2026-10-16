# Figma deep dive: Agents

**Speakers:** Tammy (product designer), Rodrigo (product manager) — both Figma
**Source:** `talks/figma-deep-dives/figma-deep-dive-agents/transcript.md`

---

## A) Summary

Tammy and Rodrigo demo the Figma agent (launched ~a month prior) and a set of new extensions that let teams shape it to how they work: web search, local file attachments, MCP connectors (read and write back), custom skills, shareable chats, and on-canvas actions like creating variations. Their framing problem: an open prompt box implies the AI can do anything, but designers each love and hate different parts of the work, so a good AI collaborator must support a huge range of use cases and adapt to a messy, non-linear, multiplayer process — rather than forcing everyone toward a single high-fidelity output in a silo. The core claim is that AI should "do the laundry and dishes" (the tedious work) so people can focus on what they care about, while keeping the human in the driver's seat. The demo shows parallel prompting (kick off multiple agent tasks and keep working live), generating designs from a Notion spec and a connected design system, reconnecting stray styles to the design system, generating a page from a CSV, constrained variations, agent-driven animation/code-layer edits, and reusable/composable skills (e.g., a "Tammy feedback" review skill and a "spec up" skill that calls a foundational "create documentation" skill) shareable across an org.

---

## B) Key points and tools

- **Figma agent**: an on-canvas AI collaborator that "knows your canvas, knows your context, knows Figma," available via a left-rail tab and an on-canvas entry point on selections. Now in beta on pro/org/enterprise plans; coming to FigJam and Slides soon.
- **Web search**: agent can do product/design research and pull real-world examples/content directly into designs without leaving the canvas.
- **Attachments**: drop in local files (spreadsheets, docs, CSVs) for the agent to build from.
- **MCP connectors**: pull content from external tools (documents, data, code) and **write back** to them — e.g., generate designs from a brief, then update the PRD with references. Expanded connector set includes Hex, Slack, Granola, Asana, GitHub, Notion; connectors published in Make are available here too.
- **Custom skills**: steer agent behavior with your conventions/preferences; **skills are just markdown files** you can copy-paste in. Portable from other agents "in seconds," shareable with the team to scale expertise across an org.
- **Composable skills**: skills can call other skills and leverage connectors (e.g., "spec up" → "create documentation"). Foundational skills are built once and reused without repetition.
- **Shareable chats**: see how teammates work, learn/share best practices; chats can be made private with one click.
- **On-canvas common actions**: e.g., **create variations** with constraints (e.g., "only layout changes, don't touch style/fonts") to explore ideas safely.
- **Parallel prompting**: start multiple agent tasks, move elsewhere, and keep making manual tweaks live while they run; track running work in the left panel.
- **Design-system integration**: agent uses connected libraries (`@`-mention design systems), pulls in real components, and can reconnect stray colors/typography to the closest matching design-system tokens. Output is "design layers all the way down," directly editable.
- **Agent-driven motion & code layers**: agent can tweak animations (swing/rotate) and operate on interactive code-layer objects (make vertical, make a grid, make the title bigger, add bounce).
- **Feedback loop**: leave comments on a design and have the agent address them; a review skill can annotate designs (typography, hierarchy, accessibility).
- **Deep links**: agent output links jump to exact frames/nodes.
- **Design philosophy**: support both deep/solo and wide/collaborative work ("go deep" vs "go wide"), embed into the messy middle, keep humans in the driver's seat — "the goal isn't just generating a bunch of options, it's getting to that outcome that you're looking for."

---

## C) Verified takeaways (with quotes)

**1. Skills are just markdown — codifying your own best practices is low-barrier and scales expertise across a team.**

The most transferable idea: a "skill" is a plain markdown file of your best practices that any teammate (or agent) can reuse. For our team this maps directly to capturing review standards, service conventions, and runbooks as agent-consumable markdown skills.

> "skills are just markdown files. You can copy paste them in… You do not need to think of yourself as an AI expert in any way to write one. It's just taking your best practices from your head and giving those as instructions."

**2. Composable skills + a foundational base skill let large orgs scale without repetition.**

"spec up" builds on a complex "create documentation" foundational skill. The backend analogue: layer task-specific agent skills on top of shared foundational ones (coding standards, logging/observability conventions) so teams build on a common base.

> "this create documentation skill is like a foundational skill… folks can just build on top of it without you having to repeat all of that. And that's really helpful if you're in like a larger org and you're trying to scale your expertise through skills."

**3. Connectors that read AND write back close the loop between source-of-truth docs and generated artifacts.**

Generating from a Notion/PRD spec and writing changes back (with references) is directly analogous to keeping tickets, design docs, or API specs in sync with implementation via tool connectors.

> "you can take that brief, generate designs in Figma, and then write back your changes to the PRD with a bunch of references to all the designs that you just made."

**4. Parallel prompting + a running-task panel enables fire-and-continue multitasking.**

Kicking off multiple agent tasks and continuing to work while tracking them maps to how our team can run multiple AI coding tasks/agents concurrently and monitor them.

> "what we're calling parallel prompting, being able to stop, go somewhere else, do lots of different things at once."

**5. Constrain the agent's scope to get safer, more useful output.**

Limiting variations to "layout only, don't touch style/fonts" is a precise-scoping technique. For coding agents, constraining changes to specific files/concerns reduces collateral damage.

> "I can actually constrain what the agent can do quite a bit. So, I don't want to mess with style or fonts. I just want to try some layout changes."

**6. AI should take the tedious work so humans focus on judgment — and humans stay in the driver's seat.**

The "laundry and dishes" framing plus "in the driver's seat" is a healthy default for adopting AI: automate toil, keep human ownership of outcomes.

> "We want the AI to do laundry and dishes so that we can do art and writing."

**7. Encode reusable reviewers as skills (the "Tammy feedback" pattern).**

A skill that applies a specific person's/team's review heuristics and annotates the work is directly portable to engineering: a "team code review" skill encoding our standards.

> "I could use a skill that Tammy hopefully created for me… which will actually review my designs and give me some of the greatest hits of Tammy feedback."

---

## D) Role and team actions (including AI enhancements)

- **[INFERRED] Capture team best practices as markdown skills.** Convert our code-review standards, Spring Boot/Kafka conventions, and integration runbooks into plain-markdown agent skills that anyone can reuse and that work across multiple AI tools.
- **[INFERRED] Build a foundational + composable skill hierarchy.** Create a base "engineering standards / documentation" skill and layer task-specific skills (e.g., "write a Kafka consumer," "scaffold a REST endpoint," "write an ADR") on top, so the team scales expertise without duplication.
- **[INFERRED] Use connectors that write back to keep docs in sync.** Where AI generates or changes code, have it update the linked source of truth (Jira/Confluence/PRD/API spec) with references, closing the loop between spec and implementation.
- **[INFERRED] Adopt parallel-prompting / multi-agent multitasking.** Run multiple AI coding tasks concurrently and track them, rather than serializing AI work.
- **[INFERRED] Constrain agent scope explicitly.** When using coding agents, restrict changes to specific files/concerns (analogous to "layout only") to avoid unintended modifications.
- **[INFERRED] Create a reusable "team review" skill.** Encode our review heuristics (correctness, error handling, observability, edge cases) into a skill that reviews and annotates AI-generated or human PRs before a human reviewer engages.
- **[INFERRED] Use shareable chats to spread AI best practices.** Share effective agent conversations so teammates learn prompting/workflow patterns.

---

## E) Not applicable / unclear items

- The talk is design-canvas-specific (Figma design generation, motion, code layers, design-system component swapping, annotations). Concrete features apply to backend Java/Kafka/REST work only by analogy; the strongly transferable parts are skills, connectors, parallel prompting, scoping, and the human-in-the-driver's-seat philosophy.
- Many moments are heavily visual and several demo tasks were "still going" or pre-baked ("I have another example where it worked"), so some outcomes are onscreen/edited rather than fully described `[UNCLEAR IN TRANSCRIPT]` (e.g., motion compass result ~00:22:21, variations fixes ~00:22:00).
- Figma-specific products (design agent, Make connectors, code layers, on-canvas entry points, libraries/Octo design system) are platform features with no direct backend equivalent.
- The exact set/behavior of available connectors and the design-system reconnection logic are demoed but not specified in detail `[UNCLEAR IN TRANSCRIPT]`.

---

## F) Key terms reference

| Term | Definition |
| --- | --- |
| Figma agent | An on-canvas AI collaborator aware of the canvas, context, and Figma, accessed via a left-rail tab or on-canvas entry point |
| MCP connectors | Integrations that let the agent pull content from external tools (docs, data, code) and write changes back to them |
| Custom skills | Plain markdown files encoding conventions/best practices that steer agent behavior; portable and shareable across a team/org |
| Composable skills | Skills that can call other skills and use connectors, enabling foundational skills to be reused by more specific ones |
| Parallel prompting | Starting multiple agent tasks at once and continuing other work (manual or agent) while they run |
| Create variations | An on-canvas action that generates multiple options, optionally constrained (e.g., layout only, no style/font changes) |
| Code layers | Interactive, code-backed objects on the canvas that the agent can also manipulate (e.g., make vertical, make a grid) |
| Shareable chats | Agent conversations that can be shared so teammates learn each other's workflows, or kept private with one click |
| Deep links | Links in agent output that jump directly to the exact frames/nodes referenced |
