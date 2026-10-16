
00:00:12
Our next speaker will be Craig Lebenz, a   developer relations engineer at Google.   Craig's been exploring the advantages   and challenges of using AI not just to   generate content, but to actually   generate the user interface itself. Um,   please give a warm welcome to Craig.   >> [clears throat]   >> Hello everyone, and welcome to Design   for the Future of Apps.


00:00:47
 As they said, my   name is Craig Lebenz, and I've been   working in open source at Google for the   last 7 years.   And specifically within open source,   I've been working on a thing called   Flutter, which is a multi-platform UI   toolkit by Google.   But don't worry, we give away Flutter   for free, so you have not accidentally   stumbled your way into a time-share   sales pitch.


00:01:10
  But it turns out that   Flutter is not the only thing that the   Flutter team gives away for free.   The other thing that we give away is   coffee.   So this year brain scheme was called Gen   Latte, and I personally spent my   spring building out this demo. And we   stood it up twice, once at Google's big   Cloud event in Las Vegas, Google Cloud   Next, and then again at Google I/O in   Mountain View just this past May.


00:01:39
  And Gen Latte's idea is pretty simple.   We wanted users to be able to work with   Gemini and Nano Banana to create an   image of their personal happy place. And   then   world-class baristas would make a very   real latte and print that image of their   happy place on top of the coffee using   edible ink printers.


00:01:59
 So, here is   somebody's   happy place   adorably with their dog probably on a   hike or some such. And here was my happy   place at the IO version of this   celebrating what at that time was a   margarita. So, you could see where my   head was at after a long day at the   conference.   Now, Gen Latte was so named not just   because it had generative AI which of   course it did.


00:02:27
 It was contractually   obligated to. It's 2026.   But also because it had another thing in   it all together called Gen UI standing   for generative user interface.   But before we can understand how Gen UI   factored into Gen Latte, we must first   understand Gen Latte itself. So, the   ordering flow was as follows. You'd   start it out, you'd give it your name,   you configure the drink, you tell the   baristas how you want this thing to   taste, and then you enter your happy   place.


00:02:57
  And this would just be whatever the   first thing that came to mind was. A lot   of people would put, you know, on a hike   with my family.   And then Nano Banana would get to work   and it would create a batch of images   representing that place. But if even the   best image out of that batch didn't   quite match what you were imagining, you   could continue the adventure and answer   some more questions that had been   authored by Gemini in advance.


00:03:17
 So, for   example, if you said your happy place   was at the zoo with your family, Gemini   might say, "Marat, what   what animal exhibit are you at?" And   "How big is your family?" And "What time   of day is it?" and whatnot. And then   you'd get another batch of images and   you could continue.   And this is where Gen UI came in to play   because that you can see that these   questions do not all require the same   user interface to help users answer   them.


00:03:48
 There's multiple choice questions   here. There's also different kinds of   sliders. There were open-ended questions   that had you know, were best served by   just a text box. So, uh   GenUI was how we met each question uh   you know,   helped users answer each question.   And uh this is all kind of getting a   little abstract and might feel abstract.


00:04:12
  So, let's zoom in a little bit,   especially so we can get to the concerns   that are relevant for designers.   So, all of this is pointing to the   question, "Well, what is GenUI?"   And most people think of AI these days   as either coding assistants, obviously   that's extraordinarily popular. It could   also be an agent running autonomously on   your laptop and opening up bank accounts   in your name that you did not ask for.


00:04:35
  Or it could be the chat interfaces where   we seek low-grade therapy from uh   different LLMs. But at Google, we   started to wonder, "Well, what if these   agents could respond to users' needs not   just with walls of text that nobody   wants to read, but instead rich,   ephemeral user interfaces?" And so,   after months of thinking and the   scratching of many chins, this idea   started to coalesce and we call it   GenUI.


00:05:03
  And there's even a protocol for it   called A2UI, standing for agent-to-user   interface. And that's its logo there on   the right. Now, this is mercifully not a   technical tour of that protocol, but   instead an exploration of the kinds of   questions that come out of following   this paradigm.


00:05:22
 So, it's an invitation to   all of you to ponder those questions   with us because engineers have opened a   real can of worms with this and we're   going to need designers to help us make   sense of it.   And these questions touch every aspect   of app development, ranging from your   design systems to how you prototype   early versions of your app, to basic UX   concerns around consistency and   affordances, to even your server bill   every time a user launches your app   because as the world has found out in   the last few months, tokens are actually   not free.   And now, if you would like to explore   this protocol that I'm going to gloss   right over, then you can head to   a2ui.org and have yourself a read.   So,   is the future of apps GenUI? Well,   maybe.   I think it really depends on the app   itself. So, it could be true that it's   the future for some apps.   But, as I was building Gen Latte this


00:06:22
  spring, I started to realize that GenUI   is not just a boolean that your app   either has or doesn't have. Instead,   it's much more of a spectrum with a dial   that you can tune up and down. And as   you move up and down that spectrum, you   really transform your app.   So, to grasp this spectrum, I'm going to   propose to us a four-tier system of   GenUI adoption.


00:06:47
 You could of course   imagine a totally different number of   tiers. There's a continuum between each   of these tiers.   So, this is by no means an official   list, but it helps me reason about where   we're going in 2026 and beyond.   So first, to level set all the way on   the left, well, I guess this is your   all's left, is level zero with zero   GenUI and completely deterministic user   interfaces.


00:07:12
 And I'm calling this   one-sided UI because   all of your UI logic probably lives on   the server, think like Wikipedia, or in   the client, that would be most web apps   these days, or presumably, though I've   never seen the source code, even the   Figma design client.   And this category covers the vast   majority of apps ever made.   It also covers some surprising   interfaces like earlier versions of the   web interfaces to talk to Gemini,   ChatGPT, or Claude.


00:07:44
 So, the key insight   here is that even though an LLM is   providing non-deterministic answers to   our deepest questions about life, the   code itself, which receives that answer   and shows it to the user, is   deterministic.   So, code and UI   UI code and content are different   things.   So, to advance to level one, which I'm   calling full stack UI,   what you would probably do is mix and   match where the responsibilities fall   between your client and your server.


00:08:22
 And   I think generally these days how that   tends to play out is that the server   fills in some blanks on what is   otherwise a primarily client-driven UI.   I think a lot of news websites live in   this space these days where some simple   front-end code how to like put all the   paragraphs of the article into some P   tags and show it to the user, but the   server might have final say on where ads   get placed or how other related news   stories are represented.


00:08:51
 Also, dynamic   and flexible AB testing frameworks are   really well suited by this architecture.   But level zero and level one are   siblings in my mind because they share   this attribute of being completely   deterministic,   which is a little bit of a spoiler for   how you move on to level two,   which I'm elegantly calling AI-driven,   server-driven UI, which really begs the   question,   who's driving this thing?   But what you do at this level is you   start to sprinkle in some AI magic into   the server part of your already split UI   responsibilities.   So, you've got ChatGPT, Claude, Gemini,   etc. helping you work out what to show   the user in real time. And to me, this   is when you actually finally start to   enter   genu I land because your UI is no longer   deterministic.   And Gen Latte, the coffee disseminating


00:09:51
  apparatus that I've been droning on   about, was a level two UI because these   questions were dreamed up on the server   by Gemini and then they were sent down   to the client as UI directives.   Now, level two questions ask or sorry,   level two UIs ask some very interesting   questions of us that are going to force   designers and developers to collaborate.


00:10:14
  So, for example, Gen Latte has this   catalog of card widgets which know how   to show users the questions that they   would need to tweak the images that they   were looking at. But when I was writing   that widget, I didn't know how long the   question was going to be. Also didn't   know what aspect ratio I was going to be   rendering in.


00:10:32
 Obviously responsive   components and overflowing text are   nothing new, but it's a little weirder   like you expect to see that kind of   stuff in maybe the review body or like a   comment body.   It's a little weirder if what's supposed   to be the page's H1 or H2 i- ends in an   ellipses. That would make me think,   "Wow, this is a really broken UI.


00:10:54
"   Another question that I had to deal with   was just not knowing for the multiple   choice questions, for example, how many   options Gemini was going to give me. And   sometimes it would put one word in each   of the options like in this screenshot   and other times it'd be like, "Here,   have a whole sentence."   So, how do we fit all of this dynamic   content into the available space that we   have? Well, for Gen Latte, I had to lay   out on a sort of like shadow canvas in   advance all the text and measure every   single pixel that was uh consumed by   those letters. And for the buttons of   multiple choice questions, I even had to   count the padding within the button and   the border thickness itself and figure   out when they were going to line wrap   and then I would tweak the font sizes   until everything fit. And that worked in   so far as it got rid of the surprising   ellipses, but it came at great cost it   came at the cost of great complexity   within that component and also sometimes   I would have surprisingly sized text. So


00:11:53
  did I create the best possible UX for   users of this demo?   I'm personally invested in thinking so   because I've already subjected thousands   of people to it over several events, but   in the future I would love to work with   more designers on questions of that   category.   Now,   to get to level three, there's a couple   more dials that you need to turn and   we're going to talk about those, but if   you make it all the way to the end and   you become a Gen UI maximalist, things   ultimately end up becoming something of   an AI take the wheel situation.   And there's two primary differences   between level two and level three.   The first one is that the further you go   toward level three, the more control   over and and the more freedom over your   UI you are probably delegating to your   AI agent.   Uh so you might literally say, here's   our design system, here's our grid rules   and here's the user and what we think


00:12:52
  they're trying to do, go crazy.   And you can see how that's a   categorically different beast than a   full level two situation where the AI   has just kind of targeted control over a   limited space of your user interface.   You might also, this is the second   thing, you might also as you go further   toward level three, ultimately end up   delegating the complete application   state to uh the AI agent and   the uh what this can mean is that when   you click a button, when your user   clicks a button in your interface, there   might not be any local code that you   call it that you run immediately to   favorite the item or submit the form or   whatever that button does. No, instead,   a couple hundred milliseconds ago, when   the AI agent decided that this UI needed   a button there, it already paired it   with a server-side action, probably like   a tool call, if you're familiar with


00:13:51
  those. And then you the your application   on the front end just says, "Well, hello   again, Mr. or Mrs. AI man.   Uh remember that button that you gave me   in the UI? Well, the user clicked it, so   have fun." And then it's the AI's job to   figure out how this application state   changes and what happens next.


00:14:06
 Maybe   that's just a local UI update or a full   navigation event.   So,   I've been going on uh about again Gen   Latte, but the Flutter team this spring   also made a level three demo. So, this   is called Hatcha. And it's a party   planning app where Gemini plays a sort   of improvised game of 20 questions with   users until it acquires all the   information it needs to fully uh have a   pitch deck for this event that you want   to throw.


00:14:39
 And both aspects of   the uh distinct both distinct aspects of   level three UIs were in play here. Both   the full delegation of UI composition   and the delegation of the AI's internal   state. Because how could I, as someone   working on Hatcha in advance, know   exactly what would be required to   represent the event that you want to   throw?   Uh   you know, you're going to be asked 20   unpredictable questions to figure out   what this is going to look like.


00:15:09
  So, as the Hatcha UI plays here,   just like level two had its own   questions that it forced upon us, level   three user interfaces or Gen UI   interfaces also ask some hard questions   of designers and developers.   So, uh   and I think these primarily orbit around   kind of information hierarchy and UX   consistency.


00:15:36
  So, to explore that some more,   you can think about the level of UI   granularity that you give to your AI   agent. So, on the left there is a   coarse-grained catalog where you're   passing the AI kind of high-level,   self-aware, intelligent UI components.   And that is more of a level two style,   and that creates that has the strength   of affording your users more UX   consistency, more predictability, but of   course at the cost of unbounded   creativity in what UIs you can show.


00:16:15
  And the reason, of course, that you get   that higher uh consistency and   predictability is that those components   can bake into themselves knowledge of   what's going on. They can have error and   success affordances. They can show   progress bars. They can know how to lay   out their children amidst surprising   constraints.


00:16:33
 They can know that things   need to be able to scroll potentially.   And then, if you flip all of those   details, you see a finer-grained widget   catalog. So, this would be where you,   like I was saying earlier, give your AI   agent just your design system. These are   our buttons. This is how we render text.   These are our containers.


00:16:50
 You know, this   is uh this is a list. This is a grid.   Like, have fun.   And that opens up a really wide range of   things that your app can do that you   never even predicted in advance, but of   course at the cost of consistency and   predictability.   Now,   level three GenUI is not all craziness   with no upside.


00:17:15
 Imagine a scenario where   you keep some tallies of user actions   that people take in your app amidst all   of the actions that they could have   taken. And then you bundle that   information into a request that you send   to an LLM when it's time to generate a   new interface for a user. Well, it could   notice that some poor user keeps   following a journey that stretches   through four screens.


00:17:39
 And then it could   compose on the fly a new screen   that just has everything that person   needs. And now if that user is still   successful in their quest here, you   could actually cache that output of the   A2UI protocol and save on the token cost   the next time you that user shows up.   So, zooming out a little bit,   regardless of your GenUI tier, I think   you can think of each screen in your app   as a touch point where your client and   your server come together and say,   "Okay, we've got this user here.


00:18:18
  What are they trying to do? What should   we show them? Where are they within this   page? Okay, they just took an action.   Now what do we do?" And the more of   those questions that you delegate to an   AI agent at runtime,   the deeper you've gone into GenUI land.   So, GenUI is here, which means that if   GenUI is the future of some apps, it   would follow that the future of some   apps is also here.


00:18:45
  Now, the chaos of these   non-deterministic UIs is both exciting   and kind of scary. Right now in its   final form, by which I mean level three   on the spectrum that I just totally made   up,   this this implies turning almost   everything into a network request. And   they're slower than old world network   requests we're used to cuz an LLM has to   think about stuff.


00:19:05
 And you have to pay   the tokens for all of those things.   But those downsides are are going to   last forever   because Gemini 4, Google's premier   on-device model, can already drive   genuine experiences on a powerful   laptop. So, unless something plateaus   really soon, that's going to be running   comfortably on phones in just a few   years.


00:19:24
 And that is going to mitigate a   lot of those downsides and possibly open   up genuine to becoming a much more   realistic and appropriate option for a   wider array of apps. And who knows?   Maybe one day you will be working on   just such an app.   Thanks so much.

