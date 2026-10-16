# Legibility by design

**Speaker:** Ryan Powell, Design Lead, Waymo  
**Source:** `talks/legibility-by-design/transcript.md`

---

## A) Summary

Ryan Powell describes the design challenge at the heart of Waymo's autonomous vehicle product: when you remove the human driver, you create a communication vacuum — no eye contact, no body language, no verbal cues — that erodes rider and pedestrian trust. His team's solution was to deliberately design a "new language of trust" through carefully curated in-car UI (showing what the car sees without overwhelming), a psychoacoustic sound design system (anchored in the musical key of E), and an external LED display on the lidar dome that communicates vehicle intent to pedestrians and cyclists. The core design principle throughout is "ruthless curation over complexity" — more information doesn't build trust faster; the right information at the right moment does. The talk closes with a call to action for all designers: identify the empty driver's seats in your own products — the moments where users need a signal of intent but aren't getting one — and design to earn trust, not to educate.

---

## B) Key points and tools

- **Waymo scale**: 200M+ rider-only miles, 20M+ passenger trips, 500K+ rides/week across 11 US cities; expanding internationally to London and Tokyo
- **92% reduction in serious injury crashes** vs. human drivers — but "safety is statistical, trust is emotional"
- **The communication vacuum**: removing the human driver removes body language, eye contact, and verbal communication — all of which a passenger unconsciously reads to feel secure; design must create a proxy for this lost dialogue
- **Ruthless curation over complexity**: the engineering sensor output (raw lidar/camera data) is too dense for riders; design curates exactly what to show to build understanding without overwhelming
- **In-car 3D UI elements**:
  - Green path: the car's planned trajectory
  - Simple 3D geometry: nearby vehicles
  - Laser-point-overlaid human figures: pedestrians (showing biological motion — arms, legs)
  - Green underlay: cyclists
  - Orange traffic cones: rendered in real-time; one of the highest-yield design decisions made ("riders instantly relax")
  - Buildings: dimmed to reduce competition with more safety-relevant elements
- **Status layer**: sits above the 3D scene; acts as the "voice of the driver"; explains what the car is doing ("slowing down in a school zone"; "waiting for intersection to clear")
- **Psychoacoustics and sound design**: entire soundscape anchored in the musical key of E (associated with joy and clarity); spa music on entry; rising scale = trip start; falling scale = arrival; notifications that shift deliberately away from base key to draw attention
- **External display (lidar dome)**: a 360° display on top of the vehicle; originally used to show rider initials for identification; extended to communicate intent to pedestrians — a soft, forward-facing visual pulse ("I see you, go ahead") and a backward signal to following drivers
- **Good signal principles**: legible, easy to learn, glanceable
- **Dooring prevention**: directional chime + screen graphic if a cyclist is approaching from behind when a rider attempts to exit
- **Teen accounts**: dual-user design — freedom/privacy for teen, real-time location + support access for parent; design serving two users simultaneously with different emotional needs
- **Conversational future**: when legibility becomes invisible, interaction becomes natural language — telling the car to "pull up in front of the red car" the way you'd tell a human driver
- **Early adopters vs. mainstream**: early adopters forgive quirks for novelty; mainstream users have low tolerance and don't care about the technology — "stop designing to educate or impress, start designing for trust"

---

## C) Verified takeaways (with quotes)

**1. "Ruthless curation over complexity" is a principle for any system that communicates state to its users — including internal tooling and APIs.**

Our systems emit a lot of information: Kafka events, service logs, monitoring dashboards, API responses. The Waymo lesson is that showing everything builds anxiety, not trust. What matters is surfacing exactly the right signal at the right moment — the equivalent of orange traffic cones, not raw sensor data. This applies to how we design error messages, log output, API error payloads, and internal tool dashboards. `[RELEVANCE UNCERTAIN — NEEDS CONFIRMATION]`

> "We've learned that building trust requires a ruthless curation over complexity. We want to show you everything the car can see and how sophisticated this technology is — but we want to be able to explain its behavior without overwhelming them."

**2. When moving from early adopters to mainstream users, stop designing to impress and start designing for invisible reliability.**

Internal tools are often adopted first by technically sophisticated colleagues who tolerate friction. As usage broadens, the same design lesson applies: mainstream users want things to work predictably, not to be impressed by capability. Reliability and legibility matter more than feature exposure.

> "Stop designing to educate or to impress. Start designing for trust."

**3. Design for multiple users simultaneously when a system's actions affect more than one stakeholder.**

The teen account example — simultaneously designing for rider privacy and parental reassurance — has a direct analog in our work. Many of our systems have multiple stakeholders with different needs: data consumers who need confidence in data freshness/accuracy, operations teams who need visibility into system health, and product owners who need confidence in feature stability. A single interface design that serves one stakeholder without acknowledging others leaves gaps.

> "Here, design became less about the user interface and more about creating a silent, trusted partner for busy families."

**4. The best UX eventually becomes invisible — legibility succeeds when users stop noticing the interface and start trusting the outcome.**

> "When UX achieves perfect legibility, it becomes invisible and conversational, and dare I say, more human. You stop watching the steering wheel spinning on its own... and you just relax."

---

## D) Role and team actions (including AI enhancements)

- **[INFERRED] Apply "ruthless curation" to our internal tool interfaces**: For dashboards and internal tools, audit what information is currently surfaced and ask: is this the orange cone (instantly builds confidence) or raw sensor data (creates cognitive load)? Prioritize legibility of system state over completeness of data exposure.
- **[INFERRED] Review API error messages and log output for legibility**: Are our error responses and log messages the equivalent of the status layer ("slowing down in a school zone — here's why") or the raw sensor dump? Error messages that explain *why* a failure occurred and *what to do next* build trust in systems the way Waymo's status layer builds trust in the car.
- **[INFERRED] Identify your team's "empty driver's seats"**: In your most-used internal tools or systems, find the moments where a user has no signal about what the system is doing — loading states, long-running jobs, ambiguous failure modes. These are the communication vacuums that erode trust and generate support requests.

---

## E) Not applicable / unclear items

The primary domain of this talk — autonomous vehicle design, rider UX, external pedestrian communication, sound design for physical vehicle spaces — is not directly applicable to our backend engineering team.

- In-car UI design, 3D rendering of vehicle sensor output, psychoacoustic sound design, and external LED signaling are physical product design concerns with no engineering analog in our context.
- The Waymo rider experience (onboarding, trip UI, arrival flows) is a consumer product context.
- Teen account design and dual-user journeys are product design concerns that would apply to a consumer-facing team, not our internal tooling context.
- [UNCLEAR IN TRANSCRIPT at 00:09:23–00:10:04] — references to on-screen video demonstrations of the Waymo in-car UI and external display animations cannot be fully assessed from the transcript text alone.

The transferable insights (ruthless curation, trust through legibility, invisible UX, multi-stakeholder design) are captured in Section C above with appropriate context flags.

---

## F) Key terms reference

| Term | Definition |
| --- | --- |
| Communication vacuum | The speaker's term for the gap in human-to-human cues (eye contact, body language, verbal exchange) that opens up when the human driver is removed from a vehicle; design must create proxies for this missing communication |
| Ruthless curation | Waymo's design principle of showing only the information that builds understanding and trust — not the full raw output of the car's sensors — to avoid overwhelming riders |
| Status layer | The text-based overlay in Waymo's in-car UI that acts as the "voice of the driver," explaining what the car is currently doing and why |
| Psychoacoustics | The study of the psychological and physiological effects of sound; Waymo uses it to anchor their vehicle soundscape in the musical key of E (associated with joy and clarity) to reduce passenger anxiety |
| Legible (signal design) | A signal that is easy to understand at a glance, easy to learn once, and requires no explanation — one of three principles Waymo uses for external display design |
| Level four autonomy | Full self-driving where the passenger never needs to intervene; contrasted with driver assist (level 2/3), which still requires human readiness to take control |
| Dooring | The hazard of a vehicle door being opened into the path of an approaching cyclist or scooter; Waymo's 360° sensors detect this and alert the exiting rider before they open the door |
