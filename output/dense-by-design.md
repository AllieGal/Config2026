# Dense by design

**Source:** `talks/dense-by-design/transcript.md`
**Session:** [View session](https://config.figma.com/san-francisco/session/69636242-b6b2-4b27-a831-bfd73eed654f/)

---

### A) Summary

Matthew Stromon (former Stripe designer) recounts how Stripe's CEO Patrick Collison asked why the Stripe dashboard couldn't look like the Bloomberg Terminal, which launched a year-long investigation into what "density" actually means. The central argument is that density is not a single property — it is a ladder of five progressively nuanced definitions, culminating in "value density": value delivered per second per pixel. Most discussions about making UI "more dense" are misdirected because they conflate these five different things. The real question for any design decision — or any information system — is whether the time and space you ask users to spend is commensurate with the value they receive. The talk ends with a meta-point: the most productive outcome was not an answer but a vocabulary, which is what good questions produce.

---

### B) Key points and tools

- Five definitions of density (ladder):
  1. **Visual density** — pixels/elements on screen
  2. **Information density** — data-to-ink ratio (Tufte); every pixel should communicate something
  3. **Meaning density** — arrangement communicates meaning (Gestalt: proximity, similarity, common region)
  4. **Time density** — how quickly a user extracts value; brain time thresholds are design-relevant
  5. **Value density** = value ÷ (time + space) — the target metric
- **Brain time thresholds for UI design:**
  - <100ms: instant, no animation (brain perceives as a single moment)
  - 100ms–10s: transitions and animations appropriate
  - 10s–1min: show spinner or indeterminate loader
  - >1min: let users leave; notify when done
- **Edward Tufte** — data-to-ink ratio; 1885 Paris–Lyon train schedule as the gold standard
- **Gestalt principles** — proximity, similarity, common region; arrangement without labels communicates groupings
- **Absorptive capacity** — the brain's speed limit for processing information; increasing density past it destroys usefulness
- Google vs. Yahoo: Google increased value density by removing visual and information density but giving you the one relevant link instantly
- ECG example: density is contextual and user-dependent — the same graphic is high-value-density for a cardiologist and zero-value-density for a layperson

---

### C) Verified takeaways (with quotes)

**1. The time threshold framework directly governs API + UI design decisions.**
> "Once we get past a minute... let your users just leave. I'll notify you when it's time to come back."

Directly applicable to long-running backend operations exposed through internal web apps: Kafka batch processing, catalog indexing, bulk configuration updates. Blocking the user past 1 minute is the wrong pattern — async + notification is the right one. Progress bars are required for 10s–1min operations.

**2. Value density = value ÷ (time + space) is a practical evaluation framework for any feature decision.**
> "Value density equals the amount of value that your users are getting from what you've designed divided by the amount of time and space that you ask them to spend on it."

For any feature of an internal web app: before building, ask — how much value does this provide, and how much time + screen real estate does it cost? Removing information can increase value density (the Google lesson).

**3. Arrangement communicates meaning without adding content — applicable to dashboards and config UIs.**
> "Arranging information on the page can actually communicate something."

`[ANALOGOUS]` Grouping related configuration fields by proximity, using visual similarity to indicate status patterns, and separating unrelated controls can dramatically improve internal tool comprehension without changing any content.

**4. Density is contextual to the user — the right density for an engineer differs from a business stakeholder.**
> "Density isn't fixed. It depends on who's looking at it."

When designing internal tools for dual audiences (engineers vs. operations teams), the same data surface may need different density treatments. Expert users often need more density, not less.

---

### D) Role and team actions (including AI enhancements)

1. **Apply the time threshold framework to all long-running operations in internal web apps.** Rule: >1min = async + notification; 10s–1min = progress indicator; <100ms = skip transitions entirely. `[INFERRED]`

2. **Evaluate internal tool features using value density.** For each proposed feature: what is the expected value to users, and what time + screen space does it cost? If the trade-off is unclear, the feature probably isn't ready.

3. **Use Gestalt grouping principles in internal dashboard layouts.** Proximity, similarity, and visual region communicate grouping and status for free — use them deliberately in internal web app UIs.

4. **Use AI to flag time density issues in new UI flows.** When building a new internal tool screen, prompt an agent with the time threshold framework and ask it to identify interactions likely to exceed the 10s or 1-minute thresholds. `[INFERRED]`

---

### E) Not applicable / unclear items

- Bloomberg Terminal / Stripe dashboard specific design work — not applicable
- The meta-point about questions vs. answers is useful as a mindset, but not an action item
- `[UNCLEAR IN TRANSCRIPT]` `00:10:26–00:10:45` — Live dot-rearrangement demo illustrating Gestalt meaning density; visual not captured in transcript

---

### F) Key terms reference

| Term | Definition |
| --- | --- |
| Visual density | The amount of pixels/elements present on screen |
| Information density | The proportion of visual elements that are actually communicating data (Tufte's data-to-ink ratio) |
| Meaning density | How the arrangement of information communicates groupings and relationships without labels (Gestalt) |
| Time density | How quickly a user can extract value from a screen; measured in real time |
| Value density | Value delivered ÷ (time + space cost); the ultimate metric for UI decisions |
| Absorptive capacity | The brain's speed limit for processing information; the point past which increasing density destroys usefulness |
| Gestalt | 1920s German psychology framework: proximity, similarity, and common region principles for how the brain perceives patterns |
| Data-to-ink ratio | Tufte's concept: every piece of ink on a graphic should communicate data; excess ink is noise |
