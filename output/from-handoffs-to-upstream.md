# From handoffs to upstream

**Speaker:** Frederik (last name not given), founder, 9-person design studio in Copenhagen  
**Source:** `talks/from-handoffs-to-upstream/transcript.md`

---

## A) Summary

Frederik describes how his Copenhagen design studio stopped doing handoffs and started pushing production code directly — transforming into a "design engineering studio" that owns the design system in code. The core problem he spent 12 years watching was careful design work getting "butchered in implementation," not through bad intent but through a structural gap: the person who cares about the detail is not the person who implements it. Rather than hiring engineers in-house (which he feared would flip the studio into a dev shop), he used AI to compress the timeline for a single designer to transition into a design engineering role. That designer (Modestas) went from Figma-only work to shipping an NPM component package consumed by client developers across three continents in about five months. The talk is a detailed playbook: how to pick the right person, how to time-box the initial test, how to structure daily syncs and engineering meeting exposure, and how to intervene on shame without shielding the person from productive struggle.

---

## B) Key points and tools

- **Design engineering**: the practice of designers owning, building, and shipping design systems directly in code — removing the handoff and closing the gap between design intent and shipped product
- **Moving upstream**: designers taking ownership of the implementation layer rather than delivering specs to developers and waiting for the output
- **AI's role in this shift**: compressed the timeline from "career change requiring back-to-school learning" to "2–4 months of focused work under the right conditions"
- **The one-person playbook**: pick one designer with the right traits (organized, detail-obsessed, curious about code, able to think architecturally); time-box one week with a ready-to-implement UI spec; observe, don't manage the output
- **Storybook**: the component documentation/preview tool used as the first deliverable for the design engineering pilot — components separated, running in a browser, not in Figma
- **Cursor**: the AI coding tool Modestas used to prototype and implement a "unbuildable" chart component, which he then walked developers through
- **NPM package**: the studio shipped its first design system as an NPM package with a separation-of-concerns approach — designers own the component logic, client developers hook up their own API
- **Daily 15-minute design engineering sync**: a structured daily deadline to surface blockers, prevent disappearing into perfectionism, and maintain momentum
- **"Intervene on shame, stay out of the struggle"**: the leader's role is to protect the person from public embarrassment in engineering settings before they have the language to hold their own — not to shield them from productive difficulty
- **Sentence for navigating unfamiliar territory**: "We'll circle back to you on that. We need to weigh our options." — a complete, professional answer that shows process without requiring an apology
- **Results**: 84% of production code in one client project built by a designer; design system runs white-label mobile apps in production; three designers pushing to client repos

---

## C) Verified takeaways (with quotes)

**1. The structural gap between who cares about details and who implements them is the actual problem — not communication or tooling.**

For our team's full-stack delivery work, this insight has an inverted relevance: engineers taking ownership of the UI layer close this gap from the other direction. When engineers own both the backend and the frontend, design intent doesn't get lost in a handoff — and the person who cares about the detail *is* the person who implements it.

> "What I've come to realize is that the person who cares about the detail is not the person who implements said details."

**2. AI compressed the timeline for crossing the design-to-code boundary — from a career change to months of focused work.**

By analogy, our engineers expanding into full-stack development (or into unfamiliar domains like AI-assisted features) should expect that timeline compression with AI assistance, but not a removal of the learning requirement. Architectural instinct and the ability to direct AI (not be directed by it) still take time to develop.

> "Two years ago, a product designer shipping production code or maintaining a design system, that would be a career change, completely. Now, it means a two to four months of just focused work under the right conditions."

**3. Separation of concerns (design system as NPM package, client developers hook up the API) is a strong architectural boundary.**

This directly maps to how our team should think about internal shared libraries and component ownership in our Spring Boot / multi-service architecture. Owning a well-defined module that downstream consumers can hook up to their own data layer is exactly how the studio structured their client relationship — and it's how our internal library strategy should work.

> "Our own NPM package... their developers would hook it up to their own API. Separation of concerns, just how we wanted it."

**4. To create culture change, you need a trusted peer to demonstrate what's possible — not a top-down mandate.** `[RELEVANCE UNCERTAIN — NEEDS CONFIRMATION]`

When leading a team through an unfamiliar transition (AI tooling, new technologies, new patterns), the most effective change vector is often a trusted colleague who has already done it — not a mandate from leadership.

> "Believe it or not, people don't move passionately in any direction, especially a career change, just because their boss tells them that this new thing over here, AI, is great. They move when somebody they trust shows them what is possible."

---

## D) Role and team actions (including AI enhancements)

- **[INFERRED] For full-stack delivery work: own the whole stack deliberately.** The studio's lesson — that ownership of the implementation layer is the only way to protect quality — applies to our internal tool development. When building internal web apps end-to-end, resist splitting ownership at arbitrary boundaries. The person who cares about the experience should be involved in how it's built.
- **[INFERRED] Apply the "separation of concerns" model to shared library design.** When building shared components or utilities for internal use, structure them so downstream teams can hook in their own data/logic without importing the whole library — analogous to the NPM package + client API separation described in the talk.
- **[INFERRED] Time-box AI-assisted skill acquisition.** When introducing a new tool or pattern to a team member (e.g., a new AI development workflow, a new framework), give them a bounded spike — a specific task, a clear week, and space to struggle — rather than an open-ended ramp-up. Evaluate on demonstrated capability, not cleanliness of output.

---

## E) Not applicable / unclear items

- The majority of the talk is specifically about designers transitioning into engineering roles, which is the inverse of our team's situation (engineers expanding into full-stack delivery, not the reverse).
- Storybook-based component libraries and Figma-to-code workflows are design-engineering-specific and are not applicable to our Java/Spring Boot backend work.
- The studio's commercial model (design studio selling design engineering services to clients) is not relevant to our team's internal product context.
- Mobile white-label app development is outside our current scope.

---

## F) Key terms reference

| Term | Definition |
| --- | --- |
| Design engineering | The practice of designers taking ownership of and shipping production code — specifically design systems — rather than handing off specifications to developers |
| Moving upstream | Designers entering the implementation phase earlier and more directly, rather than delivering finished specs at the end of a design process and watching from outside |
| Storybook | A development tool for building, documenting, and previewing UI components in isolation from the rest of the application |
| NPM package | A Node.js package published to the npm registry; used here as the distribution format for the studio's design system components, allowing downstream developers to install and consume them independently |
| Separation of concerns | The architectural principle of keeping distinct responsibilities in distinct modules — in this talk, the studio's components own the design logic while client developers own the API integration |
