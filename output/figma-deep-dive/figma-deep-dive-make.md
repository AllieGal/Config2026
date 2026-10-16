# Figma deep dive: Make

**Speakers:** Laura (design advocate), Brett (design advocate) — both Figma
**Source:** `talks/figma-deep-dives/figma-deep-dive-make/transcript.md`

---

## A) Summary

Laura and Brett address the most common complaint about Figma Make — "it's not using my design system, so it's not useful" — and argue this is false: Make works well with a design system, it just needs to be told how. The bulk of the talk is a practical method for making AI output stay "on system": package components (ideally as an NPM package, which an LLM can even generate from a Figma library and publish to a private registry), then supply well-structured, machine-readable **guidelines** in markdown, bundle everything into a reusable **make kit**, and provide **templates** as pre-baked starting points. They emphasize that LLMs (like people skimming a long letter) prefer bite-sized, deliberately-referenced context — so guidelines should be split into a high-signal front-door file, a discovery file (where to find things and how to verify, to prevent hallucinated components), and an exact setup file (imports, providers, build config). They demo the full flow on the complex enterprise SAP Fiori (UI5) design system (and contrast with smaller Offtrail), including generating guidelines with an LLM in ~42 minutes, testing the kit with a robust prompt, verifying output with a "compliance check" skill that scores results against a publish threshold, building a template with onboarding overlays and preset/recipe prompt panels, and a governance/rollout model where kit updates propagate to all consuming files.

---

## B) Key points and tools

- **Core claim**: "Make is generally good in designing with your design system. It just needs to know how." Not as simple as handing it your component library.
- **Prototyping code vs. production code**: not all code is the same. Prototyping code optimizes for speed, fast builds, fewer dependencies; production requires stability, integration pipelines, heavier QA. Code is now a fast "material," not just an end state.
- **NPM package**: "a versioned bundle of reusable code you install in your app" so it uses the same buttons/inputs/layouts/patterns. Preferred distribution for a production design system; LLMs can generate a valid NPM package from a Figma library and publish to a **private NPM registry inside Figma**.
- **Library vs. make kit vs. template**:
  - *Library*: the familiar component library.
  - *Make kit*: a code representation of components + usage guidelines packaged so Make produces consistently on-system designs (can use NPM packages, but doesn't have to).
  - *Template*: a common pre-baked starting point for new make files (can use make kits, but doesn't have to), saving time and credits.
- **Markdown everywhere**: simple, lightweight, structured, easy for models to understand — "one of the main languages we use to talk to the machines."
- **Rules/guidelines are the critical missing piece.** Structure guidelines so the model references them deliberately, not by scanning everything each move:
  - *Guidelines file* (capital-G, the default/front door): product character (density, surfaces, elevation, UI feel), sets defaults, defines required reading order of other files. Must be high-signal; cannot be deleted.
  - *Discovery file*: teaches the agent how to navigate — where to find component guidance, source code, stories, docs, icons — and **how/when to verify decisions**, preventing hallucinated components/properties/imports/icons.
  - *Setup file*: exact CSS imports, providers, theme setup, package usage, build configs; if skipped, components render incorrectly or fail at runtime.
- **Generating guidelines with AI**: copy human-readable guidelines into an LLM + attach the recommended structure → machine-readable guideline files (SAP took ~42 min as a *starting point*, then refined with engineers/PMs/design peers).
- **Skills for verification**: skills that evaluate whether generated markdown is true to the injected guidelines, and a "Fiori compliance check" skill that reviews output, checks components/properties, and scores it (e.g., 4.7/5 against a 3.8 publish threshold).
- **Make kit creation flow (demo)**: gear/cog → create a kit → pick direction (Library styles vs. NPM package) → select/search packages (public or private registry) → edits `package.json` dependencies → checklist (install packages, optional custom config) → provide guidelines (generate or bring your own; delete placeholders, keep capital-G `guidelines`) → test with a robust prompt → run compliance skill → polish (component showcase) → publish kit (name, thumbnail, versioning).
- **Queued prompts**: you can queue prompts/skills in Make (e.g., queue the compliance check to auto-run after generation).
- **Verification tactics**: point-and-edit tool shows purple outlines for real components; inspect code to confirm real components (e.g., SAP "object page") vs. random `<div>`s.
- **Templates (demo)**: built on SAP's "dynamic page layout" + "floor plans" (page templates/patterns); built via a long, detailed scaffolding prompt that includes flows/interactions and uses only design-system parts. For rigid templates, prefer prompt-only over design-reference attachments to hard-test the kit.
- **Onboarding overlay** (shoutout to Atlassian): a first-open overlay explaining what the template is, what can be changed, and what resources exist — onboards designers, engineers, PMs alike.
- **Presets and recipes**: a panel of pre-baked prompts so anyone can switch the whole interface/floor plan/theme in one click; also AI-generated (including the overlay TSX). File placement matters — presets/dialog go in the **app folder** (part of the template), not the guidelines folder.
- **Governance / rollout model**: two historical artifacts (library + documentation) now extended with guidelines + skill files → feed into make kits as a **governed artifact** → templates provide ideation starting points. **Kit updates (NPM packages + guidelines) publish down to all consuming templates/make files.** Emphasis on an ongoing feedback loop and testing early/often.

---

## C) Verified takeaways (with quotes)

**1. AI output only stays "on system" if you give it structured, machine-readable rules — this is the central, directly transferable lesson.**

For our team, "design system" maps to our service standards, API contracts, shared libraries, and conventions. AI won't follow them unless we encode them as structured, machine-readable guidance.

> "Make is generally good in designing with your design system. It just needs to know how… So, however you get your components into make, it still needs one thing, one critical piece. Rules."

**2. Split context into front-door + discovery + setup so the model references it deliberately, not all at once.**

This three-file structure is a reusable pattern for any AI-assisted codebase: a high-signal entry doc, a "where to find things and how to verify" doc, and an exact environment/setup doc.

> "You don't want make to have to scan through all of these files every time it needs to make a move. We want it referencing them deliberately and only when the prompt or workflow calls for it."

**3. A "discovery" doc that tells the agent where to look and how to verify reduces hallucinations.**

Directly applicable: documenting where our schemas, generated clients, and modules live — and how to verify usage — would cut AI hallucination of nonexistent methods/imports.

> "it tells the agent where to look and when and how to verify its decisions. This file also helps [prevent] hallucinated components, properties, imports, and icons by making their discovery explicit."

**4. An exact setup/environment file is non-negotiable — skipping it causes runtime failures.**

Mirrors our reality: build config, dependency versions, providers/clients setup. Encode these precisely for AI tools.

> "required CSS imports, providers, theme setup, package usage, and build configurations… If this is skipped, components may either render incorrectly or fail at runtime. So, this should be exact and explicit."

**5. Use skills to automatically verify AI output against your standards, with a numeric pass/fail threshold.**

The "compliance check" skill scoring output against a 3.8 publish threshold is a concrete quality gate. The analogue: an AI "standards check" that scores generated code against our conventions before merge.

> "the skill actually outputs for us a score out of five… Our publish threshold based on our skill is 3.8."

**6. Translating human docs into machine-readable guidance is fast with an LLM — but it's a starting point requiring human refinement.**

The ~42-minute SAP guideline generation, then refinement with engineers/PMs, is a realistic model for converting our existing docs into AI-consumable form.

> "all I actually did to turn those huge guidelines into a file for Make, I just fired up my LMM and copied the guidelines in and attached the structure… this took around 42 minutes… but it should just be the starting point."

**7. Versioned, governed kits that propagate updates downstream — like a shared internal library with semver.**

Kit updates publishing down to all consumers is exactly how a well-run shared library/BOM works in our ecosystem.

> "updates to kits can be pushed down to consuming files. That means any changes to your NPM packages and guidelines… will update when published and update any template or make file that uses them."

**8. Separate fast prototyping context from heavy production context.**

> "Production requires stability, integration pipelines, heavier QA. Prototyping code is the opposite. You want speed, faster build times, and fewer external dependencies."

**9. LLMs prefer bite-sized, well-structured information.**

> "I really tend to just read the first and the last paragraph, and large language models are not that different. They really like bite-sized information."

---

## D) Role and team actions (including AI enhancements)

- **[INFERRED] Encode our engineering standards as structured, machine-readable guidance.** Create the equivalent of the three-file pattern for our repos/services: a high-signal "front door" doc (architecture, conventions, reading order), a "discovery" doc (where schemas, clients, shared libs, tests live + how to verify usage), and an exact "setup" doc (build config, dependency versions, local env, providers/clients).
- **[INFERRED] Build AI "compliance check" skills with thresholds.** Author skills that score AI-generated code against our conventions (error handling, logging, Kafka/REST patterns, dependency rules) and gate merge on a minimum score, analogous to the 3.8 publish threshold.
- **[INFERRED] Add discovery/verification guidance to cut hallucinations.** Explicitly document where real APIs/methods/clients are and how the agent should verify them, reducing AI invention of nonexistent imports/methods.
- **[INFERRED] Treat shared internal libraries like governed, versioned "kits."** Ensure updates to shared libraries/BOMs and their AI guidance propagate to all consuming services, with versioning and an early/often feedback loop.
- **[INFERRED] Use LLMs to convert existing docs to AI-consumable form, then refine.** Bulk-translate our READMEs/runbooks/standards into structured markdown guidance with an LLM as a starting point, then have engineers/PMs refine.
- **[INFERRED] Separate prototyping vs. production scaffolds.** Maintain lightweight prototyping setups (fewer deps, fast builds) distinct from production pipelines, while still being able to pull in real shared components/packages.
- **[INFERRED] Provide templates + onboarding + presets for internal tooling.** For internal apps, offer pre-baked project/template starting points with onboarding docs and common "recipe" prompts/scaffolds so any teammate can start on-standard quickly.

---

## E) Not applicable / unclear items

- The talk is design-system/Make-specific (Figma libraries, make kits, floor plans, themes, component showcases, point-and-edit purple outlines). The concrete tooling doesn't apply to backend Java/Kafka/REST work, but the *patterns* (structured machine-readable rules, discovery/setup files, verification skills with thresholds, governed/versioned kits) transfer strongly.
- Several demo steps were fast-forwarded or pre-baked ("I'm going to fast forward to a completed version," "let's go to my first run"), so some outputs are edited rather than fully shown `[UNCLEAR IN TRANSCRIPT]` (e.g., compliance score result ~00:18:35, template generation ~00:23:13).
- SAP Fiori/UI5 specifics (dynamic page layout, floor plans, object page) are enterprise-design-system details with no direct backend equivalent; referenced only as examples.
- The exact contents of the generated guideline files and the compliance-check skill are described conceptually but not shown in full `[UNCLEAR IN TRANSCRIPT]`.

---

## F) Key terms reference

| Term | Definition |
| --- | --- |
| Figma Make | Figma's AI tool for generating code-backed designs/prototypes; the focus of this talk on making its output stay "on system" |
| NPM package | A versioned bundle of reusable code installed in an app so it uses the same components/patterns; can be LLM-generated from a Figma library and published to a private registry |
| Make kit | A packaged code representation of components plus usage guidelines so Make produces consistently on-system output (optionally using NPM packages) |
| Template | A pre-baked starting point for new make files (optionally built on a make kit), saving time and credits |
| Guidelines file (capital-G) | The default "front door" markdown doc giving product character, defaults, and the required reading order of other guideline files; cannot be deleted |
| Discovery file | A guideline doc telling the agent where to find components/source/docs/icons and how/when to verify decisions, preventing hallucinations |
| Setup file | A guideline doc with exact imports, providers, theme setup, package usage, and build config required to install/run the design system |
| Compliance check skill | A skill that reviews generated output against the design system and scores it (e.g., out of five) against a publish threshold |
| Floor plans (SAP) | SAP's reusable page templates/patterns within its dynamic page layout; analogous to page templates/patterns in other design systems |
| Presets and recipes | A panel of pre-baked prompts letting users switch interface/layout/theme in one click; placed in the app folder as part of the template |
| Onboarding overlay | A first-open overlay explaining a template's purpose, what can be changed, and available resources, for all roles |
| Governed artifact | A make kit (library + guidelines + skills) that is versioned and whose updates propagate down to all consuming templates/make files |
