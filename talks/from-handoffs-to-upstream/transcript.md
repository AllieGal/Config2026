
00:00:13
Hello everybody.   Hi. Super excited to be here. Uh I've   been asked to talk about my personal   experience of turning my design studio   into a design engineering studio that   ships and own design systems in code. Um   I haven't flown across the Atlantic   Ocean to come here to talk about AI even   though these slides may make it seem   like it.


00:00:33
 Between you and I, I'm kind of   sick of AI, honestly. And just the Uber   ride here from the airport, I watching   all those billboards, that's   insane.   However, however, the technology, AI as   a tool, um is a catalyst for us as   designers, for our industry, and for my   studio, too, to move upstream, to take   more ownership of things.   My name is Frederik.


00:00:56
 I run a nine-person   design studio back in Copenhagen. Most   of our design team push to client repos   today. I haven't forced anybody to do   this, by the way. I've created the   opportunity for them to move in that   direction.   However, as you all know, the work we've   been doing for a while now is kind of   been moving in that direction   even before AI.


00:01:16
 From a business POV as a   design studio, there's a huge commercial   upside for us to own design system work   and move closer to code as designer. But   I took this risk, I moved in this   direction because of more personal   reasons. I'll start with that first.   12 years.   That's how long I've watched um   really careful design work get butchered   in implementation.


00:01:40
 And that is sounds a   bit rough. It might my co-workers or my   own design work   not by bad developers, not by ill   intentions, but by a gap I'd accepted as   just normal, you know, cost of doing   business. We'd spend months getting   something right, and it would ship   looking just, you know, a bit wrong.   I called it a communication issue.


00:01:57
 I   called it a Figma annotation issue, and   but it wasn't. It was a structural   issue. And   what I've come to realize at least is   that the person who cares about the   detail is not the person who implements   said details.   Eight months into, just to give you a   bit of, you know, behind the scenes of   my studio.


00:02:17
 Eight months into most client   relationship, the hardest work for us   was sort of done. Like we'd architected   the systems, we'd   redesigned their products. After that,   we were just sort of on the outside   looking in.   Um   we'd see certain things get pulled   apart. It wasn't the engineer's fault on   their own.


00:02:33
 Um you know, we weren't there   to govern it. Decisions were made in   isolation. Stakeholders give feedback   way too late sometimes. But that's where   I saw the opportunity. I saw the   opportunity that if my designers could   gain the trust of our clients to get   access to our clients' code base,   we could own the design system. We could   quality assure things.


00:02:52
 We could take   ownership of component decisions.   We'd be able to keep the integrity   of our design work essentially.   The relationship would also be stronger   because we would all of a sudden be able   to take ownership of quality, the output   of what, you know, we care so much   about, what ends up in the user's hands.   And engineers, from my perspective at   least, would be freed up to do way more   more and like way more important stuff,   innovative stuff.


00:03:18
  That's a win-win-win situation.   And in case you were wondering, yes,   every quarter for the last five years of   having this agency, this studio, I've   been thinking about hiring my own   developers in-house.   I haven't done that, though.   They would have the same taste as us.   They would be sitting next to the   designers who made the decisions.


00:03:36
 We   would have control of the output.   Agencies I've looked up to for decades,   Fantasy, MetaLab, Ueno,   great teams have done it this way with   great success. But I also knew what   would happen next.   The engineering head count would   probably start to grow a bit, usually by   demand, Uh then it would outgrow the   design team that I originally set out to   build, and suddenly I'm running a   development agency with a design   function attached.


00:04:01
 And for me,   personally, that simply wasn't what I   wanted to do.   AI as a tool changed that. Not because   it makes coding easier, although it   obviously does, we all know this, but   because it changed the timeline.   Now, stick with me here because   this is this comes from my own mind. Two   years ago, a product designer shipping   production code or maintaining a design   system, that would be a career change,   completely.


00:04:28
 Like back to school,   courses, late-night learning.   Now,   it means a two to four months   two to four months of just focused work   under the right conditions, and the   conditions are super crucial. I'll get   back to this.   Um   I'm not interested. I don't know how   many engineers is in this audience, but   I'm not interested in getting jumped by   them after this talk.


00:04:46
 So, I just want to   clarify   that AI have not made anybody, you know,   a design engineer or a design system   architect like from day one. It requires   exposure, extensive training.   That's what we've been going through.   Like you need architectural instinct.   You need a dumb understanding. You need   to be able to direct the tool and not be   directed by it.


00:05:07
  Prompt engineering, super important.   AI sped up the timeline.   It did not move any bars, you know, for   quality.   Regardless, the opportunity   enabled us as a design studio to   essentially   stop handoffs. We started building, we   started shipping. We stopped being a   vendor that simply delivers, and we   became what engineers build on top of.


00:05:30
  That's crazy. It's still crazy to me.   So, if you're unaware that this is a   possibility, even after today, after all   these great talks we had,   I'm here to tell you that it's not. It's   right now, and it starts with the design   system ownership in code.   We as designers can have a much larger,   integral impact on important product   features if we own the design system.


00:05:53
  We're all in different situations both   in here and online. I'm here to show you   how a small Copenhagen based design   studio did it, but whether you're a four   Fortune 500 design director or a chief   design officer   um   freelancer even, this playbook remains   the same. And it starts with one   designer and the right conditions.


00:06:14
  The key is picking one person. Not a   team, not your entire organization, one   person. And for me, that was Modestas.   He's in the crowd somewhere here, so if   you you should find him and talk to him   later.   To give you some context, over there I   hear. I hired him 3 years earlier to   replace me in Figma.


00:06:29
 You know, I had to   run a studio. Three reasons why I picked   him. He was organized, detail obsessed,   and curious about code.   All wonderful traits to find in a   designer.   But person- personality wasn't enough.   Unfortunately, he also had four   slightly underdeveloped skills that, you   know, capabilities that I needed for   this to work. Or so I thought.


00:06:53
  He thought architecturally, you know, a   component lived inside a system in his   head, not on a page in Figma, not on the   canvas. He thought about how his work   would be consumed downstream by   developers. We saw that in, you know,   nice Figma files, good handoffs.   Developers actually wanted to consume   his work.


00:07:09
  He had basic DOM understanding from   working with developers previously.   And like anybody in this room, he could   learn how to prompt.   Not type into a chat box prompt, but you   know, direct a tool prompt. It's a big   big distinction here.   Quick note on perfectionism because I   know a lot of people in this room   probably have it.


00:07:28
  This will speed up the learning process   big time.   But you need to manage it. Modestas was   and still is super defensive about his   ideas. He's super proud. He wants to   impress. He's a good old-fashioned   perfectionist.   I love that about him because I'm very   similar. But as a leader, those traits   are important to notice because you need   to design around them.


00:07:47
 Good traits can   pose as negatives, you know, when you're   moving people to a different place or   changing their career essentially from   design to engineering.   I expected this perfectionism would slow   him down because   I knew for myself that would paralyze me   if I all of a sudden had to, you know,   go from a Figma canvas to make design   system architectural decision that would   last a long time in code.


00:08:09
  Early on, I didn't not   I just needed momentum.   That's why I told Modestas early on that   I expect mistakes. I expect the work I   expect us to look back on this work in   the next upcoming weeks and, you know,   be embarrassed by it. That's the signal   that what we're doing here is working.   Imposter syndrome   is very prevalent among me, you, all of   us.


00:08:32
  Um   if you sprinkle a bit of design system   architecture on top of that, you have a   lethal mixture. So, you as a leader need   to name it before they do.   Modestas was down for a challenge. So,   before we moved on, I time boxed 1 week.   This seems simple, but it was really   good.


00:08:49
 I, you know, removed everything   from his calendar, gave him 1 week, I   handed him a B2B SaaS UI. I know you   guys love this over here.   B2B SaaS UI that   we had design in Figma. It was fully   specked, it was ready to go, never   shipped, never coded, it was just   staying in Figma. I had some   expectations. They were quite simple,   you know, I wanted him to extract the   components, I wanted him to build the   initial Storybook setup, I wanted him to   make it real.


00:09:12
 Mind you, he'd never build   a production   component library before and I wasn't   testing whether he could do that   cleanly. That would be foolish at this   point. I was testing whether he could,   you know, under the circumstances, under   this bit of time pressure, being   uncomfortable,   lift those capabilities, those four   capabilities I just mentioned before.


00:09:31
  This is what we had at the end of the   week. Storybook running, components   separated, working in a browser, not in   a Figma file. That was a big step.   He read his way into, you know, half of   it, and you know, messed around and   figured things out as he went along.   Some of it was rough, some of it was   over-engineered, none of it was finished   by any means.


00:09:51
  Um   but the full capabilities I was looking   for was all in there.   That was enough for me to fully commit.   We moved on to something a bit more fun,   which was billable work after this, but   before I mentioned that,   I got to share you how certain things   needed to line up before we made that   decision.   The studio absorbed the cost of him   learning on the job, obviously.


00:10:11
 You   know, he's got to be able to go at his   own pace. It's super important. You   cannot rush this stuff.   We bought a design system course to   strengthen architectural decisions, and   you know, get some terminology going   both internally and externally.   And as corny as this may sound,   trust was a huge part of this.


00:10:32
  He started prototyping his design in   code on his own, without my mandate,   because he thought that was a better   medium to express his design work.   That's trust.   I have a I had a very quick clear aha   moment shortly after the initial test.   Um Modestas um   has designed something in Figma, but I   think it was a complex chart components,   and we were told it was unbuildable.


00:10:54
  This is not possible.   Modestas asked what code of JavaScript   framework the developers were using. Um   he coded it in cursor, prototyped it, uh   and he walked the developers through his   implementation.   Turns out it wasn't that unbuildable   after all.   And that was like, "Okay, this is the   right thing for us to do.


00:11:10
"   Truly one of the most important things I   did,   and also one of the simplest.   I dedicated 15 minutes of my own time   every day, call it a design engineering   sync. It was 2:00 p.m. Uh and it was a   daily deadline, essentially.   Individual contributors, from my   experience, can, you know, without a   clear horizon, can disappear into   problems and, you know, perfectionism.


00:11:35
  And this thing gave us a reason to   surface, to talk. Sometimes we talk for   5 minutes, sometimes we talk for hours.   Doesn't matter, but it was there.   Then,   I put him in engineering meetings.   This was the scariest room I could think   of, you know, representing engineering   meetings at that point in time.


00:11:54
  Great movie, too.   In the start, the meetings were   uncomfortable for both of us because it   was all brand new. We had architecture   talks, we had planning sessions, and   rooms where we did not have all the   answers yet. The instinct most leaders   have here is to protect, you know,   smooth the path, which is a good   instinct, and I agree with that.


00:12:12
 But,   initially here, the only thing I   protected Modestas from was one thing,   and that was being publicly exposed by   engineers in these   in these meetings, sorry, in these   meetings before he had the language to   hold his own.   There's a sentence I used in these   rooms.   We'll circle back to you on that. We   need to weigh our options.


00:12:31
  That's a complete answer. Requires no   apology, shows process, not ignorance,   and you really cannot be ignorant when   you're moving from design to   engineering.   You need to find your version of this   because it will happen.   Modestas watched me use these the   sentence initially. He started using it   himself, and at this point, he doesn't   need it anymore.


00:12:53
  This goes without saying,   but for all my leaders in this room, in   such a drastic transformation that is   moving a designer to become more   engineering led,   there's a difference between protecting   them from shame and protecting them from   struggle.   Struggle is a good thing. Struggle is   how we all grow.   Contemplating how, you know, we made the   wrong architectural decision 2 weeks too   late,   that sucks, but it's growth.


00:13:18
  And the late nights reading Reddit   threads about what Angular framework to   use for your next cross-platform mobile   application, I'm sure that sucks, but   it's growth, and it's really good.   Shame, however, is how people stop   growing.   Looking stupid in a Zoom call full of   engineers   kills any momentum, kills any growth   you've grown with this person.


00:13:40
  You got to intervene on the shame, and   you got to stay out of the struggle. The   struggle is good.   Back to the timeline. By October,   we shipped our first design system with   downstream developers consuming our work   in code.   Big deal. It was the initial building   blocks, the foundation, the semantic   tokens, the primitive components, all   this jazz.


00:14:01
 We even built a feature using   our own NPM package.   That's crazy. Our own NPM package. It   was an invoicing module, you know, fake   logic, but it was their developers,   Propeller, our clients' developers would   hook it up to their own API. Separation   of concerns, just how we wanted it. It   was really good, and it created the   goodwill we needed as a design studio   to be able to take more ownership of   engineering.


00:14:27
  Later, same year, in December, we had to   extend and restructure slightly the   storybook we built because Propeller   wanted us to make a mobile application   for them.   Shows what we were doing was working.   That foundation, those mobile   components, all those architectural   choices   now runs   a handful of white label apps in   production.


00:14:52
  Built off the work one designer did in   his first 5 months of transitioning into   a design engineering role. A designer   built this.   And at this point, many designers have   built this, actually.   Super super exciting.   At this point, I started seeing things   at the office, you know, culturally,   things were happening.


00:15:09
 I first saw it in   our Friday design reviews. The whole   studio looks at work in progress   together.   Modestas had Modestas had already   started bringing his, you know,   components, his code, his storybook to   these design review meetings. He brought   code and we started to see the the why   and what we we were doing clicking in   the eyes of everybody in the studio.


00:15:30
  Design engineering and design system   work started to become a topic in our   personal development conversations. The   first time it happened, uh a designer   asked me in a one-on-one, "Hey,   Frederick,   I want to do what Modestas is doing. How   can we make this happen?"   At this point, Modestas had already done   the hard part of showing everybody that   you as a designer can transition into   something potentially for them more   meaningful.


00:15:51
 You could take more   ownership of things. The empowerment was   flowing through our team and to   capitalize on this,   I planned for Modestas to speak to his   colleagues. Uh we were heading on our   annual retreat in October anyway at this   point, so it was perfect timing.   Not only did I communicate on this   annual retreat that, you know, us as a   design studio in the next year would be,   you know, our core services would become   design engineering and design system   ownership, which just sounds insane.


00:16:14
 Um   but I also asked Modestas to present. It   wasn't a status update, it was a real   talk about   what design engineering is and what it   unlocks for a designer, for our   industry.   He stood in front of his colleagues who   had watched him be uncomfortable and,   you know, very deep in his work for   months and he shared his optimism um   that this is the future.


00:16:36
 Like this is   the future for us as designers.   For me, and this seems obvious, but for   me, the same talk would have been an   instruction. But for Modestas, a guy   people trusted,   it was an offer.   Believe it or not, people don't move   passionately in any direction,   especially a career change, just because   their boss tells them that this new   thing over here, AI, is great.


00:16:59
  They move when somebody they trust like   Modestas shows them what is possible.   This is also important to say because   the honest version is that not everybody   in my team have asked to do this   transition. Some are juniors who want to   deepen their product design craft and   that is   that comes first.


00:17:13
 That's super   important. Some people are still   cautious about this whole thing and I   get that, but Modestus is part of, you   know, when they get there, they get   there.   Half of my designers ship code today.   The other half does equally important   work. This the future of our industry   does not require everybody to transition   into this.


00:17:35
  Not at all.   12 months ago, Modestus was   quote-unquote only making pixels in   Figma. Really good pixels.   But today, the design systems he built   is consumed by developers across three   continents.   That's not a job change. Like that's a   completely different person doing   completely different work in a very   short amount of time.


00:17:56
  And as a leader watching this happen has   been one of the most rewarding things   that I've done in the five years of   running the studio. And I truly believe   that you get to experience that, too.   Quickly, here's how it looks. Just a   screenshot from a Git repository.   Three designers from a team pushing   stuff into our client's codebase.


00:18:15
  This seemed impossible and insane   not that long ago.   And this number   still surprises me. We had to   double-check this a few times before we   flew over here.   84% of production code in one of our   client's projects is built by designer.   We have a design system component   coverage that is sky-high.   We have that ownership.


00:18:35
 We have that   quality.   For most of the codebase that we're in   and the one I just mentioned, the line   between designer and engineer isn't just   blurred, it's completely removed. And   that's what design engineering is to me.   Like that makes me so excited. I run a   small studio, no no scale, no famous   name. Outcome is what I sell.


00:18:51
 What   actually ships. What actually moves our   client's business forward. Design   engineering is what let me build the   studio I always dreamed of in terms of   craft.   One way the gap between what we intended   as designers in Figma   and what ships is as small as we can   possibly make it.   The commercial upside is real, but   that's not why I made the bet.


00:19:11
 I took   the risk because the work I wanted to   make as a design studio simply wasn't   possible any other way.   And I'm here to tell you that design   needs to own the code.   Whether that's your organization's   design system   or the front-end implementation of an   integral part of your product   experience,   you guys need to own the code.


00:19:31
  Design needs to move upstream.   If you lead a design team, I'll leave   you with this. If you lead a design   team, next Monday pick the designer who   cares and who shares similar uh   capabilities and interests as Modestas.   Hand him a UI ready for implementation.   Give them a week to build it. Get out of   the way.


00:19:48
  Don't force your entire organization to   chase this shiny new thing over here.   It will backfire.   And if you're a designer in this room   thinking, "My leader will never move on   this. I won't get the opportunity."   You got to start anyway.   The skills that you build now   will compound.


00:20:02
 Like from a decade from   now, this this is the thing you need to   focus on.   Monday, set up your LLM of your choice.   You know, get started with Figma MCP.   Ask a developer you trust in your team   for access to the codebase. Fix   something small. Build something new you   just designed in Figma.   Ideally using the components from your   storybook or component library.


00:20:20
 Your   developers will love you for that. Be   curious. Ask why.   The skills that you acquire now will   compound.   You don't need permission to start.   Finally, for the leaders in this room,   I've written down some thoughts in a you   know, more extended version than I can   present in 20 minutes. Uh the   day-to-day, the decision-making, the the   commercial impact.


00:20:40
 You can download it   here or you know, find me or my team   roaming around for the rest of the week.   Uh we'd love to chat. Share your link.   Thank you very much.   >> [applause]   [music]

