# Skill issue: how we built an OS for PMs at Figma

**Speakers:** Jinen Kamdar (Product Lead, Slides and FigJam) and Lawrence Luk (Product Technical Program Manager), Figma  
**Source:** `talks/skill-issue-how-we-built-an-os-for-pms-at-figma/transcript.md`  
**Session:** [View session](https://config.figma.com/san-francisco/session/5d27f158-dd26-4f34-b7e0-991224db8b7a/)

> **Note on names:** Transcript ASR says “Jenan” / “Janan” / “Janine” — official Config listing is **Jinen Kamdar**. Lawrence’s last name (**Luk**) is from the official listing.  
> **Transcript completeness:** Building blocks, starter skills, and 25%→100% adoption are complete in text. **Watch the recording** for What’s Up prompt iterations, starter-skill UIs, Prateek quote slide, Windows XP metaphor, and Elan’s end-to-end walkthrough.

---

## A) Summary

Jinen Kamdar and Lawrence Luk describe how a small volunteer team at Figma built PMOS (PM Operating System) — a set of AI skills, context files, and a user profile, all stored in GitHub, that gives Figma's PMs a single AI-native way to navigate their fragmented tool landscape (Slack, Asana, FigJam, Figma, GitHub, docs, task trackers). The seed came from Ezra (monetization PM); CPO Yuki sponsored three volunteers with a **1-month** build-and-rollout deadline. The core problem was glue work and catching up across five or six tools whose AI features weren’t talking to each other. The team built three foundational building blocks (context, profile, experience), three starter skills (What's Up, Write My Weekly Update, Spec Reviewer), and a hackathon-driven adoption strategy that moved from ~25% product-team setup to 100% product org adoption. The talk's closing message: this isn't revolutionary — any team could build a PMOS, a design OS, or a company OS.

---

## B) Key points and tools

- **PMOS (PM Operating System)**: a GitHub-hosted set of AI skills, context files, and a team/personal profile that any AI agent can reference; modeled on an operating system — default apps (starter skills), plus an ecosystem where users can install more or build their own (Windows XP metaphor on stage)
- **Three building blocks** (the foundational abstractions that make skills reusable):
  1. **Context**: what the agent can access (connected services and artifacts) and what matters most within them — specific Slack channels, Asana projects, relevant repos
  2. **Profile**: who you work with, your org structure, your priorities, your manager and teammates by name — lets the agent understand phrases like "my organization" or "my team"
  3. **Experience**: what makes output “readable, useful, even beautiful” — not just accurate (length/sourcing emerged earlier via prompt iteration)
- **Three starter skills**:
  1. **What's Up**: morning brief synthesizing Slack, Asana, FigJam, and other tools into a focused, sourced update — signal over noise
  2. **Write My Weekly Update**: generates a weekly update from GitHub contributions, Slack activity, and Asana — written in the user's voice; includes what shipped, what's next, what's top of mind; one-click publish
  3. **Spec Reviewer**: checks a spec document against Figma's internal spec template (problem, solution, metrics, etc.) and gives a report card with coaching on red/yellow sections
- **Skills file**: a file (stored in GitHub) that defines what the agent should do when invoked — combines context, profile, and experience building blocks; any skill can reference the shared building blocks without duplicating them
- **Connections used**: Slack, Asana, GitHub, Figma MCP (FigJam builder skill), HexMCP (experiment review), org chart
- **Friction log**: a running list of every problem, complaint, and confusion encountered during user onboarding — stack ranked and addressed iteratively; done 10+ times with the team before broader rollout
- **"Forward deployed engineer at your own company"**: the practice of sitting with users, watching them onboard, and observing where they get stuck — not just collecting feedback but observing behavior
- **Hackathon / offsite adoption strategy**: instead of async rollout (which stalled at ~25% adoption), the team took over a product offsite and ran a hackathon where PMs used PMOS to build on top of PMOS — resulted in dozens of improvements shipped to GitHub and 100% adoption
- **Named ecosystem examples:** Prateek (self-onboarded while on leave); Prasant (editor PM, prolific forker); Elan (growth PM day-in-the-life — scout → experiment review → codebase insight → FigJam; ~2 hours saved on one prep)
- **"Use it yourself every day" requirement**: the team required themselves to find product-market fit in their own workflows before considering the rest of the team
- **"If you do it wrong, you feel like you have to use AI at work. If you get it right, you feel like you get to."**: the design goal for PMOS

---

## C) Verified takeaways (with quotes)

**1. The PMOS framework (context + profile + experience) is a directly portable pattern for any team building AI-assisted workflows.**

Our team could build an Engineering OS (EMOS) using the exact same three building blocks: a context file that lists our key services, Kafka topics, API contracts, and relevant repos; a profile file that describes team members, responsibilities, and shared conventions; and experience files that govern how AI output should be formatted (concise, sourced, actionable). These files, stored in our repo, could be referenced by any AI skill we build.

> "We realized that there were three fundamental building blocks to making any skill for this type of project really valuable. Those are context, profile, and experience... We took those building blocks and abstracted them into their own files so that any prompt or skill could access them."

**2. Start with a single use case; let complexity grow naturally from there.**

Our team should resist the urge to design an all-encompassing AI system and instead identify one high-friction, repetitive task that AI could handle — a daily Jira/Slack brief, a PR description generator, an ADR template pre-filler — and build just that first.

> "It's tempting when you're starting with a really grand vision or North Star document to try to design the whole system at once, but we thought that would be biting off more than we could chew. So we tried to focus on a single use case and let the complexity grow from there."

**3. Build it for yourself first — find product-market fit in your own workflow before asking others to adopt it.**

> "The way to make something worth using every day is first to try using it every day yourself. And so this was a core requirement as we got going — we were trying to find product-market fit for ourselves with our personal workflows before considering the rest of the teams."

**4. The "What's Up" skill — a sourced, concise brief from all connected tools — is immediately applicable to our team.**

If engineers start each day reading chat, checking tickets, and reviewing PR notifications across multiple services, a "What's Up" skill that synthesizes team Slack channels, Jira sprint updates, and PR activity into a single focused brief — with source links — would reduce that context-gathering overhead.

> "We wondered if we could turn that very tedious and fragmented ritual into something that was as simple as reading an article in the newspaper. The way that would actually work is with a simple interaction where you can ask an AI what's up, and it would tell you everything that you needed to know."

**5. A "Spec Reviewer" skill — checking artifacts against team conventions — maps directly to our PR and ADR review process.**

The spec reviewer concept (AI evaluates a doc against a known template, produces a report card, coaches improvements) could be adapted for our team to review PRs against our coding standards, or ADRs against our decision record template.

> "With the spec reviewer, it'll give you a report card on how well completed those sections are. Anything that's yellow or red it will actually coach you and help elevate the standard of your document."

**6. Async rollout stalls; synchronous offsite adoption with hands-on building succeeds.**

The team hit 25% adoption with async rollout and broke through to 100% only by taking over an offsite and running a hands-on hackathon. When introducing significant AI tooling changes to our team, plan for a synchronous, dedicated session — a sprint kickoff, a team day, a hack day — rather than expecting adoption to happen organically in between meetings.

> "We knew that we weren't going to be able to get people to do this in between their busy day, in between their meetings. And so that led to step two — hijack an offsite, or really any virtual or physical space where you have your team's attention."

---

## D) Role and team actions (including AI enhancements)

- **`[INFERRED]` Build a team "Engineering OS" (EMOS)**: The talk closes on PMOS / design OS / company OS — not an “Engineering OS.” Using the same three building blocks, create three files stored in our team repo: (1) a `context.md` capturing our key services, Kafka topics, REST APIs, and repos; (2) a `profile.md` capturing team structure, member responsibilities, and shared conventions; (3) an `experience.md` capturing how AI output should be formatted. Reference these in all AI skill prompts.
- **Build a "What's Up" skill for our team**: Connect to our team's Jira board, key Slack channels, and GitHub PR activity to generate a daily brief — sourced, concise, action-item-prioritized. Start with just Jira + one Slack channel; grow from there.
- **[INFERRED] Build a PR review assistant skill**: Model after the spec reviewer — define our team's PR conventions (test coverage, error handling patterns, Kafka consumer standards, Spring Boot conventions), then build a skill that gives a report card on new PRs and coaches improvements. Validate on our own PRs first.
- **[INFERRED] Keep a friction log during AI tool rollout**: When introducing new AI workflows to the team, track every point of confusion, every failed interaction, every complaint. Stack rank and address issues before expanding adoption. Do this deliberately, not reactively.
- **[INFERRED] Plan a dedicated team session for AI workflow adoption**: Don't rely on async Confluence pages or Slack announcements to drive adoption of new AI tooling. Plan a sprint kickoff or hack day where team members set up, try, and extend the tools together — with someone available to unblock.

---

## E) Not applicable / unclear items

### Watch the recording (visuals / demos missing from transcript)

| Timestamp | What’s missing | Why it matters |
| --- | --- | --- |
| `00:01:36` | PM calendar visual | Glue-work / time allocation framing |
| `00:05:58`–`00:07:02` | What’s Up prompt iterations on screen | How building blocks were discovered |
| `00:08:29`–`00:09:27` | Starter skill UIs / report card | What’s Up, weekly update, spec reviewer |
| `00:12:18` | Prateek quote “in blue” | Adoption proof |
| `00:12:37` | Windows XP / PMOS desktop metaphor | OS analogy |
| `00:13:18`–`00:15:23` | Elan end-to-end day-in-the-life | Main applied demo |

### Other notes

- PM-specific skills (spec writing, product review facilitation, stakeholder update communication) are not directly applicable to our engineering role — but the underlying framework and most of the building blocks transfer cleanly.
- HexMCP (experiment review with statistical results) is Figma-internal tooling.
- The FigJam builder skill and Figma-specific org chart connections are design-tool-specific.
- The "codebase insight skill" example (~00:14:27) references using a GitHub connector to look at the actual codebase for technical trade-off analysis; the concept is described but the specific implementation details are not.

---

## F) Key terms reference

| Term | Definition |
| --- | --- |
| PMOS (PM Operating System) | A GitHub-hosted set of AI skills, shared context files, and a user profile that gives Figma PMs an AI-native way to navigate their fragmented tool landscape; analogous to an operating system with default apps (starter skills) and a developer ecosystem for custom extensions |
| Context (building block) | A PMOS building block that specifies which services and artifacts the agent can access, and what within them matters most (specific Slack channels, Asana projects, repos) |
| Profile (building block) | A PMOS building block that describes who you work with, your organizational context, your priorities, and your team structure — enables the agent to interpret references like "my team" or "my manager" accurately |
| Experience (building block) | A PMOS building block for making output readable, useful, even beautiful — not merely accurate |
| What's Up skill | A PMOS starter skill that synthesizes Slack, Asana, FigJam, and other connected tools into a concise, sourced morning brief — designed to replace the fragmented context-gathering ritual at the start of a PM's day |
| Spec Reviewer skill | A PMOS starter skill that evaluates a spec document against a known template, produces a report card (green/yellow/red), and coaches the author on improving incomplete sections |
| Friction log | A running log of every problem, complaint, and point of confusion encountered during user onboarding — stack ranked and addressed iteratively; the team's mechanism for continuously improving the PMOS setup experience |
| Forward deployed engineer | The practice of embedding yourself with users, watching them onboard or use a product, and observing where they get stuck — used to smooth rough edges in PMOS setup |
| Skills file | A file (stored in GitHub) that defines what an AI agent should do when a skill is invoked — references shared context, profile, and experience building blocks; any team member can extend or fork |
