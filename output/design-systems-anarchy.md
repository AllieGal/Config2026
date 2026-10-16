# Design systems anarchy

**Source:** `talks/design-systems-anarchy/transcript.md`
**Session:** [View session](https://config.figma.com/san-francisco/session/ace52d61-6725-4338-80c9-cd8b0e8757e4/)

---

### A) Summary

Lauren (Head of Design Foundations at Mercury, formerly Expedia, Dropbox, Cash App) argues that design systems teams have drifted into becoming gatekeepers — the "permission required, no deviations" culture that is the opposite of their intended purpose. Drawing on three landmark punk music venues (924 Gilman, Factory Records/Haçienda, CBGB), she presents three principles for systems that enable rather than control: set clear values and get out of the way; be a relentless beacon of craft through the quality of your own artifacts; and stay radically open to how the system evolves. Her central argument is "stop thinking about building a system and start thinking about building a scene" — and the warning is that control is at odds with innovation. The best outcomes come from teams that weren't asking permission.

---

### B) Key points and tools

- Design systems teams have become gatekeepers: "stagnant systems, no deviations, permission required"
- AI as "Xerox machine" — anyone can now build; the question is whether to add constraint or enable experimentation
- Three venues / three principles:
  1. **924 Gilman** (Berkeley, all-ages punk): explicit values at the door; low barrier to contribution; trust sorts by intent — Dropbox principle: **"own the product, not the system"**
  2. **Factory Records / Haçienda** (Manchester): obsessive craft in every artifact; documentation is an argument for quality; **"be the beacon of craft"**; "coherence is evidence that someone cared"
  3. **CBGB** (NYC): two rules ("carry your equipment, play original music"); everything else up to the band; staying open created Heart of Glass
- "The people doing the most interesting work in your org are probably already outside of your system and they stopped asking permission a long time ago"
- "Deviation is the point. It always was."
- **ACAB = All Components Are Breakable** — punk reinterpretation used as the talk's closing line
- "Lowering the floor and raising the ceiling are part of the same job. Trust brings people in, and craft shows them what to aim for."
- "Taste making attracts taste makers. You find your best collaborators by making work good enough that they want to work with you."

---

### C) Verified takeaways (with quotes)

**1. Shared standards infrastructure works best when it lowers the floor AND raises the ceiling.**
> "Lowering the floor and raising the ceiling are part of the same job. Trust brings people in, and craft shows them what to aim for."

`[ANALOGOUS]` Directly applicable to how the team manages shared libraries, coding standards, and internal platform tooling. When shared standards become gatekeepers (long review cycles, rigid structure requirements, heavy boilerplate), teams route around them. The right model: make contribution easy, model exceptional quality, and let the system evolve from both ends.

**2. "Own the product, not the system" — a principle for any platform or shared infrastructure role.**
> "Our job is to build the tools, the patterns, and the documentation. What consuming teams built with them were theirs. We weren't co-authors of their product decisions."

`[ANALOGOUS]` If the team owns shared libraries, internal APIs, or platform services: the platform team's job is to enable consuming teams, not to co-own their implementation decisions. Becoming a co-author of every consumer's code is a sign the platform has become a bottleneck.

**3. The quality of documentation and code artifacts is itself a craft signal.**
> "Every artifact that you release shows your position on craft... Coherence is evidence that someone cared."

Directly applicable: the quality of the team's API documentation, service READMEs, and shared code reflects the team's quality bar to every collaborator. Well-crafted docs attract careful collaborators; sloppy docs signal that quality is optional.

**4. Teams working outside the standard system are a signal, not a compliance problem.**
> "The people doing the most interesting work in your org are probably already outside of your system and they stopped asking permission a long time ago."

When engineers build their own utilities or bypass shared patterns, that is product feedback about the shared standards. Treat it as a signal to listen to, not a compliance issue to resolve.

---

### D) Role and team actions (including AI enhancements)

1. **Audit the team's shared libraries and internal standards for gating behavior.** Which standards add meaningful quality or safety? Which just add friction? Remove or automate the friction-only gates. `[INFERRED]`

2. **Invest in the quality of shared tooling documentation as a craft signal.** README files, API docs, and service specs that are clearly well-made attract collaborative contributions. Use AI to bring existing docs up to a higher quality bar quickly. `[INFERRED]`

3. **Treat teammates who build workarounds as product feedback providers.** When someone writes their own utility instead of using a shared one, ask why rather than enforcing compliance — the answer usually points to a gap in the shared standard.

4. **Apply "own the product, not the system" to any platform responsibilities.** If the team has shared library or internal platform ownership, define clearly: the platform team ships the stage, product teams play the show — not the other way around.

---

### E) Not applicable / unclear items

- The design systems content is primarily for design infrastructure teams; all applicability here is by analogy to shared engineering standards
- Factory Records, CBGB, and 924 Gilman — used as illustrative examples; the principles are the takeaway
- Specific design tooling (Figma variants, component sets) — not applicable

---

### F) Key terms reference

| Term | Definition |
| --- | --- |
| Design system as "venue" | Metaphor: shared infrastructure enables product teams (bands) to do their best work; it doesn't control what they play |
| Permissive by design | Setting clear principles and enabling contribution, then reviewing and evolving post-hoc rather than gating up front |
| ACAB | "All Components Are Breakable" — no part of the system is so precious it can't evolve or break |
| Own the product, not the system | Dropbox principle: platform teams build tools and patterns; consuming teams own their product decisions |
| Taste making attracts taste makers | Making your own work excellent draws in the best collaborators; craft is a magnet, not just a standard |
