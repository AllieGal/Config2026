# Own the loop: how designers and researchers win with AI evals

**Source:** `talks/own-the-loop-how-designers-and-researchers-win-with-ai-evals/transcript.md`
**Session:** [View session](https://config.figma.com/san-francisco/session/2bb4e5de-dbaf-47c5-8c12-b58e5728ab62/)
**Speaker:** Setor Zilevu, Ph.D., Researcher, Figma

> **Transcript completeness:** **Among the strongest of the four** for spoken content — definitions, myths, three eval types, four levers, and the John / “technically accurate but wrong” story are fully usable from text. **Watch the recording** mainly for slides used as evidence (Design X vs Y, rehab system UI, CDO reaction, score trajectory) — not required to understand the argument.

---

## A) Summary

Setor Zilevu makes the case that AI evals — the systematic process of defining, measuring, and improving AI output quality — are not an engineering-only problem, and that designers and researchers are uniquely positioned to lead them. He opens with a formative story: an early cyber-human stroke rehabilitation system (piloted with survivors including "John" at Emory University) that correctly measured movement but missed that a patient was dangerously overcompensating — technically accurate, but wrong. This gap between "technically passes tests" and "does what people actually need" is the core problem evals are designed to close. He defines three types of evals (human, auto, and UX), walks a full Figma agent eval cycle (intent → rubric/calibration → measure → surface failure modes → improve), and identifies four levers through which product teams can directly shape AI model behavior: system prompts, eval design (rubrics), data sets, and capabilities. The central claim is that "whoever defines the rubric defines the target" — and that the ability to define what good means is a research and design skill, not an engineering one.

---

## B) Key points and tools

- **AI evals**: the systematic process of defining success criteria, measuring AI outputs against those criteria, and continuously steering model behavior toward what users actually need — not just what the model can technically produce
- **The John story**: a stroke survivor whose rehabilitation app told him he was improving while he was actually overcompensating — the system was technically accurate but wrong because the "definition of good" didn't match the therapist's judgment; the canonical example of evals failing
- **"Technically accurate but wrong"**: the class of AI failure where outputs pass all test cases but don't serve actual user needs — the problem evals are designed to surface
- **Three types of evals**:
  1. **Human evals**: a rubric is created by the team, handed to expert graders who score AI outputs against it; the grader scores become the "ground truth"; expensive and time-consuming but creates the foundation for calibration; limitation: doesn't scale
  2. **Auto evals** (AI grading AI): an LLM is taught to apply the human graders' rubric; enables scoring thousands of outputs automatically; limitation: only as good as the human graders it learned from — uncalibrated graders scale noise, not judgment
  3. **UX evals**: the product is tested with real users in their natural context; signal feeds directly into model improvements; closes the blind spots of human and auto evals (graders score in a vacuum; real users don't)
- **Eval loop**: intent → success criteria (rubric) → measure → learn → repeat (continuously)
- **"Quality is no longer verified at the end. Quality is directed throughout."**: the shift in mindset from deterministic product development to probabilistic AI product development
- **Four levers to influence model behavior**:
  1. **System prompts**: shape the model's tone, guardrails, and behavior in production
  2. **Eval design**: whoever defines the rubric defines what the model gets measured against — and therefore what it becomes
  3. **Data sets**: what the model learns from and gets judged on; must reflect real user needs, not just what's easy to collect
  4. **Capabilities**: what the model can do for people, shaped by the tools and context it's given
- **Calibration**: the process of aligning graders so they score the same output consistently — the prerequisite for human evals to produce useful signal; uncalibrated graders produce inconsistent noise
- **Edna Mode analogy (The Incredibles)**: Edna didn't start with a spec — she started with "what does Jack Jack need?" and continuously adapted the suit as she observed his behavior; the model for how to run evals
- **Two myths debunked**: (1) evals are strictly an engineering problem; (2) you define "good" once and you're done — human expectations evolve, and so must the definition
- **Human disagreement is the data**: when people can't agree on which output is better, that disagreement reveals the implicit criteria that need to be made explicit — the foundational spark of an eval

---

## C) Verified takeaways (with quotes)

**1. "Technically accurate but wrong" is the central failure mode for AI in production — evals are the mechanism to detect and prevent it.**

This is the most important takeaway for our team. AI tools can generate code that passes linting, compiles, and even passes unit tests but doesn't actually serve the intended purpose — particularly in complex domain logic (catalog data transformations, Kafka event processing, inventory state management). Building evals for AI-assisted features means defining what "correct" actually means in our domain *before* the AI produces output, not just checking that it builds.

> "What was interesting was that our system did exactly what we asked. It measured movement. It tracked progress. It gave feedback. But it still almost sent a patient down the wrong path. And because of that, I think and I reflect, I never asked the one question that truly mattered. Did our definition of good match the therapist?"

**2. "Whoever defines the rubric defines the target" — our team should own the definition of quality for AI in our systems.**

This principle has direct engineering relevance. When we use AI for code generation, PR review, or system design suggestions, the implicit rubric is being set by whoever structured the prompt or context. Making that rubric explicit — what does a good Kafka consumer look like? what does a correct catalog data transformation look like? — gives our team control over the target. Without a rubric, the AI optimizes toward a default that may not match our standards.

> "When you design the eval, you actually design what good means. And everything with the model measured is closed against the bar you set. So, whoever defines the rubric defines the target."

**3. The eval loop (intent → criteria → measure → learn → repeat) is a directly adoptable process for any AI-assisted feature.**

When our team builds or integrates an AI-assisted capability — whether it's AI code generation in our IDE, an AI feature in one of our services, or an AI-assisted migration tool — we should run this loop. Start by defining what the system needs to be good at and where to focus first. Write the success criteria before measuring. Measure consistently. Surface gaps to engineering. Repeat as user needs evolve.

> "Quality is no longer verified at the end. Quality is directed throughout. We now become the orchestrators."

**4. Auto evals (AI grading AI) scale judgment — but only if the human rubric they're trained on is calibrated.**

For our team, this has an important implication for AI-assisted code review. If we use AI to evaluate AI-generated code (e.g., a Claude code reviewer checking another Claude's output), the quality of that review is bounded by the quality of the criteria we've given it. An uncalibrated AI reviewer scales whatever implicit standard is embedded in its system prompt — which may or may not match our team's actual quality bar.

> "With auto evals, you're only as good as the human graders it learns from. So if your graders aren't calibrated, you're no longer scaling judgment, you're just scaling noise."

**5. UX evals — observing real users in natural context — surface failure modes that rubric-based evaluation misses.**

For internal tools we ship, watching real colleagues use the tool in their actual workflow will surface failure modes that no test or rubric catches. The signal from this observation should feed back into how the tool behaves — including any AI features embedded in it.

> "The people who use AI products don't live in a vacuum. They bring their own workflows, their contexts, and that context isn't always captured in human and auto evals."

---

## D) Role and team actions (including AI enhancements)

- **Define a quality rubric for AI-assisted code generation on our team**: Identify the top 3–5 criteria that define "good" AI-generated code in our context (e.g., follows Spring Boot patterns, handles Kafka consumer errors correctly, uses our shared config patterns, is properly tested). Write these down explicitly. Use this rubric when prompting AI tools and when reviewing AI-generated PRs.
- **[INFERRED] Before shipping any AI-assisted feature, define its eval loop**: For any feature that uses AI internally (AI-assisted search ranking, AI-generated recommendations, AI classification of catalog data), document: (1) what the model needs to be good at, (2) what the success criteria are, (3) how you'll measure it, and (4) how you'll surface failures for improvement. Don't ship without this loop being at least defined, even if not fully automated.
- **[INFERRED] Distinguish AI correctness from AI usefulness in testing**: When writing tests for AI-assisted features, separate "does the model produce technically valid output" (correctness) from "does the output do what users actually need" (usefulness). The John story shows these can diverge. Design at least some test cases from real user scenarios, not just schema validation.
- **[INFERRED] Calibrate any AI reviewer you use for code quality**: If you use AI to review AI-generated code (or to enforce standards), provide it with explicit rubrics, examples of good and bad output, and calibration examples before trusting its judgment at scale. An uncalibrated AI reviewer scales inconsistency.
- **[INFERRED] Apply the four levers explicitly when building AI-integrated features**: For each AI capability built into our services, identify which of the four levers (system prompts, eval design, data sets, capabilities) are in our control and invest there. Don't treat the model's default behavior as fixed.

---

## E) Not applicable / unclear items

### Watch the recording (visuals / demos missing from transcript)

| Timestamp | What’s missing | Why it matters |
| --- | --- | --- |
| `00:02:00`–`00:03:10` | Cyber-human stroke rehab system + John’s app on screen | Visual of “accurate but wrong” setup |
| `00:06:01`–`00:06:44` | Design X vs Design Y homepage images (audience vote) | The disagreement exercise is slide-dependent |
| `00:08:39`–`00:10:57` | Edna Mode / Incredibles clip | Analogy is narrated; video adds clarity |
| `00:14:47`–`00:16:49` | Figma agent eval loop artifacts (rubric, scores, failure-mode triage, CDO reaction) | Concrete Figma examples of the flywheel |
| `00:16:26`–`00:16:49` | Leadership / CDO reaction slide to improvement trajectory | Evidence of impact is on screen |

### Other notes

- Audience framing (designers/researchers “owning” evals) is less relevant to our eng team; principles transfer.
- Figma-internal agent eval details are product-specific.
- **Speaker name ASR:** transcript says "Setu Adhav"; official listing is Setor Zilevu (header uses official).
- Career path in talk: Virginia Tech → Google → Meta → Figma.

---

## F) Key terms reference

| Term | Definition |
| --- | --- |
| AI evals | The systematic process of defining success criteria, measuring AI outputs against those criteria (via human graders, automated LLM graders, or real user observation), and continuously steering model behavior toward what users actually need |
| Human eval | An eval approach where the team creates a rubric and hands it to expert graders who score AI outputs; produces calibrated ground truth but is expensive and slow to scale |
| Auto eval | An eval approach where an LLM is taught to apply a human grader's rubric and scores outputs automatically; scales to thousands of outputs but is only as good as the human calibration it was trained on |
| UX eval | An eval approach where real users interact with the AI product in their natural context; surfaces failure modes that rubric-based evaluation misses because real users bring their own workflows and contexts |
| Rubric | The explicit, shared definition of what "good" means for a given AI output — the document that graders use to score consistently; whoever defines the rubric defines what the model is optimized toward |
| Calibration | The process of aligning human graders so they score the same output consistently, using the same rubric; the prerequisite for human evals to produce reliable signal rather than individual opinion |
| Eval loop | The continuous cycle of: define intent → set success criteria → measure → learn → repeat; the speaker's framework for steering AI product quality over time |
| "Technically accurate but wrong" | The speaker's term for AI outputs that pass all technical test cases but fail to serve actual user needs — illustrated by the stroke rehabilitation system that measured movement accurately but missed dangerous compensatory behavior |
| Four levers | The speaker's framework for how product teams can directly influence model behavior: (1) system prompts, (2) eval design/rubrics, (3) training data sets, (4) capabilities/tools/context |
