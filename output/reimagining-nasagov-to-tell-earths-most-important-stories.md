# Reimagining NASA.gov to tell Earth's most important stories

**Speakers:** Ben Schoon (Head of Design, Blink UX) and Megan Greco (Senior Design Lead, Greenlight)  
**Source:** `talks/reimagining-nasagov-to-tell-earths-most-important-stories/transcript.md`

---

## A) Summary

Ben Schoon and Megan Greco describe a multi-year effort to redesign nasa.gov from a fractured landscape of 3,000+ separate sites — each competing to tell its own story — into a unified, research-grounded digital experience governed by the Horizon Design System. The project was triggered by the 21st Century Integrated Digital Experience Act (2018), which required federal agencies to modernize their digital experiences. The team's approach had three foundations: deep audience understanding through "thinking styles" (behavioral archetypes rather than demographic personas), divergent visual exploration anchored in a mood board continuum, and a deliberate process of gathering high-fidelity stakeholder feedback from low-fidelity sketches. The result is a design system now used by 500+ NASA content creators that powered real-time coverage of the Artemis 2 mission and expanded into NASA+ (streaming) and NASA Kids.

---

## B) Key points and tools

- **21st Century IDEA (Integrated Digital Experience Act)**: 2018 US legislation requiring federal agencies to modernize their digital experiences; the forcing function for the nasa.gov redesign
- **Thinking styles**: behavioral audience archetypes based on motivations, not demographics; contrasted with personas which describe *who* someone is demographically; thinking styles describe *why they care* and *how they engage*
  - Pragmatist (Miss Piggy): wants real-world impact and "how does this help me on Earth?"
  - Learner (Beaker): relentlessly curious
  - Explorer (Gonzo): pushes limits
  - Dreamer (Kermit): led by imagination
- **"Personas are the horoscopes of UX"**: vague, comforting, but rarely useful at design time; the speaker's dismissal of demographic personas in favor of thinking styles
- **Mood board continuum**: a spectrum from "technical" (methodical, analytical) to "majestic" (bold, heroic, awe-inspiring) used as a shared visual language for stakeholder alignment — not a single mood board but a range that different page types could reference
- **"Low-fi design, high-fi feedback"**: core principle — stakeholder feedback on low-fidelity sketches is more honest and actionable (engages with concepts) than feedback on high-fidelity designs (devolves into font and color debates)
- **Horizon Design System**: the atomic design system built for NASA; foundations, elements, components, modules, templates; delivered via WordPress CMS to 500+ NASA content creators; used across nasa.gov, NASA+, and NASA Kids
- **Blink UX**: the product design agency Ben leads; built the nasa.gov design system
- **Research approach**: 2,000-person survey (broad motivations, pain points) + 20 in-depth qualitative interviews (diverse age, ethnicity, income, education, familiarity with NASA)
- **Key design metaphors** extracted from divergent exploration: red arrows (wayfinding), circles (NASA's visual language — planets, engines, the meatball logo), technical bits and bobs (telemetry aesthetic), high contrast (technical modules on majestic dark backgrounds)
- **"Murphy bed" navigation**: an unobtrusive, collapsed global navigation that reveals itself on hover and tucks away to let content take center stage — the concept that survived iterative stakeholder feedback and shipped
- **Scale**: 3,000+ sites reduced to one unified experience; 500+ Horizon system users at launch; Artemis 2 (moon mission) covered in real time using the full Horizon toolkit

---

## C) Verified takeaways (with quotes)

**1. Thinking styles — understanding *why* users behave the way they do — are more actionable than demographic personas.**

For our team's internal tool development, this is directly applicable. Rather than defining our internal tool users by role (engineer, QA, PM), we should understand their behavioral motivations: the person who wants raw data access quickly (pragmatist), the person who wants to understand how the system works (learner), the person who wants to explore edge cases (explorer). These thinking styles will drive different interface decisions than role-based personas.

> "While personas tell you who someone is demographically, thinking styles tell you why they care. Unlike personas that often feel like cardboard cutouts, thinking styles are dynamic, motivational, and behavior-driven. They help you move beyond users and to design for humans."

**2. Low-fidelity proposals get higher-quality feedback from stakeholders than polished ones.**

This principle directly applies to how our team proposes architectural changes, new service designs, or internal tool features. A rough sketch of a system design (whiteboard diagram, ASCII art, simple Mermaid diagram) invites conceptual engagement. A polished implementation doc invites bikeshedding on details. When seeking meaningful feedback from partners, propose rough first.

> "Low-fidelity gets you high-fidelity feedback. It invites the right conversation. High-fidelity tends to pull the feedback towards surface-level details. That's when you start debating fonts and colors and photos."

**3. Find and serve your underserved user — that's where the real breakthrough is.**

Every product has a "Miss Piggy": a user who is perfectly capable and motivated but whom the current design has unintentionally ignored. For our internal tools, this might be the on-call engineer who needs to quickly understand a system failure, or the new team member who doesn't have the context to interpret raw data outputs. Serving that person well improves the tool for everyone.

> "Find your Miss Piggy. Every product has a user who's been underserved and underestimated. Serving that person well, that's where the real breakthroughs are."

**4. As AI tools get better at generating from design systems, the premium on divergent human exploration increases.** `[RELEVANCE UNCERTAIN — NEEDS CONFIRMATION]`

> "As AI tools get better at linking directly into our design system, there's a growing pull towards that visual average. The antidote is divergent human exploration. Use the extra time you have from these new efficient processes to get into a genuine state of play."

---

## D) Role and team actions (including AI enhancements)

- **[INFERRED] Define thinking styles for our internal tool users**: Rather than using job titles to define who uses our internal tools, identify the behavioral motivations of our actual users. What problem are they trying to solve when they open the tool? What's their relationship to the data — do they want raw access, pattern recognition, or guided decision support? These motivations should drive interface decisions.
- **[INFERRED] Use low-fidelity artifacts for architecture proposals**: When proposing a new service, a schema change, or a significant refactoring, start with a diagram or written narrative rather than a full implementation. Present it deliberately rough to invite conceptual feedback before committing to implementation details.
- **[INFERRED] Identify and serve our team's "Miss Piggy"**: Examine our internal tools and identify who among our users is underserved — likely the new engineer, the on-call engineer in a crisis, or the downstream team consumer who doesn't have deep knowledge of our domain. Improving the tool for that person typically improves it for everyone.

---

## E) Not applicable / unclear items

The majority of this talk is specific to:
- A multi-year government website redesign project
- NASA's brand identity evolution and visual design system
- Consumer-facing UX for a public information website
- The Horizon Design System (WordPress-based content management)

None of these are directly applicable to our backend engineering team's context.

The transferable insights (thinking styles, low-fi for feedback, underserved users) are captured in Section C.

[UNCLEAR IN TRANSCRIPT at 00:19:55–00:20:38] — the speaker references on-screen visuals of nasa.gov pages (topic hubs, image galleries) with intermittent technical difficulties; the design system's visual specifics cannot be fully assessed from the transcript alone.

---

## F) Key terms reference

| Term | Definition |
| --- | --- |
| 21st Century IDEA (Integrated Digital Experience Act) | 2018 US legislation requiring federal agencies to modernize their digital experiences for constituents; the forcing function for the nasa.gov redesign |
| Thinking styles | Behavioral audience archetypes based on motivations and behavior rather than demographics; describe *why* someone engages with a product, not who they are demographically; contrasted with personas which the speaker calls "the horoscopes of UX" |
| Mood board continuum | A spectrum from "technical" (analytical, precise) to "majestic" (bold, awe-inspiring) used by the Blink/NASA team as a shared visual language for design direction — not a single mood board but a range that different page types reference |
| Horizon Design System | NASA's atomic design system built by Blink UX; delivered via WordPress CMS; used by 500+ content creators across nasa.gov, NASA+, and NASA Kids |
| Low-fi design, high-fi feedback | The team's core principle: presenting low-fidelity sketches to stakeholders produces more honest, conceptual feedback; high-fidelity designs pull feedback toward surface-level details |
| Murphy bed navigation | A collapsed, hover-to-reveal global navigation pattern metaphorically inspired by a Murphy bed — appears when needed, tucks away to let content take center stage; the navigation pattern that shipped on nasa.gov |
| Atomic design system | A design system architecture built from the smallest units up: tokens → elements → components → modules → templates; both Horizon (NASA) and Nova (Rocket) use this approach |
