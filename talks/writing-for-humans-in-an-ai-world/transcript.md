
00:00:14
Thank you.   Okay, so when AI started getting popular   a couple years ago, most people were   using it for text generation. They were   automating the generation of headlines,   error messages, UI copy, novels.   Uh and this was me. I was looking around   because I don't know if you know this,   but I am a human text generator.


00:00:41
  And everyone was doing my job all of a   sudden, very quickly.   It was scary. I was really wondering,   are we cooked?   Then, oddly enough, I got hired by an AI   company to lead content design.   The thing that I thought was being   eradicated by AI.   And I've been there a year and a half.   Uh I'm not cooked.   But things have changed.


00:01:15
  In fact, the first couple months of my   role at Anthropic, uh I had to kind of   figure out what my job was and what was   Claude's job.   Here's an example.   So, the waving hand is next to me. I'm   labeled human.   >> [gasps]   >> And this is a   uh PR that Claude helped push where we   were updating some error messages.


00:01:36
  So, in my old life, uh a string change   like this was a big part of my job. I   would have all these different um   documents or Figma files where I was   showing all the different variants, and   I would talk to my PM. We would run it   through engineering and then through   localization.


00:01:52
 It would come back to me   because something was always wrong.   Uh that could take 2 weeks and it was   like a big important job that I did.   Now, that process takes 20 minutes tops.   Uh, I just tell Claude what I want.   I ask it to update it in the repo. It   sends me a PR to stamp and we ship it.   I don't even have to go through   engineering because the engineers have   built the system so that we have   production-ready code.


00:02:23
  Sometimes I don't even know what I want   and I just ask Claude what needs   updating based on the content standards   that I've fed it.   So, yeah.   The part of my job, this was me uh   before, the part of my job where I was   painstakingly shaping strings is mostly   gone.   Now, my work is way further upstream   helping Claude be a good writer or   expanding our systems to help us all   write well with Claude.


00:02:52
  And it's fun to work this way. Content   designers have always wanted a seat at   the table.   Uh, and now that we can ship code, we're   kind of like dancing on the table, which   is great.   But, there was also some ego death that   had to happen through this process. I   was asking myself, am I even a writer?   Am I still a designer?   I had to just fully accept that parts of   my expertise are not needed anymore in   this AI workflow.


00:03:23
  And that shift   about what it means to design AI with AI   and what it means to have these   existential questions about your job,   um, that is what this talk is about. So,   over the last couple of months and this   year and a half, I've learned three   things that have really helped me   adjust.


00:03:40
 And if you find yourself in this   position where you're asking yourself if   you're cooked, I hope these can help you   adjust as well.   So, the first thing I realized is that   the role of language has changed so much   in the product development process. I   actually had a PM tell me the other day,   "Whoa, the market value on writing has   gone way up.


00:04:01
" And I was like, "That's   cool, cuz I'm a writer."   But, he was right. Because these are   large language models.   We use language to tell them what to   build. So, even if you weren't a writer   before, you do need to understand that   language is now a primary design medium.   And that's a big shift.   The second thing I learned to adjust to   is the pace of work.


00:04:29
  Y'all, it is not slowing down. I'm here   to [laughter] tell you.   And this is a great quote from our CPO,   Ami Vora.   Uh she says, "Technology is changing at   a rate that is hard for anyone to   understand."   People who are making products, product   designers, product makers, we need to be   the bridge between the technology and   the problem.


00:04:52
  We have to be the translation layer,   helping people understand what's even   possible, because they don't always   know.   So, that means for us, as designers, we   have to learn a new technology,   understand how to build around it,   design it to make it easier to use, and   then always be looking over our   shoulders, making sure that our users   are coming along.


00:05:18
  And that's why our job is so hard right   now. We are building on ground that is   constantly shifting.   On the micro level,   we're designing for non-determinism.   In an AI experience,   anything can happen. Not anything, if   you have safeguards, but mostly anything   can happen.   And that's not the same as designing a   static flow.


00:05:41
 And then on the macro   level,   I think my slide disappeared, but   on the macro level, we're designing for   a future that we don't know what it's   going to be, but it's rapidly being set   right now. The decisions that we're all   making are actually going to impact the   life that people lead in the next 10   years.   So, yeah.   Our design medium has changed a little   bit. The pace of work is major.


00:06:10
 And   you're building the future right now. No   pressure.   But we're going to go over each one   here.   And since that was a little heavy, I'm   just pausing for this cute moment uh   animated by our in-house animator, Bing.   Okay.   So, let's talk about the first   adjustment. Language is design.   So, where words used to be the medium   that we used to communicate about   design, or maybe words on top of the   design like UI content, now it's often   the medium that is shaping the   experience.


00:06:47
 And I'll show you what I   mean.   Earlier this year, and earlier this   week, I think, but we've been in the   headlines.   But earlier this year, a lot of people   were shifting and switching over to   Claude.   And when you switch from one AI to   another, you lose everything. It's   really painful.   We wanted to fix that.   So, the fastest way to do that is a   prompt.


00:07:12
 You give the old AI a prompt,   ask it to export memories, bring the   memories into the new AI.   We made a prompt. It didn't work. The   first team passed on it, just delivered   this really thin list, and we were kind   of like, "What's going on? This is not   what our users would expect from a   memory import feature."   But if you look at the language here,   you can kind of see why.


00:07:36
 There's phrases   like, "It is my right. It is an   imperative."   This reads like a demand letter, but it   also pattern matches to a jailbreak   attempt.   And models are are trained to be   cautious for this manipulative language.   So, it hedged and it didn't give us what   we wanted.   I reframe the prompt to be about data   portability.


00:08:03
  I said, "I'm moving to another service.   Need to export my data." Models totally   understand this as a user as a as a use   case, a legitimate user right.   And they pattern match it to account   migration.   We got way more memories.   This is what we shipped.   But even after this, a engineer rewrote   the prompt into a checklist and got even   more memories.


00:08:32
  So, millions of people have run with   this prompt now.   And what I learned that day is that not   only is my audience changed, I used to   be writing for humans, but now I'm   writing for an AI to help humans. But   for real, language is design. We changed   the words, the product experience   changed.


00:08:53
 And that is all we changed in   the design   to get different outcomes.   But that's an example of product   prompting. There's a deeper level of   prompting that not all of us get to see,   but that we should really understand.   It's system prompt and training.   So,   at Anthropic, the team who does this is   led by Amanda Askew, and her team is   concerned with Claude's character.


00:09:23
  And the prompting that they do   has these principles. And one of them is   that Claude should be diplomatically   honest rather than dishonestly   diplomatic.   That is a character trait that is   programmed into Claude way before Claude   ever meets a user.   And it is actually the thing that you   experience when Claude disagrees with   you, when Claude pushes back on you, but   does so in a respectful way.


00:09:51
  Like for instance, if you wanted to   throw a giant party in your tiny   apartment,   uh a genuinely helpful model that wasn't   quite being honest would say, "Yeah,   let's plan that party." But Claude   pushes back. Claude would say, "I don't   think you have enough room for that many   people.   Why don't you rethink this?"   And that is the experience you get with   Claude, and it's all because of that   system prompt and training.


00:10:20
  And here's an example about when Here's   an example of when our prompt made   things get a little funky.   So, we did a a little experiment in   Claude code where we added the word   sarcastic, witty, and dry into the vibe   description, and Claude turned into a   bit of a creep for a second.   >> [laughter]   [gasps]   >> It says, "Let me get some context before   I interrogate you.


00:10:44
"   >> [laughter and gasps]   >> And it was to the point where engineers   were asking Claude to be nice again.   So, what I'm saying here is like I know   not everyone in this room is a writer or   a content designer, but understanding   language's new role in the product   development process is so crucial cuz   everything you design is on top of this   layer.


00:11:08
  So, get under the hood, read your system   prompts, understand your tool   descriptions, write your own evals, and   shape that layer because that is   actually the experience.   All right. The second thing I had to   adjust to is that is the pace. And I   just keep telling myself, "Readjustment   is endless."   I had a teacher a history teacher in   seventh grade, who would start every   class by saying, "Change is the only   constant.


00:11:37
" And that's like my whole   self-care mantra at Anthropic.   So, as I spoke about earlier,   we're shipping a lot. We sometimes ship   every week for series for months on end.   And we're not only shipping products,   features, we're also shipping models.   And anytime a company ships a new model,   it not only improves what exists, it   rewrites what's possible.


00:12:07
  So, for instance, if you were going to   ask this question, "What can I create in   Claude?" That changes so dramatically   almost every week.   And every time that the capabilities of   your model or your product leap forward,   it increases this gap   of what people think AI can do and what   can actually do.


00:12:28
 And that gap is growing   every day. Like, my parents still mostly   think you can just ask Claude questions   that you would ask Google, but you can   do a lot more with it.   So, here's an example of a capability   gap that we had.   We have these things called connectors.   That's what we what we call our MCPs.   Uh but people were not finding them.


00:12:52
  They were three to four clicks deep,   and even when users would hit a moment   where a connector would actually like   make sense to use, only one to two   percent of people would go find it.   Uh but they were looking for the   connector capability. They were asking   Claude, "Hey, can you help me schedule   something? Can you look at my schedule?"   That would be a calendar tool that could   be connected.


00:13:15
 Or, "Hey, I need help with   project management." That's a project   management tool that could be connected.   And so, they were asking Claude that   question, and what we really want Claude   to do is be genuinely helpful   and connect the tool, but it also didn't   realize that that was the right answer.   So, Claude was just building the tools   from scratch,   which is like a lot of tokens and not   great.


00:13:41
  So, what we had to do for our design is   we had to create the conditions where   Claude could be genuinely helpful and   answer that question by closing that   gap. It brought the feature to users. We   wrote a prompt based on different   elicitations   to bring the connectors into the chat.   This is my obligatory metric slide to   show you that it had impact.


00:14:06
  Uh   >> [laughter]   >> But, it's also because I want you to see   that if you're having problems with, you   know, getting user adoption or getting   people to understand your product,   it might not actually be anything with   your UI or your visual design. It might   be because that gap is so wide.   And we know from our research that   people expect AI to tell them what it   can do.


00:14:32
  But, if you don't design the AI to do   that, then that gap is going to remain.   So, that's a straightforward kind of   closing of the gap. People couldn't find   a capability, we put the affordances in   place.   What about a   What about when people don't understand   a capability? That's more of a mental   model design.


00:14:55
  I'm going to tell you a little story   called the tale of agent mode.   So, we had a situation earlier this   year, a great situation, where people   were using   Claude code and they loved it, but they   were using it for more than Claude code,   more than coding, I mean.   And you can see in this tweet, there's   awesome powerful features, but I don't   really want to use the terminal UI.


00:15:16
 And   not everyone wants to see be grep and   bash all day. I I understand that.   But they wanted the capability and   there's that gap again.   So internally, we were working on   something that we were calling Claude   Code for knowledge workers. Um but it   did not have a name.   And because every single thing in AI is   called something agent or agent   something, it very quickly became known   internally as agent mode.


00:15:47
 Claude agent   mode.   But that did not feel right.   The reason it didn't feel right is   because we already knew from talking to   knowledge workers, which is all of us by   the way, um   that people who were we were building   for weren't super stoked on agents.   They wanted a tool that expanded their   capabilities, that made them feel more   skilled.


00:16:14
 They didn't want to be a   manager to a bunch of uninhabited task   loops.   But the pressure is strong. You see   agent on every single billboard.   And so we faced a lot of opposition. All   of the people who didn't want to call it   agent, we faced a lot of opposition. And   this was the vibe for a few weeks.   RIP agent mode, long live agent mode.


00:16:42
  Finally, UXR, the angels of design, did   research that kind of validated that   this was not the right model. This was   not the right mental model at all. In   fact, it's not really the big idea.   Yeah, Claude is doing agentic tasks   although Claude Code, but what future is   that building towards?   Really, people needed to understand this   new working paradigm and that is   actually what we needed to name.


00:17:10
  So we tried a ton of ideas. I was trying   to push for Claude Cook.   Honestly, so glad it didn't go that way.   >> [laughter]   [gasps]   >> But, we ended up shipping co-work, and   it was finalized by our comms team, no   less. So many people were involved. And   now it's the mental model that we're   building on for other work-based   features.


00:17:31
 I really think if we had   called it co-work agent mode, we would   have severely limited the way people   perceive it.   And co-work is now becoming   category-shaping language. Microsoft   adopted the name directly for the   co-pilot co-work powered by Anthropic,   and people started to talk about a world   where you're co-working with AI.


00:17:50
 And   that capacity gap for knowledge workers   around the question of "How do we use   Claude?" is closing, cuz now we can say,   "For co-working."   So, my call here is to remember that as   designers, our special skill is helping   people navigate the world.   And this AI world needs a lot of   navigation help.


00:18:14
 So, whether you're   closing the capacity gap with   affordances, or prompting, or mental   models,   it's going to keep growing, so your your   like skills there are ever more critical   every day.   Okay, finally,   the last thing I adjusted to is the   existential dread of designing the   future.   I think we're all kind of feeling this   right now.


00:18:45
  We don't know what the world's going to   be like, but it's rapidly being set.   I have a friend in brand who says   everything that they work on, they think   about how it will be reflected back in   10 years. And that's really like major,   and I certainly didn't feel that way   when I was writing strings in travel   software 5 years ago.


00:19:06
  But, I think we feel that way because   there's it we all know there's a big   change happening right now.   And the scale of change that AI has   often gets compared to the industrial   revolution,   which totally makes sense from an   economic standpoint. But from a design   standpoint, I think there's two other   revolutions that we should examine a   little bit more urgently.


00:19:28
  So, the first one is cars.   How does your body feel when you're   walking through a road or a neighborhood   that was built for cars versus built for   humans?   It feels different, right?   When cars arrived, design defaults   favored bigger roads and smaller   sidewalks.   And they didn't think about what it   feels like to be a person in that space.


00:19:56
  Or when social media, the this design   revolution happened,   we started seeing patterns like endless   scroll and likes and the engagement   weighted algorithms.   And now we know that it creates dopamine   spikes that have shaped our attention   spans for the past decade, much like   cars shaped our cities.   I don't think any of those designers,   those urban planners, set out to hurt   humans.


00:20:27
 And I don't think the people who   were designing social media at that time   set out to hurt teenagers' attention   spans.   But what happened is that   patterns started forming and then   proliferating, and then they became the   defaults.   And the thing about design is that it   encodes values.   So, the values for the people designing   those cities was that they wanted to   make it easier for cars to get around.


00:20:55
  And then we were stuck with a place   that's worse for pedestrians.   The values for social media is they   wanted to make it easier to stay on that   platform.   And what we got left with was something   that was way worse for our attention   spans and for our children.   We are in one of those moments right now   where the values that we have today   and the values that we encode in our   designs are going to shape the next 10   years at least.


00:21:25
  And this is a very San Franciscan San   Francisco flyer that   I saw on Andy Wolfie's LinkedIn. Thank   you, Andy.   Uh but it says give your agent legs.   It's where somebody can write an AI   and ask it to then tell a person to do a   task.   But the way that it's said, it makes the   human a sub agent.


00:21:48
 That's certainly a   value, but is it one that you want to   proliferate? Is it one that you want to   support?   I feel this so strongly on my team   because as I told you, I'm a human text   generator and I I work at an AI company   and it spits out lots of text.   And I built an agent for my team that   does 90% of our content, our UX writing.


00:22:16
  It even has a name, Content.   >> [laughter]   >> And we love it. Uh but it could have   been really scary to offload our   responsibilities to this thing.   But we wrote it, we created it with us   in mind. So it uses the team guidelines.   Uh somebody on my team, Hoy, set it up   so that it creates a ballot system every   week that we vote on.


00:22:42
 So if it if it   made a change, we vote whether or not   that's going to go into its memory. And   it also knows to ping one of us if   something like really important happens,   like a name. We do not let Content name   things.   But   what could have been scary actually   ended up being incredible. So many more   people at Anthropic know about content   design because of content.


00:23:10
  And now it's actually expanded our   reach, our scope, and our allies.   And that feeling of expansion is really   what people want from AI. They don't   want to be replaced. These are quotes   from a study we did where 80,000 people   told us about their thoughts and fears   around AI.   They're super excited, but they're also   scared because they don't know what's   going to come next.


00:23:38
  And I hate to tell you, but it's our job   here. I mean, I love to tell you cuz I'm   excited.   But it's our job to actually help them   navigate this unknown.   But how do we do that? How do we build   this future when everything is changing   for us right now?   We got to start with what we value.   So human thriving has to be the goal   that we design around.


00:24:05
  It can't be this thing that just emerges   if we get the capabilities right.   It's really easy in tech to just look   for product market fit and make a really   powerful system.   But if you don't put humans at the   center of that, you could have a really   powerful system that degrades our   relationships with each other, that eats   up our attention spans, and that even   makes us think that our own thinking   doesn't matter.


00:24:31
  And we have to start with what we know.   We know what addictive design looks   like. We've all felt it in our devices.   Design against that.   We also know that models that just tell   you what you want to hear are   sycophantic.   Eval against that.   And we know, deep in our hearts, what   humans need.   They need to feel capable.


00:24:52
 They need to   feel connected. This is a principle that   we have on our team, our product design   team.   Give users a meaningful role.   If anything, when you're designing AI   experiences, just look at that and say,   "Did I leave room for the person?"   And finally,   don't forget what you do best. If you're   an animator, like Bing who did a lot of   these animations, if you're like the   icon king or queen on your team, if you   make super dope interactions, or if   you're a writer, shout-out to my   incredible team of writers,   don't stop doing what you're doing.   I wrote these greetings in the first   couple of months I started at Anthropic.   I did not know if writing was going to   be a thing. I didn't know if content   design was dead. I wrote these and   they're still the number one thing   people reach out to me about.   Good old-fashioned product delight.   So, yes.


00:25:52
  Everything is changing.   But, what's new for designers? We've   always been on the forefront of change,   and we've always been helping people   navigate it.   So, I for one am going to keep writing   for humans in the age of AI, and I can't   wait to see how you design for them.   Thank you.   >> [applause]   [music]

