# Building real-time user insights into your design workflow

**Source:** `talks/building-real-time-user-insights-into-your-design-workflow/transcript.md`
**Session:** [View session](https://config.figma.com/san-francisco/session/ddcc3459-4bc6-43d4-8aba-103c1870e703/)

---

### A) Summary

Prayag (co-founder, Marvin) argues that while AI has dramatically accelerated the speed of building products, the fundamental bottleneck in design has not changed: getting real customer feedback at the right moment before decisions are made. He contends that AI moderation tools are "a faster horse" — they scale the number of interviews but do not solve the timing problem. His solution, launched at Config 2026, is an in-app AI interview intercept: a JavaScript SDK that watches for behavioral triggers (repeated clicks, navigation confusion, new feature landing) and, at that moment, initiates a live AI-moderated interview with screen recording, intelligent follow-up questions, and support for 40 languages. Results stream back to Marvin for analysis and distribution via Slack, Teams, or Figma.

---

### B) Key points and tools

- Speed of building has massively accelerated; speed of understanding users has not kept pace
- AI moderation tools (AI-conducted interviews at scale) are a "faster horse" — don't solve the timing problem
- "Best feedback comes from the moment someone is in your product, not in a survey they fill out later"
- In-app surveys have low response rates because they ask users to convert mental models into words — high cognitive load
- **Marvin in-app AI interview intercept** (product launch at Config): JavaScript SDK trigger → screen recording → AI-moderated interview → 40-language support → video analysis → Slack/Teams/Figma distribution
- Trigger types: repeated clicking, back-and-forth navigation, new feature landing page
- "One researcher per user" — their stated product vision
- Central problem restated: "How do we get to user insights before the decision's going to be made?"

---

### C) Verified takeaways (with quotes)

**1. The timing problem is more important than the research volume problem.**
> "The problem has always been the same. How do we get user insights before the decision's going to be made?"

`[ANALOGOUS]` For internal tooling: teams often learn about internal tool usability problems from chat messages or verbal complaints — after the decision has already shipped. Even basic in-the-moment feedback (a floating "something wrong?" button with auto-captured context) would change the timing.

**2. In-the-moment feedback has fundamentally higher fidelity than reconstructed feedback.**
> "If you catch them when they're in your product, the fidelity is completely different."

`[ANALOGOUS]` For backend APIs: when an engineer encounters a confusing error response or unexpected behavior in a service, capturing that signal at the moment of confusion (not in a retro two weeks later) produces more actionable feedback. Smart error messages with embedded feedback links are a lightweight equivalent.

**3. Behavioral triggers are a more reliable signal than opt-in feedback.**
> "A trigger could be something like the user is frustrated because they keep clicking the same button over and over again."

`[ANALOGOUS]` For internal web apps: instrumenting common frustration patterns (repeated failed submissions, long dwell time on a config field, repeated error states) as behavioral signals is more reliable than waiting for users to self-report.

---

### D) Role and team actions (including AI enhancements)

1. **Add behavioral signal instrumentation to internal web apps.** Track repeated failed actions, error states, and navigation dead-ends in internal web apps. Use these signals to surface usability issues before they become Slack complaints. `[INFERRED]`

2. **Evaluate Marvin's in-app AI intercept** if the team starts building user-facing features or conducting UX research on internal tools. The behavioral trigger model is directly applicable to internal tooling. `[RELEVANCE UNCERTAIN — NEEDS CONFIRMATION]`

3. **Replace post-hoc API feedback with in-context signals.** When publishing new service endpoints or internal APIs, include a feedback mechanism in error responses (e.g., a link to a GitHub issue template pre-filled with the error context). `[INFERRED]`

---

### E) Not applicable / unclear items

- Marvin as a specific product (UX research SaaS) — evaluate separately for team's research needs
- The talk is primarily targeted at designers/UX researchers; backend service applicability is by analogy only
- `[UNCLEAR IN TRANSCRIPT]` `00:06:55–00:08:07` — Product launch video plays inline; content partially captured in transcript narration but full demo not rendered in text

---

### F) Key terms reference

| Term | Definition |
| --- | --- |
| In-app AI interview intercept | A JavaScript SDK that detects behavioral triggers in a live product and initiates a real-time AI-moderated screen-recorded interview with the user |
| Behavioral trigger | A user action pattern (repeated clicks, navigation confusion) that signals frustration and initiates a research prompt |
| AI moderation | AI-conducted user interviews; faster than scheduling human researchers but described here as "a faster horse" |
| One researcher per user | Marvin's product vision: every user gets real-time, personalized research attention at the moment they need to be heard |
| Faster horse | Doing the same thing faster without rethinking the fundamental problem; contrasted with finding the "automobile" |
