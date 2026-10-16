# The edge case is everyone

**Speakers:** Willie King (Business Development Manager, Accessibility, T-Mobile) and Lex Lilely (Associate Director of Product Strategy, Kettle)  
**Source:** `talks/the-edge-case-is-everyone/transcript.md`

---

## A) Summary

Willie King (deaf from birth, raising two deaf daughters) and Lex Lilely describe a multi-year partnership between T-Mobile and design agency Kettle to redesign the phone call experience for the deaf and hard of hearing community. The core product challenge: even with existing text-to-speech and speech-to-text tools, making a phone call as a deaf person involves constant friction — choosing a communication mode, coordinating with an interpreter, navigating IVR dial-pad menus, and dealing with silence on the other end. The talk presents three design learnings: (1) the deaf and hard of hearing community is not a monolith — communication needs are diverse and shift mid-call; (2) accessibility is a practice, not a feature — it must be integrated from day one, not added as a late-stage checklist; (3) designing *with* your intended audience, not just *for* them, produces fundamentally better results. A key insight came from a test session where one designer noticed the deaf user was exhausted by typing while the hearing user sat in complete silence — which led directly to the "quick replies" feature.

---

## B) Key points and tools

- **T-Mobile's accessibility history**: over 35 years as a relay service provider; currently the nation's leading relay provider; serves deaf, hard of hearing, deaf-blind, blind/low vision, and speech disability communities
- **Kettle**: human-centered design agency partnering with T-Mobile on this project
- **Core product goal**: an equitable call experience between a deaf/hard of hearing person and a hearing person — "what if a phone call finally worked for everyone?"
- **Three interaction modes** surfaced through user testing:
  1. Type your response → delivered via text-to-speech to the other caller
  2. Speak your response → read real-time transcription of what comes back
  3. Hear the response → reply through the keyboard
  - Preferences vary by user and can shift mid-call; the hardest design challenge was surfacing these without cluttering the call interface
- **Quick replies**: one-tap responses that keep the conversation alive in real time without requiring the deaf user to type a full response; discovered through observation, not spec — the breakthrough that came from watching a real test session
- **Dark mode**: not a simple color inversion — required defining text/background color pairings that hold up across both modes; revealed accessibility gaps that weren't anticipated upfront
- **Cognitive load reduction with color**: certain color combinations (yellows and blues in particular) can meaningfully reduce reading cognitive load on screens; being explored for future iteration
- **Onboarding design**: deliberately low-stakes feature discovery; users choose synthetic voice gender before their first call; call logs provide organizational memory; goal was "make the system feel approachable, less scary"
- **Research approach**: dedicated accessibility researcher at T-Mobile; a community of consistent deaf/hard of hearing participants who tested throughout (not one-off sessions); participants evolved from feature suggesters to fine-tuners
- **The "51 million" framing**: 1 in 7 Americans experience some degree of hearing loss (50M+); this is not a niche — it is a growing mainstream problem, increasingly including people who don't self-identify as having a hearing disability
- **Product status at time of talk**: not yet live; acknowledged as the reality of moving carefully when building for a community that has experienced harm from tools that failed them

---

## C) Verified takeaways (with quotes)

**1. Accessibility is a practice built in from day one — not a late-stage checklist item.**

This applies directly to our team's internal tool development and our eCommerce-facing services. Accessibility, observability, error handling, internationalization, and other non-functional qualities share this pattern: they are orders of magnitude more expensive to retrofit than to build in. Treating them as completion criteria rather than foundational requirements creates compounding technical debt.

> "Accessibility of any kind shouldn't be treated as a late stage checklist item. Features like dark mode and scalable text aren't just nice-to-haves. They're essential. And they need to be in the conversation from day one, not added in at the end."

**2. Design with your intended audience, not just for them — and bring them inside your process continuously.**

For our team's internal tool work, this means involving the engineers and teams who actually use these tools in the design process — not just as reviewers of finished specs but as ongoing collaborators who shape the work. When your users are in the room, you catch things that empathy and research alone cannot surface.

> "Having him in the room not only shaped the product, it changed how we operated as a team... What we found over time was that our users weren't this entity we periodically returned to. They were there, alongside us. And honestly, it made us sharper, more focused, and a lot more present."

**3. The most important features are often discovered through observation, not specification.**

The "quick replies" feature — one of the team's favorite features — was not designed in advance. It was discovered in a test session when someone noticed two things at once: the deaf user was exhausted by typing, and the hearing user was sitting in silence with no feedback cues. The breakthrough came from watching the experience, not from asking users what they needed.

> "This observation led us to one of our favorite features, quick replies. One-tap responses that keep the conversation alive in real time. They were small moments of humanity that put the texture of a real conversation back into a phone call."

**4. Designing for the underserved creates a ripple effect that improves the product for everyone.**

> "Even if accessibility isn't your core brief, treat the edges of your audience like they're the center. Because designing for accessibility creates a ripple effect that makes the product better for everyone in ways you won't always see coming."

**5. Insight and empathy are not the same thing.** `[RELEVANCE UNCERTAIN — NEEDS CONFIRMATION]`

Understanding a user group intellectually does not give you the same understanding as having a member of that group in the room. For our team, this is a reminder that building internal tools for other engineering teams without those teams present in the design process risks missing what actually matters to them.

> "As a practitioner who doesn't experience these disabilities, I had to be really honest with myself. Insight and empathy are not the same thing."

---

## D) Role and team actions (including AI enhancements)

- **[INFERRED] Treat non-functional requirements as foundational, not additive**: When designing new services or internal tools, include observability, error messaging, operational documentation, and (where applicable) accessibility as requirements from the first sprint — not items to be added before launch. Create a "non-functional requirements" section in our PRDs and technical design docs.
- **[INFERRED] Involve internal tool users in the design process continuously**: For internal tools, identify a small group of representative users (engineers from other teams, QA, on-call engineers) who can act as ongoing collaborators throughout development — not just reviewers of finished prototypes. Make it easy for them to give feedback at any stage.
- **[INFERRED] Watch your users use the tool, don't just ask them about it**: Schedule at least one observation session per internal tool where a teammate who didn't build it uses it while someone watches. The most valuable discoveries often come from what people *don't* say — where they hesitate, where they navigate incorrectly, where they give up.

---

## E) Not applicable / unclear items

- The specific product (a call experience for deaf and hard of hearing people) and its technical implementation (text-to-speech, speech-to-text, real-time transcription, synthetic voice selection) are not applicable to our backend engineering domain.
- T-Mobile's relay service infrastructure and the telecommunications accessibility regulatory context are not relevant.
- The product is not yet live at time of talk; no metrics or outcomes are available.
- The color science findings (yellows and blues reducing cognitive load) are UX/visual design specific.

The transferable principles (accessibility as practice not feature, design with not for, observation > specification, edge case = everyone) are captured in Section C.

---

## F) Key terms reference

| Term | Definition |
| --- | --- |
| Relay service | A telecommunications service that enables communication between deaf/hard of hearing individuals and hearing individuals by providing an intermediary (human or automated) for translation between TTY/text and voice |
| Quick replies | One-tap response options surfaced during a call that let a deaf user signal engagement or respond briefly without typing — discovered through observational testing, not specification |
| 21st Century IDEA Act | [Referenced in a different talk; see NASA.gov synthesis] |
| Cochlear implant | A surgically implanted device that provides a sense of sound to a person who is profoundly deaf or severely hard of hearing; one spectrum point in the diverse hearing experience the team designed for |
| Real-time call transcription | Text display of what the other caller is saying as the call happens — one of the core features enabling deaf and hard of hearing users to follow a phone conversation |
| Equitable call experience | The project's design goal: a phone call that works as well for a deaf/hard of hearing person as for a hearing person, without requiring workarounds or special coordination in advance |
