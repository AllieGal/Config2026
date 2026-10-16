
00:00:12
Well, hello. Um, welcome to our final   session of talks for today on the   mezzanine stage. If we haven't met yet,   I'm Rachel. I'm on the engineering   design systems team at Figma.   >> And I'm Megan. I'm on the club jewels   team at Figma.   We're your host for the mezzanine stage   today.


00:00:26
 We're excited for this last   session, but I know you guys are   thinking, how can there possibly be more   incredible talks?   >> Well, we're about to show you. Um, up   next we have Setu Adhav, who will   take us on a deep dive into the world of   AI Evals. He'll show us they're more   than just a raw technical tool. They can   actually better ground our work in user   experience. Please give it up for Setu.


00:01:05
  >> Hello everyone. My name is Setu Adhav.   So, before we get into the topic of AI   and Evals, I have a mini confession to   make to you all.   And that is over the last 5 years, I've   been cos playing as a researcher.   So, truth be told, I always thought I'd   be a neurosurgeon growing up.   But I quickly found out that I'm   terribly afraid of all blood and   needles.


00:01:28
 So,   I realized that that wouldn't be the   best career path for me.   And so, this led me to ultimately decide   to pivot away from healthcare into   computer science, where I thought I'd be   staying far away from medicine.   But, unfortunately for me, right before   my undergrad graduation, my father   suffered from a stroke.


00:01:49
  And I remember my world took a 180.   And I think a lot back to how I felt   that moment, the uncertainty, the fear,   and also the realizations of the   complexities of health care and the   patient recovery process.   When I reflect back, I think about how   that single moment really altered my   trajectory.   I decided to pivot back into health care   and I stayed as close as I could to   medicine and dedicated both my masters   and my dissertation on trying to figure   out how we can use artificial   intelligence to improve patient   outcomes.   And so it was from this experience that   I've held on to this deep belief that   families deserve access to high-quality   care through technology.   So very early on in my career, I helped   build one of the world's first   cyber-human systems for stroke   survivors, which you can see here on the   screen.   And at the time, the goal was simple.   Allow patients to receive high qual-   high-quality therapist feedback at home   using interactive apps and wearable   sensors.   And so in order to do this, we needed a


00:02:48
  pilot this with real stroke survivors.   And now, this brings us to John.   John was one of our first participants   at our study at Emory University.   John suffered from a mild stroke, which   left his left arm weak, and he joined   our study hoping for one thing.   A glimpse of what getting his mobility   back might feel like.


00:03:10
  And on the screen in front of him were   was one of the apps that I built.   It walked him through his rehab   exercises and gave him feedback on how   he was progressing.   And during our pilot at Emory   University, it kept telling him similar   things. He's getting better and his   movements are improving.   And John was thrilled about the type of   feedback he was getting.


00:03:29
  But behind him, a therapist was watching   the same screen and her face said   something completely different.   She saw what the system couldn't.   John was overcompensating.   He was extending his shoulders to make   up for his weak arm.   And a therapist catches that instantly,   but our system didn't.   Now, if she hadn't been in the room,   John could have practiced the wrong   patterns for months thinking he was   actually healing, which have actually   made his recovery process 10 times   harder.


00:03:58
  What was interesting was that our system   did exactly what we asked.   It measured movement. It tracked   progress.   It gave feedback.   But it still almost sent a patient down   the wrong path.   And because of that, I think and I   reflect, I never asked the one question   that truly mattered.   Did our definition of of good match the   therapist?   When we look back, we see that our model   was accurate.


00:04:21
 Technically, it passed all   of our test cases.   But it was also wrong.   And ever since that study, we ultimately   end up improving our system to   drastically match the expectations of   the therapist.   And I thought a lot about that gap   between what we initially built and   versus what John actually needed.   And today it makes me wonder,   how many AI products are out there right   now that look accurate, but aren't doing   what people actually need?   And how do we decide what AI should do,   not just what it can?   So, fast forward now a little over a   decade, and I'm still working on solving   that core problem.   Across my career from Virginia Tech to   Google to Meta and now Figma, that exact   same question keeps popping up in the   form of AI evals.   So, now I'll be honest with you all.   When I first heard the words AI evals, I   was generally confused and I thought it   wasn't for me.   It sounded like something that was   reserved only for machine learning


00:05:21
  scientists. And I know I'm not the only   one who has felt that way, because I   guarantee you there's been someone in   this room who has been in a product   meeting where engineers leaned forward   and said, "We need to improve our eval   coverage or our benchmark data   saturated." And you just nodded your   head.


00:05:36
  You didn't raise your hand. You didn't   ask what it meant. You just wrote it   down in your notebook so you could   secretly Google it later.   And then when you Google it later, it   didn't help. And you probably looked a   little bit like Michael Scott over here.   So now, if you've ever felt that way,   don't worry because by the end of this   talk, you're going to know exactly what   evals are, how to do them, and why   you're the best person in the room to   lead.


00:06:01
  Now, before we continue, I want us to   quickly do an exercise together.   Imagine you prompted your favorite AI   design tool to generate an output from   the text that you see here on the   screen.   So, create a homepage for a running   mobile app.   Now, imagine design X is your first   output.   Now, imagine design Y is your second   output.


00:06:26
  There are no right or wrong answers   here, but raise your hand if you think   design X is better.   Now, raise your hand if you think design   Y is better.   Look around the room.   We're split.   If I ask each of you to explain why you   voted the way you did, every single   person will give me a slightly different   answer.


00:06:45
  And that's because we're human.   Our unique backgrounds and life   experiences uh impacts how we perceive   quality.   In the past, we might have looked at   this room and said, "We have a problem.   Nobody agrees."   But in the world of AI development, that   disagreement isn't the problem. That   disagreement is the data.


00:07:03
  What we just did right there, that's the   foundational spark of an eval.   An eval simply means taking human   disagreement, distilling it to a shared   measurable criteria, and using that   criteria to systematically steer the   product's output.   That's it.   So, why does it feel so complicated   sometimes?   I think that's because there are two   myths that we've been telling ourselves   that aren't true.


00:07:24
  The first myth is that evals are   strictly an engineering problem.   We assume that because engineers build   the model, they must own the   measurement, and therefore the   definition of good.   But look what we just did.   The hard part wasn't just about   generating the output.   The hard part was also evaluating   whether the output was good and being   able to articulate why.


00:07:45
  So, now you might be thinking, "Okay, we   define what good is once and we're   done."   But, human expectations evolve.   What feels like magic today will feel   like a baseline requirement a month from   now.   And because the human context is always   constantly shifting, our definition of   good must shift with it.


00:08:02
  When we look at historically how we   build products, it went through the   process of ideate, visualize, build, and   ship.   And it worked because they were   deterministic.   However, with AI, that that   predictability has been shattered.   You can enter the exact same prompt   three times, and you're going to get   three different outputs.


00:08:21
  And so, because of this, our approach to   how we evaluate and measure quality   needs to shift.   Now, building products is an evolving   process to define what the product   should become, and how we can   continuously steer it in a direction   that we want.   Quality is no longer verified at the   end. Quality is directed throughout.


00:08:39
  We now become the orchestrators. Our job   sits between the model and the value   providers, people.   And along this non-linear journey, our   decisions, what to prioritize, what to   measure, and what the model needs to get   better at, directly determines what the   product becomes.   So now, how do we actually do this?   I want to show you someone who's worked   over who's worked over the last 20 years   closely resembles AI Evals.


00:09:01
 She just   never called it that.   >> I'm afraid until we're being with these   fabrics, I'll mash up tiny sensors that   monitor the baby's physical properties.   >> Oh lord, what what what is he What is he   doing?   >> What is Mozart, Robert? Can you blame   him? The important thing is that the   Soothantracker anticipated the change   and alerted you.


00:09:23
  >> Oh no, cookies. I got to get cookies.   >> We do not need cookies, as I learned   quite painfully last night. Any solution   involving cookies will inevitably result   in the demon baby.   >> Combustion imminent.   >> What does that mean?   >> Fire!   >> means fire, Robert.   >> Well, which suit has countermeasures? I   suggest you extinguish the baby's flames   before he trips the sprinkler system.


00:09:54
  >> So,   many of you have seen The Incredibles   and have seen Edna before.   But notice what she did when she was   building the suit and working with   Robert.   She didn't start with a spec, she   started with one question.   And that question was what does Jack   Jack need?   Then from this, she continuously built a   suit that was adaptable.


00:10:13
  She watched his movements, observed,   learned, and realized he had powers she   never anticipated and his powers were   always evolving.   But here's something that most people   miss about Edna. She wasn't just   observing Jack Jack, she was directing   the outcome.   Every time she learned something new   about his powers, she made a decision on   what what needs to improve next.


00:10:33
  The suit actually molded into his   behaviors. It became what she told it to   become.   Now, here's where it gets interesting.   Jack Jack isn't an AI model, but his   behavior is probabilistic, especially   when he's upset.   You can't predict what power you use,   you can't write a spec for it, but   somehow Edna was able to anticipate all   of this and steer the suit and him in   direction that she wanted.


00:10:57
  We followed that same process when we   think about how we evaluate successful   AI products.   We have to define intent, set success   criteria, measure, learn, and repeat.   And all of this happens continuously.   You become the one directing the   process.   So, where does this loop actually run?   It happens across three layers: human,   auto, and UX, which we have a unique   ability to influence.


00:11:22
  Remember earlier when none of us could   agree on which output was better?   That's because we never set the criteria   for what we defined as good.   Without that criteria, everyone is   guessing, which makes it very difficult   to track.   So now, here are three approaches that   we can take to steer the model towards   what actually provides value for people.


00:11:47
  Can you guys hear me now?   Cool.   So the first approach answers the   guessing problem head-on.   If everyone is guessing, the fix is to   write it down what good means and put it   into human hands.   That is a human eval.   You create the criteria and you turn it   into a rubric, and then you hand that   rubric over to expert graders, whose job   it is to look at the outputs and score   them.


00:12:09
  This is the moment where good stops   being an opinion and becomes   measurement.   Human eval takes a shared criteria into   numbers you can track, compare, and   improve.   The grader score now becomes the ground   truth for you and your team.   But human evals has a limitation.   Graders are expensive and grading takes   a lot of time.


00:12:29
 And so there's a limit to   how we can effectively scale this.   And so this brings us to our second   approach, which is auto evals, using AI   to grade AI.   You take the rubric, the ones you have   your graders calibrated on, and you   teach an LLM how to apply it.   So now you're no longer just scoring   dozens of outputs quickly, you're now   scoring thousands automatically.


00:12:51
  However, with auto evals, you're only as   good as the human graders it learns   from. So if your graders aren't   calibrated, you're no longer scaling   judgment, you're just scaling noise.   So now this brings us to UX evals, and   this is the third approach that aims to   solve the blind spots for both human and   auto evals.


00:13:07
  With human and auto evals, the graders   score the outputs in a vacuum, and so do   LLMs.   But the people who use AI products don't   live in a vacuum.   They bring their own workflows, their   contexts, and that context isn't always   captured in human and auto evals. And   this is where UX evals aims to fix that.


00:13:24
  You put the product in front of real   users and watch them use it in their   natural context to see how you can   improve the model.   Now, this might sound a lot like   traditional research and on the surface   it is, but the core distinction is the   gap it closes to how we actually improve   model quality.   The signal you get from real users feeds   directly into model improvements.


00:13:45
  And now, when it comes to understanding   these three layers and actually helping   improve model quality,   who has spent years tracking and   emerging uh user needs over time?   Who has spent their entire careers   defining objective quality standards and   translating human behavior into product   signals?   Researchers and designers.


00:14:04
  Understanding user needs, defining what   quality looks like, and measuring   whether you're hitting the mark, this   isn't engineering bottleneck. This is   core research and design.   We aren't learning a new craft, we're   simply applying our existing skill set   into a new technical frontier.   And so, the question now becomes, how do   we take our specific expertise   and use it to shape the foundational   model itself?   When you see, evaluating AI products   doesn't require new skills, it's just   renaming the ones we already have.   So, expertise such as defining the North   Star, understanding disagreement,   surfacing user needs, and synthesizing   findings becomes writing the success   rubric or calibrating graders, defining   the eval sets or triaging failure modes   is the exact same craft, it's just now   applied at the model layer.   So, now I want to walk us through one   full cycle of this loop at Figma from   start to finish.   So, the loop starts here with intent.   Before you measure anything, you have to   decide what the model actually needs to


00:15:04
  be good at and just as important, where   to focus on first. You can't improve   everything at once.   And at Figma, this is where I spent a   lot of my early efforts where I helped   the team prioritize which use cases our   agent needed to be good at and really   nailing our eval sets.   And so now, once you know what you're   aiming for, you have to define what good   means in a way that other people can   apply the same way you would.


00:15:27
  And this is where I wrote our initial   rubric and calibrated our graders.   And calibration is the keyword here.   It's not enough to just write a rubric   down, you have to get your graders   aligned so they're scoring the same   output consistently.   And this is what turns success from one   person's opinion into a shared language,   something that's consistent, and   something that you can actually measure.


00:15:46
  And then once you can measure,   measurement looks different depending on   the direction you want to the product.   And so for one example from human evals,   be able to measure the content quality   or response quality or prompt success.   You analyze these results and how well   they're performing across each of these   different dimensions, and you actively   surface those gaps you're noticing to   the engineering team to prioritize.


00:16:07
  And this is where it all starts to pay   off, where measurements turns into   improvement.   Every test that we've surfaced uh showed   us something different, specifically the   high frequency and high severity failure   modes, the things that broke often and   the things that were broke badly.   Those went straight to our engineers'   hands for concrete signals for what we   needed to fix.


00:16:26
  And as they made those fixes, we saw the   scores go up, and that's when the   flywheel begins to happen.   And over time, we start to see the   impact of this work reflected and   noticed by leadership.   This is our chief design officer   reacting to the trajectory of our   improvements.   And what I noticed very on early on in   my time at Figma is how much our direct   recommendations and quality fixes are   highlighted to our exact team.


00:16:49
  And that's the shift I want us to really   start to prioritize.   How we can shift from influencing the   product indirectly to shaping it   strategically and directly through model   quality.   And so through this work, I've started   to realize that we have far more power   to shape AI than we think.


00:17:04
 We have four   distinct levers to influence how a model   behaves, and the first is through system   prompts.   You shape how the model behaves in   production, its tone, its guardrails,   what it will and won't do.   The second is through eval design. When   you When you design the eval, you   actually design what good means.


00:17:23
 And   everything with the model measured is   closed against the bar you set. So,   whoever defines the rubric defines the   target.   And the third is through data sets.   You decide what the model learns from,   what it gets judged on, and how you make   sure it reflects on what actually users   need, not just what is easy to collect.


00:17:42
  And the fourth is through capabilities.   You determine what the model can   actually do for people by shaping the   tools and the context that it's given.   Four levers which we're uniquely   positioned to own.   So, now I want to leave you all with   this.   We talk a lot about how AI is changing   the world. And it is.


00:17:57
 But AI doesn't   know where it's going. It only knows   where we've been.   Someone has to point it forward, and   that someone is us.   We spend our careers sitting between   what exist and what should exist.   Let's be the architects of what come   what comes next.   Be sure to own the loop.   Thank you.

