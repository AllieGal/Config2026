# 300GB story: how to inspire action when data isn't enough

**Source:** `talks/300gb-story-how-to-inspire-action-when-data-isnt-enough/transcript.md`
**Session:** [View session](https://config.figma.com/san-francisco/session/e2b0051f-0b4a-4860-bca5-71e668b04bd9/)

---

### A) Summary

Sureena (UX designer, ex-Tesla) and Luke (engineer, ex-NASA/Waymo/Google) present a five-element data storytelling framework built from the experience of making sense of 300 GB of NASA climate data. Their central argument is that data volume is not the problem — the inability to make data feel meaningful is. Raw numbers don't drive decisions; stories do, and the gap between data and action is a design problem. The framework — setting, character, plot, conflict, and call to action — is demonstrated through a climate visualization tool tracking the pika (a mountain mammal) in the Cascades under different future climate scenarios, then validated across two other domains: US hospital blood inventory management and NASA Mars Rover telemetry. In each case the underlying data did not change; what changed was how people understood it.

---

### B) Key points and tools

- **Five elements of data storytelling:**
  1. **Setting** — context that makes numbers readable; anchor the data to a place or system
  2. **Character** — a protagonist (who or what is affected); shifts from "what data" to "who cares"
  3. **Plot** — making time visible; a static snapshot hides cause and effect
  4. **Conflict** — systemic relationships; a single metric is shallow; tension lives in connections between metrics
  5. **Call to action** — show choices and consequences, not just what happened
- Machine learning model trained on species location + climate data to generate predicted habitat maps `[UNCLEAR IN TRANSCRIPT — visual demo not captured in text]`
- Interactive web tool built to layer all five elements, including a timeline slider and species selectors
- **NASA climate dataset** — precipitation/temperature projections in 20-year intervals through 2100
- **Shared Socioeconomic Pathways** — NASA's named climate scenarios (best case, current trajectory, worst case) used to power the "call to action" layer
- Applied same framework to: US blood inventory (hospital setting, blood technologists as characters, blood movement as plot, shortage vs. waste as conflict) and NASA Mars Rover telemetry (Mars surface as setting, rover as character, daily telemetry logs as plot, subsystem failures as conflict)
- Key design principle stated: "Design the experience, not just the visualization."

---

### C) Verified takeaways (with quotes)

**1. More data does not produce better decisions — story structure does.**
> "The uncomfortable truth is having more data doesn't matter if we can't make sense of it. Because if we can't make sense of it, we won't care about it."

For a team that manages large volumes of backend data, when presenting system health, data quality issues, or incident impacts to stakeholders or leadership, raw metrics alone rarely drive urgency or action. This framework is a directly applicable communication tool.

**2. Systemic relationships — not individual metrics — create insight.**
> "A single metric gives you a shallow insight. Connected relationships are what give you a story."

This maps directly to distributed systems and event-driven architecture. When diagnosing a production issue across Kafka producers, consumers, and downstream APIs, the story isn't in a single service's error rate — it's in how failures propagate across connected systems. The same applies to presenting an incident post-mortem or a system behavior to stakeholders.

**3. Making time visible transforms a snapshot into consequence.**
> "A static view hides cause and effect. Make sure you're showing changes and consequences."

For dashboards or internal tools the team builds, this is a concrete design principle: add temporal context to metrics and events. Showing a trend line or an event timeline alongside a current state makes the data actionable rather than decorative.

**4. "Design the experience, not just the visualization" applies by analogy to internal tooling.**
> "Design the experience, not just the visualization."

`[ANALOGOUS]` Internal full-stack tools can easily default to "show the data" rather than "guide the user to a decision." This principle — that a good data experience answers "what do I do next?" — applies directly to configuration UIs, inventory dashboards, and operational tooling.

**5. The same framework works across completely different data domains.**
> "Two completely different domains and different planet, but the same five elements."

The framework is domain-agnostic. It doesn't require a design background to apply — Luke is an engineer who used it at Google, Waymo, and NASA. The team can adopt it without treating it as a "design thing."

---

### D) Role and team actions (including AI enhancements)

1. **Use the five-element framework for stakeholder presentations of complex data.** When presenting catalog health metrics, Kafka consumer lag trends, or inventory data anomalies to leadership: name the setting (which system/environment), the character (who or what is affected downstream), the plot (how it changed over time), the conflict (what's at tension), and the call to action (what decision is needed).

2. **Apply "make time visible" to internal dashboards and tooling.** When building or iterating on internal web app UIs, evaluate whether the current state view is the only view. Add timeline or change history context wherever a user needs to understand drift or causation. `[INFERRED]`

3. **Frame incident post-mortems using setting/character/plot/conflict/CTA.** This structure would make post-mortems more legible for non-technical stakeholders and clearer about what decision or action is requested at the end.

4. **When using AI to analyze or summarize data (e.g. log analysis, Kafka event patterns), prompt with story structure.** Rather than "summarize these logs," try "given this data, identify what changed over time, what is affected, and what the tradeoffs of each response are." `[INFERRED]`

---

### E) Not applicable / unclear items

- Climate data processing, ML habitat modeling, and 3D geospatial visualization — not applicable
- Specific NASA/Waymo engineering domains — used as examples only; not applicable
- `[UNCLEAR IN TRANSCRIPT]` `00:06:47` — The speakers describe and demo an interactive visualization tool; the visual output is referenced but not captured in the transcript
- `[UNCLEAR IN TRANSCRIPT]` `00:08:04–00:08:57` — Animated habitat maps and 3D terrain view are central to the talk's "plot" and "conflict" demonstrations; transcript describes what is happening but the visual impact is lost

---

### F) Key terms reference

| Term | Definition |
| --- | --- |
| Five elements of data storytelling | A framework for turning complex data into actionable narrative: Setting, Character, Plot, Conflict, Call to Action |
| Setting | The context or environment that makes raw numbers readable — answers "where does this story take place?" |
| Character | The protagonist of the data story — answers "who or what is affected by this data?" |
| Plot | The temporal dimension — how things change over time; makes cause and effect visible |
| Conflict | The systemic relationships and tensions in the data — what competing forces or connected systems are at play |
| Call to action | The choices available to the audience and what each leads to; the reason to care and act |
| Shared Socioeconomic Pathways | NASA's named climate scenario models (best case / current trajectory / worst case) used to show decision-dependent futures |
