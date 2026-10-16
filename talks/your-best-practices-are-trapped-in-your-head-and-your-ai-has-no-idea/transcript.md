
00:00:13
Wonderful. Thank you for having me at   Figma. So, let's talk about snakes and   taste.   And hopefully get some more good jokes   in here.   I'm Hari Krishna. I work on VS Code and   I'm a PM.   I dabble in design, I dabble in code, I   dabble in data analysis, all the things   PM end up doing.   And I did originally   write a lot of specs.


00:00:38
  Who here knew the word or the letters   PRD before they became big with AI?   So, I   me, I I wrote PRDs.   And the problem with specs, they they   can drive decisions and they can capture   decisions, but oftentimes   you enter a meeting, nobody read your   spec, and everybody else like, "Can you   Can we go through first?" And then they   maybe last through that meeting, maybe   last through another one, but they're   not often good in really driving   decisions and making something tangible.


00:01:10
  So, when AI really hit the team in about   2 years ago, we started working going   deeper in AI and adopting it,   we saw that prototypes were a lot easier   or even me landing PRs in VS Code   directly.   Just to make a point, like, "This is a   good idea. Please, let me share what I   think we should have in VS Code.


00:01:29
" And we   have a PR ready to actually try it out.   Then, with prototypes, it became a lot   easier. If you come into a meeting with   a prototype and not a whole spec, you   actually talk about something real. You   can talk about something and make   decisions. You can bring this back into   the next meeting and bring in the   decisions from the prior meeting.


00:01:47
 You   can have AI actually apply the   discussion from the meeting. There's a   whole lot of interesting loops   happening. So, we have designers making   more powerful prototypes, iterating   quicker in their tools. We have   engineers where actually can quickly   spike something even in the PR in the   code base and PMs making a rough sketch.


00:02:07
  That's totally AI generated. My sketches   are not rough. They're really polished,   right?   Does my team know in front of you?   [laughter]   We're way too quiet for that one.   So, we want want something that we can   react to. But if something we're so fast   at AI prototyping now, and we're still   not often good at getting the output to   feel like it's actually our product cuz   that can help drive decisions.


00:02:29
 That can   help drive the nuance and the craft that   it actually looks and feels right.   And this is what I'm going to talk about   today. So, how your taste and your eyes   and your deep context from how your team   works, how you can get it into these   prototypes. And each of these compounds,   once the AI understands your taste, once   it can actually use the product, these   are all adding on top of each other and   making everything better.


00:02:56
  And it starts by writing down what's in   your head.   Let's talk about how we bring in that   taste so you don't repeat yourself all   the time to infuse taste into your AI.   So, what I'm going to show is how to   create a design skill.   So, if you're not using a design skill   while you prototype, you end up with   more generic looking things where it   doesn't use the right colors.


00:03:21
 Similar to   a design handoff where the person   getting the design doesn't actually use   the tokens but picks colors that kind of   look alike.   And every session you do in these agents   that don't have your design skills, they   start from scratch for every person in   your team. And there's a lot of tools   out there helping you with prototyping   and they make really good looking   prototypes and they might even infuse   you with some design tokens so they look   like your app, but they still don't feel   like your app. So, design system can   also bring these things into the scale,   so it looks right and doesn't and also   feels right. So, with design scale you   get the right all the right spacing, you   get all the right carryover, and it's   much easier to have these deeper   discussions in a daily review. And when   I say daily review, I mean it. We have   from the VS Code team, we switched from   a monthly release cycle to weekly   release cycle also by having these daily   check-ins to to continuously drive   decisions and unlock people, it's really


00:04:21
  part of that game. Moving faster with   prototypes.   So, let's look in one of my demo   sessions where I   worked on a Kanban style agent   orchestration board.   And that was just a   plan idea I have. We have all these   agents now working for us. How do we   effectively manage them?   The agent nicely went through the   custom agent background that is biased   towards first doing some research and   asking me questions.


00:04:47
 It actually asked   like what what I actually want and what   Kanban means in this case.   So, four questions later, it got all the   context and it made a plan.   I ran the plan segmentation and I made   this beautiful   Kanban board.   Let me just reset it so it starts from   scratch.   It's amazing. It looks looks great. This   uh   agents running with different   dependencies.


00:05:13
 They're working on their   task. Once they finish and they need   some input, they will ask for   clarifications and go into need input.   Really cool way to demonstrate the idea.   But, it also looks very very   live coded. We all see the gradients. We   see like the typical light colors from   Opus that so so loves um   big green   uh glowing buttons.


00:05:39
 So, looks cool, but   it doesn't look at all like VS Code.   So, in this this repo, I ended up   after you did some tweaking,   I ended up saving everything we talked   about. So, my questions, my input,   everything all the assumptions the   agents made, and all the input I gave, I   saved it into a spec.md.   And that's me not writing a spec, it's   just me kind of saving the conversation   and saving all the decisions we made   into something I can transfer.


00:06:07
 So, it's   really really one-pager of what we're   trying to do here.   >> [snorts]   >> Um basically, it's the long form of   please make me a Kanban board uh after   we talked about it but some more.   So, now this spec, I threw into another   repo, new prototype, pasted in the spec,   and what I get out after the agent   builds it and we do some noodling on it   is an actual nice-looking, let's make   this bigger,   nice-looking VS Code-looking prototype   that even builds on top of it.


00:06:39
 So,   there's some more input elements here.   It shows the different dependencies   between agents. So, this is a much   easier way that I can now talk about   this.   And how this works is it's a whole   prototyping repo with design skills   built in.   So, how do we get these building blocks   in there? What are all these building   blocks that actually make it possible to   make prototypes from just a simple idea   that will instantly look like your   product where you can then focus on the   details, the little effects, the   dependencies, really focus on the   experience.   One is the agents.md. That's like the   the the root of the project. And these   are all markdown files. These are all   just files in the repo in this case. So,   agents.md sits at the root and just   really describes the the brief of what   this project is about. It infuses it   with it's a VS Code prototyping repo,   think about VS Code, it's all about   prototyping. It's the always top of mind   for the agent. Every request you make to


00:07:38
  the agent, this agents.md is in its top   of mind. Then the second one is skills.   And those are just markdown files with a   description on top that are loaded on   demand when the agent sees specific   workflows that match the description.   So you can have multiple skills. You can   build a whole skill database for review,   for prototyping, for different workflows   that you found useful in the past.


00:08:00
 And   most of the time I have the agent save a   workflow, just create a skill for this   thing we just did, and then tweak it   from there.   But it's a really powerful way to build   these reusable kind of knowledge bits   and workflows and share them across the   team.   Lastly, we have instructions. And   instructions are similar to skills, but   not included based on workflow, but   based on files.


00:08:23
 So they allow you to   describe specific areas of your code   base and how the agent is supposed to   work on these areas. So all of these are   agents.md always loaded, and then skills   and instructions are progressively   disclosed to the agent. So it knows that   they exist, it knows when to load them,   but it will only ever look at the full   file once it once it matches a specific   pattern that the agent is aware of.


00:08:49
  And for all of these you want to think   about size cuz they all end up using   tokens. So it's always a good exercise   to figure out is your agents.md minimal   enough and just really captures the   essence of what the agent needs every   time it works on your project.   So, let's see how this looks like in   this prototype project.


00:09:08
  So I could browse over here to all in   the GitHub folder in my case, we're   going to go pilot, but just open up our   agent customization view.   So first one, the most important one I   mentioned is the instructions one for   agents.md.   So it's pretty straightforward. This is   This is all there is. It's   uh and the the best secret is that this   is about   um   it's kind of these extra lines.


00:09:33
 So I   kept tweaking it. I was like I created   prototype repo and then I kept tweaking   it because the agent kept making these   things like, "Oh, I going to change   this. I going to add a migration because   we have this old behavior and you need   to have the new behavior and we need to   support both.


00:09:46
" I was like, "No, this is   a prototype. We going to throw out the   old behavior. We going to move over.   This is all throwaway code. I want to   move fast. I want to be iterative. I   want to do apply a prototyping mindset."   So, this is all that the agent needs to   know always when it works on prototype   is that it's working on VS Code   features, UI concepts for VS Code.


00:10:07
  And then over time I evolved a bit more   of these development principles to not   think about how you going to ship this,   not think about too too far ahead. It's   really about focusing on the UI and the   experience and the problem. Similar how   you do a brainstorming, similar how you   do a design thinking workshop.


00:10:22
 All of   these things are really important for   the agent as well because it's otherwise   it's biased towards shipping   production-ready code, hopefully. Um   So, that's the agent assembly.   Then let's show one of the skills, the   design system skill.   It's a pretty simple one and I'm it   doesn't capture the whole design system   of VS Code, but enough to make the   prototypes look good.


00:10:47
  So, one of the easiest one, I actually   pointed it just at our folder for our   latest design theme on GitHub and it   extracted all the tokens, the spacing,   all the important stuff. I also gave it   access to our code library, to our   codicon library. So, the codicons are   all the icons that power the VS Code   icon system and that's like an instant   win to make every prototype feel much   more like VS Code that actually uses   your icon design language.


00:11:14
  So, we got color palette.   We got typography. We got a hierarchy of   headings.   We got depth. We added some shadows   lately and some corners and translucence   is in this new design system as well.   So, all of these just the combo of this   leads to instantly recognizable VS Code   design.   Not perfect, but close enough.


00:11:37
  So, lastly we have the file-based   instructions.   And one interesting thing with this   prototyping system, I added a design.md   system to every prototype cuz I find I   can talk through a prototype and noodle   on it and give feedback and iterate on   it. Let's move this over here. Actually,   the agent you misunderstood me.


00:11:55
 This is   not the problem we're trying to solve.   We're trying to solve the other problem.   But all of these things end up   not visible in the prototype. The   journey is hidden away in if I just show   people the the output. So, what is a   good artifact I can actually create   along the way?   It creates these design.md files.


00:12:12
 So, I   can go in here and actually open up the   design doc   and read about everything we did   doing this process that when I worked   with the agent and collaborated. So,   it's kind of transmission log between us   and what we decided on, how the agent   understood me, what I gave as feedback,   and all these things can then inform the   next conversation which isn't   necessarily just a prototype.


00:12:36
 So, it's   really cool system and that   design.md file is defined   here in how it's structured, in what is   in there, and how to update it.   So, these are the systems that make this   whole thing work.   But how do you share them? Now, we have   a really cool design system file and   it's in this repo. So, that's step   everybody downloading   this repo which is by the way   also open source.


00:13:04
 You can just get it on   GitHub.   You can and everybody who checks this   out will now get these skills that the   agents.md file will just work out of the   box.   But sometimes you want to then bring   these skills that work really well in   one repo and for one team across more   areas, maybe multiple teams, the whole   company.


00:13:22
 And that's where team-level   plugin marketplaces show up.   In VS Code,   you can actually browse market the   plugin marketplace right here in the UI.   I go on plugins, browse marketplace, and   we have the Copilot plugins built in,   awesome Copilot, and lastly, I have my   own plugins all the way down here from   the VS Code Team Kit.   So, the VS Code Team Kit, again, an open   source repo   on GitHub.


00:13:48
  You can check it out. It's where we   share uh code reviews things and GitHub   triage and other places that we like as   a team that makes us more productive   and   let everybody else use it.   And it's open source, so you can also   use it as well. But, it also it allows   you to connect it to any of the coding   agents you have for discovery.


00:14:05
 And when   you update them, everybody will also get   the updates.   And that's an important part. You want   to keep those things updated. That   maintenance, treating them like   infrastructure, because those are   prompts that agent harnesses and models   need to interpret. So, over time as   models update and as agents update,   these skills will work better or worse   over time.


00:14:28
 And some of you users might   have an idea like this I changed this   line to you must always do this and it   fixed all my problems. And   then you will have these philosophical   discussions on prompt crafting if you   don't have evals in place like you do   with every agentic infrastructure to   prove that the improvements actually   work.   So, it's really important to maintain   skills, to have to treat them as   infrastructure, to not have them drift   over time as you update models and   harnesses.


00:14:57
 Your team might use different   harnesses. And you have a proper   conversation around quality.   So, now the agent knows how to work with   your design. How do you actually   let it look at what you what it's   building to take more action?   So, in VS Code, we have a built-in   browser. I just showed the the websites   that you already used to preview, and   the agent can actually use the built-in   browser.


00:15:27
  And that's the most powerful thing I   recommend to everybody working on any   user-facing or any front-end application   is finding feedback loops that your   agents can use the application. We've   been doing that in VS Code in automated   ways. When we fix a front-end bug,   there's actually in the PR we have an   agent running that takes multiple   screenshots from VS Code because it's a   web app and reports back on what changed   and what got fixed.


00:15:56
  So, the built-in browser is one way to   just get an out-of-the-box eyes on your   application by the agent, and it can   iterate and fix.   If you work on native apps like Xcode um   or iOS,   then you can actually use Xcode built-in   CP as another example, which I've   a big fan of, and it's quite magical to   have the the agent just bootstrap a full   application then open it and browse   through it and take screenshots and give   feedback on its own work and tells   itself how amazing it   it did. So, it's one of these really   cool experiences, but also makes it much   more hands-off that you stop constantly   testing your own app, but the agent can   actually run through it.   And lastly, if your if your platform   isn't in here, there's probably an MCP   out there or CLI that allows you to do   that.   But it's something to really invest in   that once have it in automation, but   also have it locally, then you can have   the agent iterate over your actual   actual application and look at it.   But how does it actually do that? Like   what what do you tell the agent what


00:16:56
  it's supposed to do other than like,   "Please look at my app. Does it look   right?"   So, the does it work question is the   basic one. That's the most functional   one where the agent will give you   feedback on accessibility, maybe a   button isn't working, maybe something   else that doesn't feel right in the   application or that feels like an actual   bug.


00:17:13
 So, that's exactly the quality the   experience.   But the other experiences give it   actually a persona.   Like how would a new user with that kind   of background experience the app?   And agents are amazing. LLMs love   behaving like a different persona. In   the beginning we gave it all like you're   an expert software engineer, you're an   expert designer, designed in human   guidelines and everything.


00:17:36
 So, treat it   like give it the the persona of a new   user that's critically evaluating your   application and they have these needs.   All your user research that you've been   doing can feed into these personas and   you can get really good feedback from   the agent and and new thought processes   will be unlocked by this.   And that's like the last one as well.


00:18:00
  Like push yourself to be more of like   how do you how can you infuse a skill or   dogfooding agent with something that's   really that makes it gives it the right   mindset. Like I like the one where I   give it my vision document or my pitch   document and then just have it look at   like what I'm trying to achieve.


00:18:14
 Like   what is my promise with this   application? And then you're a critical   dogfooder that gives really   deep feedback. You're honest, you're   brutally honest. Uh tell the AI to be   really honest and roast the application   and you get better feedback.   And the agent will go deeper as well.   Because it's a critical dogfooder will   follow up a little more and do a little   bit deeper dives.


00:18:37
  So, how does this look like in action?   So, the skill we're looking at go look   over here.   Um it's also a skill in our prototype   repo. It's   my dog favorite dogfooding skill   a sharp independent dogfooder.   Um   but it's grounded in the design.md file   I showed before. So, it understands kind   of what we're trying to do with this   prototype and what's the problem, what   is the user, what is the context it's   all in.


00:19:05
 And so it first looks at the   design.md, really tries to reason about   what is it all about?   And then it opens the application, takes   screenshots, walk through the user   journey that that it kind of extracts   from design.md   and structures the feedback.   So, you can find it all in the repo   again   open source. So, it did that over   in   this   session.


00:19:30
  Okay, so it went through it took   screenshot you can see all the   screenshots it took over here.   Um it did   how many times it ran through and then   but in the end   I could read a long chat   or I could actually give it a nice uh   visual summary.   So, it's been pretty rough when I first   ran it.   Um but you can get that year of it's   it's giving feedback.


00:19:55
  Very honest feedback.   Okay, lastly we have the product brain.   Now, put it all together, put it into a   repository, your evidence that you did   research on, your prototypes, and all   your decisions.   Create different agents like design   partners and feed directions that gives   you uh more   more feedback, more pushback.


00:20:16
  >> [cough]   >> And it all compounds over time with   agents, skills, and evidence. Um put it   all into one repo and I have a link here   as well that you can try this out.   So, it's your taste, your eyes   and your context and the teams are not   winning by using more AI tools. It's all   about the context and making your taste   visible to the agent.


00:20:37
  So, when you come back home, write an   agent.md, create a skill for your   designs, and keep iterating.   Thank you.   >> [applause]

