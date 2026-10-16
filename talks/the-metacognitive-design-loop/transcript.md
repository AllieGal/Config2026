
00:00:13
Hey Config, how's your day going? Okay.   Good, awesome. All right, quick show of   hands. How many of you in the last year   or so have used AI to generate a UI   mock-up with your design system only to   spend twice as much time fixing all the   broken spacing and design tokens?   Yep.   >> Exactly. We see those hands.


00:00:32
 AI gives us   incredible speed, but it usually leaves   us with a massive cleanup job. Hi, I'm   Jenny. I'm the lead of the UX QA   engineering team at Epsilon.   >> And I'm Mike, UI design lead. Today, we   want to discuss how we've applied a new   way of thinking to our production   process to eliminate those generative   design issues.


00:00:59
  >> Let's start from my angle.   Traditionally, teams treat QA as the   gatekeeper right before a product   launch, the final hurdle that slows   everything down. Well, as a small team   against over 20 product designers and a   dozen of product engineering teams,   we were already outnumbered 100 to 1.   And we're overseeing the UI governance   of more than 60 complex applications   like audience builder, campaign   management, and loyalty programs.


00:01:31
 And   these are only a few examples across the   entire Epsilon portfolio.   >> Right. When you combine a fragmented   workflow, BRD to Figma, code to Figma,   and various AI tools that you're using   on a daily process or daily basis across   a massive portfolio of our size, the   traditional gatekeeper model simply   stops working.


00:01:55
 Historically, if you have   a design system, you're built to move   fast. But like many of you out there,   our design to dev handoff was becoming a   place where speed went to the graveyard.   So, let's take a look at our design   system. At Epsilon, we rely on Core UI   design system to keep everything   unified.


00:02:14
 But look at the sheer scale of   what we have to manually govern.   We're talking about 50 plus components,   over 30 subcomponents, 200 plus style   tokens, and more than 100 strict rules   and patterns.   >> And if you multiply those numbers, there   are 4 billion possible combinations.   That means there are 4 billion ways for   something to go wrong.


00:02:37
 And at that   scale, checking every single detail   manually doesn't just get harder, it   becomes impossible.   And when manual QA fails, the entire   product's pipeline breaks down with it.   >> Right. And uh yeah, if we can Yeah,   there we go. A little slide issue there.   Uh and then the notes are still off a   little bit.


00:03:02
 Yeah, oh nope, they're   right. So, the breakdown of what we This   is the breakdown we like to call the   pendulum of failure. On one side, you   have paralysis from over-governance. If   we all try to check every rule by hand   and micromanage every pixel, the   workflow slows to a halt, innovation   fades, and the handoff turns into   friction.


00:03:22
  >> And on the other side, you have chaos.   That's under-governance. When rules   aren't enforced consistently,   the system the system starts to drift in   subtle ways. Small inconsistencies begin   to stack. You know what those are.   Spacing feels off, components behave   differently, and edge cases are missed.


00:03:45
  Over and the the developers are forced   to make judgment calls, and designers,   they lose confidence in what's being   built. So, over time the experience   fragments. It's not one huge failure,   but a thousand tiny ones that slowly   pull the product out of alignment.   >> Right. And with these swings of   misalignment, we didn't want to have to   choose between speed or control.


00:04:10
 What we   really wanted to choose was an   equilibrium. A system where we can move   fast without losing any precision.   >> So, we have completely we reinvented our   process. Today, we're going to show you   a simple but massive shift moving QA to   the very front of the workflow. We're   going to show you how you can design at   lightning speed without sacrificing   precision.


00:04:38
 We'll show you also how we   train our agents to automatically   enforce rules so that you can stop   playing the design police and get back   to doing what you do best.   >> Absolutely. And that's when we realized   something fundamental. The problem   wasn't that our AI wasn't powerful   enough. It wasn't even a tooling issue.   We didn't even need smarter AI.


00:05:00
 We   needed an AI that could audit itself. We   needed meta-cognition.   If you've never heard of meta-cognition,   it's simply thinking about thinking.   It's the ability to reflect on a   mistake, diagnose it, and rewrite the   rules to prevent it from happening   again.   Jenny, let's go ahead and show them what   this architecture actually looks like.


00:05:22
  >> Of course, Mike. This is our   meta-cognitive design loop.   Ingest, plan, build. You're all very   familiar with these steps. Standard AI   stops at step three. And it it builds   and then it throws the output across the   fence for us to fix. We have eliminated   that by building step four and five. Our   AI   checks against the Core UI its own work   and then it loops automatically until it   passes every single rule.


00:06:00
  >> And finally, step six solidifies those   new rules. Every correction   triggers a Git commit that makes our   process smarter and more reliable after   each use, creating our desired   equilibrium.   >> We aren't just generating UI, we are   building a shared QA mind. So, how do we   actually train this mind? How do we talk   to it?   >> Well, we didn't want to compromise.


00:06:24
 We   wanted to cure that pendulum of failure.   So, we built a workflow on two   foundational tools. The first is the   Core UI MCP. It gives us direct access   to our Figma live tokens, so no   approximation, no assumptions. It builds   strictly and pulls from the latest   component catalog of Core UI. Runs every   rule it's ever learned and self-corrects   repeatedly before a human ever sees the   first output.


00:06:54
  >> And within this MCP, we have built a   dedicated UX QA tool. This is where   proactive architecture protects the   system's integrity. Every review is   grounded within the embedded Core UI   knowledge base, so the AI never drifts   from the source of truth.   >> And second is the The second tool is the   BRD agent, the business requirements   document agent.


00:07:23
  Think of it this way. Core UI MCP   protects the code. The BRD agent   protects the strategy. And the strategy   needs to be locked in early because, as   we all know, the worst moment to   discover what you're actually building   is wrong is when the design and the   development work has already begun. And   this is where UX iteration has its   biggest impact.


00:07:42
 Of course, AI   accelerates growth at accelerates   exploration, but it doesn't replace the   rigor. Our still our team still needs to   iterate, verify, and test against   concrete requirements. We're not   prompting, walking away, and calling it   done. We've built a workflow that   ensures UX design has the time and   scrutiny it deserves before anything   reaches handoff, allowing them to have   greater understanding of proposed   features and business requirements.


00:08:12
  So, let's see how this agent actually   encodes those details.   >> This is how our PRD agent workflow   operates.   We break it down into three simple   steps.   We needed to switch.   >> Yeah, the slides are just not working   today. There it goes.   >> So, we we break broken down into very   simple steps. First is set up.


00:08:35
 Instead   of starting from a blank document, the   agent interviews the PO very structured   and focused questions like who the new   users are for these features and what   exactly is out of scope.   And if the PO already has a draft, they   can upload it as well. Second is   generation. Once the agent has gathered   all of the information,   it assembles a plan.


00:09:04
 It translates plain   English into exact core UI components.   And when it's not able to find a perfect   match between a component and a a   feature, it carefully flags them as   concept slots on the code prototype or   on the Figma file so that our designers   can review them at a later time. And   finally is review and approve.


00:09:28
 This is   where human in the loop takes place.   Once the PO has explicitly approved the   plan, Now, this business requirements   document is ready for prototyping   handoff, so that our designers can   iterate on them.   This simple process ensures that every   input is on-brand, accurate, and   consistent.   >> Yeah, and to support our new process, uh   we use Figma's code connect to make our   MCP and agent workflow sharper sharper.


00:10:02
  But, building those code connect files   actually revealed something. Uh our   coded library in our design files were   not speaking the same language. So,   let's take a look at an example up here.   In our coded library, this component is   called the two-tier site header. But, in   our Figma library and in our storybook   demo, it's called the double-tier site   header.


00:10:23
 Same component, but two   different names. Um   this misalignment is a prompting failure   just waiting to happen, and it actually   did. So, consistent naming isn't just a   style preference, it's what makes   precision and predictability possible.   But,   what happens when you get all your   little ducks in a row and you line   everything up and AI still does what AI   does, it misinterprets your intent.


00:10:50
  >> That's when we use the IEU framework.   Identify, evaluate, and update. We   stopped fixing bugs and we started   mentoring logic. First, we identify the   heuristic by asking the AI, "Why did you   do that?" And second, we evaluate the   logic gap against our exact design   standards.


00:11:12
 And third, we update the   rules engine so the same mistake never   happens again. It's like mentoring your   junior assistant, but the best part is   you only have to tell them that they are   wrong for exactly one time. So, Mike,   let's take take at how we apply this on   a real UI bug.   >> Absolutely. This was a classic one when   we were trying to figure out our new   workflow. So, take a look at this table.


00:11:41
  On the surface, AI technically thinks   this is this is finished. But, the agent   treated the header and the data rows as   two completely separate layout problems.   The columns don't line up. The grid is   broken. And to anyone who knows our   system, we know that this is immediately   wrong.


00:11:56
 And this kind of error doesn't   stay contained. It creates friction. It   creates mistrust. And when agentic   workflows run without governance, they   just don't produce mistakes. They can   set governance back further than where   we started. So, the question then   becomes, what do we even do with this?   Uh as a traditional gatekeeper, I might   update the design file.


00:12:17
 Jenny might go   into the Jira ticket PR and leave a   comment for the dev to fix. But, an   architect needs to understand why this   failure happened. Not to just fix this   table once, but to make sure that it   never happens again.   >> This is the exact standard the agents   must treat the table as one straight   vertical grid.


00:12:39
 The header slots must   match the content slots beneath them.   So, how do we train the AI this   invisible rule?   >> Well, we could use a non-center   meta-cognitive prompt. We could just   say, "Hey, AI, fix this header   alignment." And the AI will guess how to   fix it eventually. But, the same mistake   will keep happening again and again and   again.


00:13:05
  >> Instead, we use a meta-cognitive prompt.   We walk it through the IEU framework.   First, we identify the reason why the   agents used the wrong number of content   slots in the header. Second, we evaluate   by explaining that the header columns   must match the data row columns beneath   them, and finally, we update the rules   engine.


00:13:30
 We encode a permanent rule for   all the layout distribution because we   force the AI to think about the grid and   reflect on its own mistake, the same bug   will never happen in our system again.   >> These rules from something as simple as   misaligned table headers to something   that's more nuanced as our butt modal   button hierarchy are exactly the type of   invisible rules that get lost in   development handoff.


00:13:59
 As a UI designer, I   know the visual logic behind our models.   Jenny knows the the to validate that UX   intent in the QA process, but when   product teams build pages with core UI   components without that governance   layer, we generate classic deck tech   debt fast, and it compounds. Suddenly,   we're just not collaborators anymore.


00:14:22
  We're back to being gatekeepers. Without   that metacognitive layer, those   invisible rules create hours of handoff   friction. That's that pendulum swing we   were talking about earlier. The endless   back and forth that nobody wants, but   everybody lives with. Codifying these   rules agentically breaks that cycle.


00:14:37
 It   reduces human error in production at the   source, and it gives us back all exactly   what we want. Less time correcting and   more time perfecting.   >> Exactly. The metacognitive   design loop moves us to true   self-governance.   The design intent is programmatically   either   programmatically validated against the   exact design standard before an engineer   ever even sees it.


00:15:11
  >> And the automatic governance can begin   with any idea.   A project manager could come to us with   a conceptual prototype.   The UX team could upload a photo from   their whiteboarding session. Genie could   update the BRD, even a single AI prompt.   Our process can only cannot only provide   those coded prototypes, but it can also   send everything back to Figma,   applying the auto layouts, theming, and   accessibility from the get-go.


00:15:35
 We are no   longer starting from scratch. Instead,   we're starting from precision.   And the browser becomes the canvas where   you apply our final brushstrokes, where   governance can truly be directed. When   the agent works directly with Core UI   and live custom properties, design   decisions stop being theoretical.


00:15:54
 And as   veterans who have always worked at that   design engineering boundary, tools like   Code Connect and A2UI aren't just new   workflow improvements and protocols.   They're how we close the loop between   what gets designed and what gets built.   >> The business impact of this is   staggering.


00:16:15
 By letting the AI do all the   heavy lifting and self-auditing, the   projects that used to take us 2 months   to build and QA, now it takes 2 hours.   And we do it without sacrificing a   single pixel of precision.   >> So, here's the blueprint we walked   through today.   First, create your own BRD agent to   standardize your strategy, preventing   mistakes before the design phase even   begins and bringing QA to the front of   the line.


00:16:47
 Second, ground your AI in an   absolute source of truth. For us, it was   creating our own MCP, the Core UI MCP,   and using Code Connect to guarantee that   our design and our code speak the exact   same language.   >> And third, stop checking every single   detail. Let the meta cognitive design   loop do all the heavy lifting and   self-correcting.


00:17:11
  Treat the browser as your canvas so that   your output is always production ready.   and finally, mentor your AI with the IEU   framework so that you can encode your   rules and you don't need to fix the same   bug again and again.   >> Right, when you combine these tools, you   build a shared QA mind.


00:17:32
 You stop being   outnumbered 100 to 1. You stop playing   the design police, and you go from being   gatekeepers, Jenny, to   >> being architects.   >> Yeah.   >> [laughter]   >> So, when the workflow is self-improving   and the governance is built in, uh   something is definitely going to shift   on your design team.


00:17:50
 You're no longer   handing off intentions and hoping that   they survive that development   translation. You're actually generating   real front-end screens and success,   proving design intent before engineering   ever enters the picture. And that closes   a huge gap that has existed in our   industry for a long time.


00:18:08
 It creates a   level of collaboration we certainly   haven't seen before at Epsilon. And more   than anything, it gives us back our   focus on craft, on quality, on the   details that actually matter. And we   become the human in the loop.   So, how do you even actually start   building this stuff? Well, luckily, you   don't need 60 applications to start.


00:18:29
 You   just need to change how you think about   your tools.   >> We want to leave you with the   architects' challenge. First, treat your   design system as code, not static pages.   Second, mentor your AI. Instead of   asking it to fix a spacing, ask it why   it used that particular spacing. And   finally,   build an immutable system so that you   don't have to fix the same bug every   sprint.


00:18:59
  >> Right, encode your corrections. So, go   ahead and scan the QR code up above if   you haven't already. You'll be able to   download our exact prompts and   templates, and more importantly, you'll   have access to Jenny's new AI tool that   lets you build your own IEU framework.   >> We used to be gatekeepers, now we are   architects.


00:19:19
 We challenge you to build   your own QA mind. Thank you.   >> Thanks.   >> [applause]

