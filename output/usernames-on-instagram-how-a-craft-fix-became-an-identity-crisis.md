# Usernames on Instagram: How a Craft Fix Became an Identity Crisis

**Speaker:** Rose McManus, Designer on Instagram (Design Systems and App-Wide Language Patterns)
**Source:** `talks/usernames-on-instagram-how-a-craft-fix-became-an-identity-crisis/transcript.md`

---

### A) Summary

Rose McManus, a designer on Instagram's design systems team, describes what began as a narrow craft question — should Instagram show usernames or display names consistently across its interface? — and evolved into a deep investigation of how product decisions become load-bearing identity infrastructure. Her central argument is that small, seemingly technical product choices can be adopted by millions of users as genuine identity artifacts in ways that are impossible to predict at the time of design. Using Jean Baudrillard's theory of simulacra and simulation as a framework, she traces how usernames on Instagram have moved from simple unique identifiers to full-fledged hyperreal identities that, for many users, are more "real" than their given names. Instagram ultimately kept usernames because they had already become that kind of infrastructure — and she encourages all product builders to ask what behaviors and paradigms they are enabling that lie beyond their current imagination.

---

### B) Key Points and Tools

- **The triggering problem**: Instagram's story viewer list was showing display names instead of usernames, allowing spam bots to display misleading names and rise to the top of lists. This was a craft inconsistency — most of the interface already used usernames.
- **The core question**: Should Instagram standardize on usernames, display names, both, or something else? Other platforms: TikTok uses display names throughout; Facebook has never had user-facing unique IDs; Twitter uses both; Snapchat uses custom names primarily.
- **Baudrillard's theory of simulacra and simulation** (Jean Baudrillard, *Simulations*, 20th century French media theorist): Four stages by which a representation becomes disconnected from reality:
  1. A faithful copy of reality (representation)
  2. A distortion or unfaithful copy
  3. A masked absence — seems real but reality is absent
  4. Hyperreality — the simulation has no relationship to any original; it is its own original artifact
- **Username constraints** drive abstraction: usernames must use the Latin alphabet, no emojis or special characters, and are zero-sum (once taken, unavailable). This forces users to approximate, distort, or entirely reinvent their identity representation.
- **Research on username abstraction across cultures**: Russian-speaking Instagram users, WeChat users, Nigerian TikTok users — the majority abstract their names in some dimension, whether abbreviating, translating, using bilingual wordplay, or adopting authenticity markers like "real" or "official" (which, ironically, mean nothing for actual authenticity).
- **Hyperreal usernames**: Some usernames have so fully divorced from the original person that the username is more real than the person's name — e.g., the Twitter account "Drill" (run by a man named Paul), whose username identity outlasted and superseded his given name.
- **Anonymity and pseudonymity as intentional levers**: Usernames enable intentional compartmentalization of identities and creation of hyperreal selves — creator brands, pseudonymous accounts, online-only personas (e.g., YoungKombucha420 as a creator identity separate from Amy France).
- **The Twitter cautionary example**: Twitter's verification rollout divorced from name matching, combined with UI mechanics where long display names push out usernames (making the real username invisible), created confusion and impersonation risk at scale.
- **Instagram's conclusion**: Kept usernames because they had already become a genuine identity artifact — "an internet export for our users, a possibility that we couldn't have planned for."
- **Design principles surfaced**:
  - Ask: "What behavior are you enabling that is beyond your current imagination?"
  - Ask: "What happens when this scales 10 times, 1,000 times, 3 billion times?"
  - Ask: "What are people investing in what we're building? Is it their identity? Is it their livelihood?"
  - Ask: "What paradigms are we creating for people who haven't been born yet?"
  - "Be pro-possibility" — surrender some control; open yourself to the world you create.
- No specific software tools mentioned.

---

### C) Verified Takeaways (with Quotes)

- **Small product decisions become load-bearing infrastructure — the same is true of API fields, event schemas, and data models.**
  > "The product choices that we make shape the world around us and reflect back to us. When we build products, we create infrastructure that real people carry with them and ultimately build around."

  Directly applicable to any work on data APIs and event schemas. Field names, data structures, and event schemas that ship today are adopted by upstream and downstream systems, consumers, and internal tools. Changing them later is costly — sometimes impossible. The "username vs. display name" dynamic maps directly to data modeling choices that seem small but become embedded.

- **Ask "what happens when this scales 10x or 1,000x?" during system design.**
  > "You have to ask yourself what behavior you're enabling that is beyond your current imagination. And what happens when this scales 10 times or a thousand times or 3 billion times?"

  Relevant to capacity planning, event schema design, and API contract decisions. A field, a topic structure, or a rate limit that works fine at current scale can become a systemic constraint or a source of unexpected behavior at eCommerce scale. This is a design-time question, not a post-launch one.

- **Unforeseeable adoption patterns should inform how loosely or tightly you constrain interfaces.**
  > "We can't predict the future, but we can use our imagination and think of human constraints with a little bit of awe and respect."

  `[RELEVANCE UNCERTAIN — NEEDS CONFIRMATION]` By analogy: when defining Kafka event schemas or REST API contracts, consider what flexibility downstream consumers might need that you haven't anticipated. Overly rigid schemas constrain future consumers; building in extensibility (e.g., a metadata map, additional properties passthrough) is the "pro-possibility" stance.

- **Naming divorces and inconsistencies create downstream confusion at scale.**
  The Twitter example (display names pushing out usernames in the UI, impersonation risk) illustrates what happens when the naming layer becomes inconsistent at scale.

  By direct analogy: if the team's Java domain model, OpenAPI spec, Kafka topic names, and UI labels use different terms for the same concept (as Epsilon also discovered with "two-tier" vs. "double-tier" in the metacognitive design loop talk), that inconsistency compounds as AI tooling, integrations, and consumers proliferate.

---

### D) Role and Team Actions (Including AI Enhancements)

- **Apply "infrastructure thinking" to data model and API design reviews.** When reviewing a new API field, event schema, or data model, explicitly ask: "If this becomes load-bearing infrastructure that downstream systems build around, does our design accommodate that? What would need to change at 10x the current consumer count?" `[INFERRED]`
- **Document the "why" behind data model decisions, especially constraints.** Username constraints (Latin-only, no emojis, zero-sum) drove years of unintended user behavior. Similarly, our API constraints (field types, required vs. optional fields, enum values) will drive downstream behavior. Documenting the reasoning behind constraints in ADRs or schema annotations creates a record that helps future teams understand what was intentional.  `[INFERRED]`
- **Audit naming consistency across the system boundary.** Cross-reference Java model names, API field names, Kafka topic/event names, and any UI labels for the same concepts. Divergences are a latent integration risk that becomes acute when AI tools or new consumers need to reason about the system. `[INFERRED]`

---

### E) Not Applicable / Unclear Items

- The core of the talk — the specific Instagram product decision about username vs. display name — is a social media product design concern with no direct equivalent in the team's backend eCommerce systems work.
- The Baudrillard framework (simulacra, simulation, hyperreality) is a cultural theory lens for understanding online identity. It is intellectually interesting but has limited direct application to backend or full-stack engineering; the takeaways above are extracted from the underlying principles, not the theory itself.
- The identity and pseudonymity discussion (creator brands, hyperreal online personas, the future of usernames at birth) is specific to consumer social media product design and does not apply to the team's work.
- The visual UI mechanics around Twitter's long display names pushing out usernames are a frontend rendering concern not directly applicable to the backend context.

---

### F) Key Terms Reference

| Term | Definition |
| --- | --- |
| Username | A unique identifier made up of characters that represents an account; for Instagram, Latin alphabet only, no emojis or special characters, zero-sum (first-come, first-served). |
| Display name | A more flexible, customizable counterpart to a username that is not subject to the same technical constraints and can include non-Latin characters, emojis, and longer strings. |
| Simulacra and simulation | Jean Baudrillard's theory describing four stages by which a representation progressively loses its relationship to the reality it depicts, culminating in "hyperreality" — a simulation that is its own original with no connection to any real referent. |
| Hyperreality | The fourth and final stage in Baudrillard's simulation theory, where the simulated version of something is more "real" than the original — illustrated by the username "Drill" being more real as an identity than the person's actual name. |
| Zero-sum (usernames) | The constraint that each username can only be held by one account at a time; once a username is taken, it is unavailable to others, which forces abstraction and approximation of real names. |
| Load-bearing infrastructure | The speaker's concept (not a Baudrillard term) for a product feature or design decision that users adopt so deeply — for identity, livelihood, or community — that it cannot be easily changed or removed without significant harm. |
| Pro-possibility | The speaker's design stance of surrendering some control over how a system is used, in order to allow for unforeseeable creative and identity-forming uses by users. |
