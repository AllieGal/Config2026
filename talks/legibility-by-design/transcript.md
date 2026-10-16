
00:00:12
Hi everyone. My name is Ryan Powell, and   I lead design at Waymo.   Years ago, I was riding my bike through   this intersection in Chicago when a car   ran a red light and hit me.   So, I survived, obviously, but that   moment stayed with me, and it redefined   how I think about our streets.   Every 26 seconds, someone else's story   doesn't end as lucky as mine.


00:00:38
  So, every 26 seconds, that's how often a   life is lost on our roads.   When we talk about building autonomous   vehicles at Waymo, we aren't designing a   cool tech novelty. So, recently, the   medical community published an open   letter calling out America's road deaths   for what they truly are, an ongoing   public health crisis.


00:01:02
  And for us at Waymo, bringing this   technology to as many people and places   as possible is a public health   imperative.   So, back in 2009,   uh Waymo started out as Google's   self-driving car project, and for the   longest time, it was viewed by the   public as an eternal experiment.   But today, I think we should officially   retire that notion.


00:01:28
  By a show of hands, how many of you have   taken a ride in a Waymo?   That's incredible. So, I think we can   all agree that autonomous vehicles are   becoming a daily reality.   >> [applause]   >> So, Waymo has driven over 200 million   rider-only miles. We've completed more   than 20 million passenger trips, and   every week, we are serving more than   half a million rides across 11 cities in   the US.


00:01:58
 And at the moment, we're   currently preparing for our our   international expansion into the streets   of London and Tokyo.   So, behind every car in every city,   there's a massive operational backbone   that you don't see. So, in addition to   the rider facing work that I'm going to   share here today, we also design the   data-rich interfaces that empower our   operations team.


00:02:22
 So, from our mission   control dashboards that monitor fleet   health um in real-time to the apps that   our depot techs use to charge or   maintain our fleet. So, we're also   designing the internal tools needed to   bring this technology to more people and   places.   So, that's all to say, this is no longer   a pilot.


00:02:45
 People are depending on us to   get from point A to point B, and our   safety data is very convincing. So,   compared to human drivers, our vehicles   have seen a 92% reduction in serious   injury crashes.   But, here's the design problem. Safety   is statistical, but trust is emotional.   Our riders don't think in terms of   statistics.


00:03:10
 They want to get from point   A to point B in a very convenient and   comfortable fashion. And so, if we don't   understand their needs in an autonomous   context, the underlying technology,   something doesn't matter.   So, let's rewind just for a second   because getting here required a massive   product pit uh pivots, and that was   largely driven by user research.


00:03:34
  Back in 2012, we were testing a Lexus   fleet, and it was equipped with early   driver assist features. It's very much   like what you see today um on vehicles   that we have with where there are driver   assist features. And it was a driving   system that still required the human to   take over at a moment's notice.


00:03:52
  So, our researchers uncovered something   unsettling.   The moment the technology worked   reasonably well,   users almost immediately over-trusted   it.   So, testers were supposed to be   monitoring the system, and again, they   were supposed to be ready to take over   at a moment's notice. But, as you can   see in this video, they were doing all   sorts of things at highway speeds.


00:04:14
  They're texting, they're putting on   makeup here, and we even had some people   completely nod off as again, as they   were on the freeway and speeding along.   So, we've completely abandoned at that   at that moment in time, we did we drew a   line in the sand, and we said, "Okay,   we're going to not pursue this idea of   going with driver assist as a stepping   stone to full autonomy.


00:04:35
 We're going to   be go all in on level four autonomy,   which is where the passenger never has   to intervene."   So, we went fully autonomous in late   2019 in Phoenix, and we spent a lot of   time with our early riders back then.   So, they were tech enthusiasts. They   loved the novelty. If the car took a   slightly weird route, or it paused   awkwardly, they forgave the friction   because they wanted to be part of the   future.


00:05:05
  But, as we expand uh from our early   adopter base, our new mainstream riders,   they care less about the novelty of   self-driving.   They have a low tolerance for   self-driving quirks. And so, I know a   lot of you are out there and dealing   with the same friction right now. You've   built this incredible product.


00:05:21
 Your   early adopters love it, but now you have   to scale past them to the pragmatists,   so the mainstream. These are users who   don't care how cool the underlying tech   is, and they just want to it's a work   flawlessly.   And so, to to design for them, you have   to stop designing to educate or to   impress, and you have to start designing   for trust.


00:05:45
  So, how did we do that? Well, we spent a   lot of time in the passenger seat   observing the nuanced dialogue that's   often unspoken that defines a   human-driven ride. So, much of that   communication is direct. You might ask   the driver, "Hey, you know, which route   are you taking?" Or, "The light's green,   you know, why aren't you moving?"   Um but, the real sophistication lies in   the non-verbal cues.


00:06:10
  So, consider the scenario that you see   here in this photograph. You're in the   backseat, the car begins to slow down.   Instinctively, you look up and you see   two things. You see the jogger ahead   outside of the windshield there, but you   also notice the driver's head turn   slightly toward them.


00:06:25
 So, in that split   second, you haven't just received   information, you've built a shared   understanding. You know why the car   slowed down, and you feel secure because   of it. And that insights became a   cornerstone for our design philosophy.   So, when you remove the human driver,   you don't just remove an operator, you   create a massive communication vacuum.


00:06:48
  And so, our jobs as designers has been   to design a proxy for that missing   dialogue. So, we are essentially   building a new language of trust.   So, early on, a lot of our riders asked,   "What can our cars see?"   Well, there's a ton that our car, you   know, that our cars see and that we   could communicate.


00:07:07
 Some of you have   probably seen a video like this. It's   what our engineers use for development.   But, this raw output is just too dense   and demands too much attention for   people that are just trying to get from   point A to point B.   So, as designers, we spend a lot of our   time curating exactly what we show in   our UI.   And we want our riders to have a sense   for just how much the vehicle can see   and understand without overwhelming   them.


00:07:37
  So, we've learned that building trust   requires sort of a ruthless uh curation   over complexity.   So, let's take a closer look at the   passenger UI that you see during your   ride.   We want to Again, we want to show you as   as everything that the car can see and   how sophisticated this technology is,   and we want to be able to explain its   behavior when that makes sense.


00:07:58
 So, the   in-car UI has to also assure um people   and and not overwhelm them at the same   time, and it has to do so whether if   it's their first trip or their 100th   trip.   So, let's zoom in then to the 3D uh part   of our UI, and here you can uh see that   we show a road surface. It's flattened   and it's grounded.


00:08:18
 The features of the   road like crosswalks and street markings   are things that we highlight here.   The car's trajectory is a predictable   green path,   and then nearby vehicles are rendered as   simple, clean, sort of stable 3D   geometry.   When it comes to pedestrians, they have   a crisp sort of light blue glow   underneath them, and cyclists have a   green underlay.


00:08:43
  And when with pedestrians and cyclists,   we got feedback early on that abstract   icons felt too detached. So, instead, we   take a hybrid approach here. We layer   the real-time laser points over the   figures, so you can actually see the   biological motion of their arms and legs   moving, and this subtle design language   communicates an incredibly complex   message.


00:09:04
 It tells the rider, the car   doesn't just see that object, it knows   what that object is, and it knows how it   behaves.   So, occasionally our riders might glance   up, they might wonder where they're at.   So, in addition to showing what the car   can see, we also pull in buildings to   provide some geographical context, but   because they're less important to   understanding what the car can see, we   sort of dim those down so that they   don't compete with the more important   elements in the scene, namely the the   nearby cars and pedestrians.   So, when it comes to building trust, um   sometimes the most valuable pixels are   on the screens are the most ordinary   ones. One of the highest yield design   decisions that we ever made was   rendering orange traffic cones on the   screen. I'm not kidding.   >> [laughter]   >> Construction zones are sometimes chaotic   and stressful. And when a rider looks   out the window and they see a row of   orange cones and they see those exact


00:10:04
  cones rendered in real time on their   screen, they instantly relax. We hear   this time and time again in the user   research that we do. So, that simple   detail in our UI says, "I see that   barrier. I understand the detour, and   I've got this."   So, in addition to the 3D scene where we   show what the car sees, we also have the   status layer that sits on top.


00:10:25
 So, this   is where we can be more direct when we   need to be. So, it's essentially the   voice of the driver and it communicates   things like the trip progress and what   the car is doing. We might be slowing   down in a school zone, and so again,   you're going to feel that. You're going   to look up, kind of wonder what's going   on, and you'll see that on the screen in   the status layer.


00:10:44
 Um in this case, we're   letting you know that we're waiting for   the intersection to clear before we we   make this right-hand turn.   So, we've also invested a lot in sound   design.   So, when you design for trust in a   deeply personal space like a vehicle,   you quickly realize how important it is   to respect that space.   So, independently, these are nice   sounds.


00:11:09
  But when we overuse sound, it's easy to   hear how it can quickly become annoying.   So, remember, in cars, alerts are mostly   around for drivers who need to react.   But our cars are filled exclusively with   passengers, and passengers don't need to   manage the vehicle. We just want them to   sit back and chill.


00:11:36
  So, to achieve sound harmony, we lean   into psychoacoustics. We've anchored our   entire vehicle soundscape around the   musical key of E.   So, in psychoacoustics, the key of E is   uniquely associated with feelings of joy   and clarity. It feels bright and and   inherently stable.   And we use sound design as as a systemic   hierarchy.


00:12:01
 So, for instance, when you   open the door for the first time,   you're greeted by a soft ambient   harmonic soundtrack in the key of E. Our   team affectionately calls this spa   music. Early on, one of the insights   that we learned about was that it was   kind of eerie when you got into a a   self-driving car and it was completely   silent.


00:12:22
  >> [music]   >> And so, this soundtrack is meant to   transition you from the outside world   into one of our vehicles.   So, from there, every functional   notification is musically paired. So,   the chime to start your ride is a rising   scale.   >> [music]   >> Heading to Dolores Park.   >> So, that rising scale denotes the onset   of an adventure or the start of your   trip.


00:12:51
  And then when you get to your   destination, the arrival chime is a   falling scale.   >> You're here. Please make sure it's clear   before exiting.   >> So, that signals a gentle return or the   fact that you've arrived at your   destination.   So, if a situation requires slightly   more attention, like closing the door,   the notification shifts deliberately   away from the base key to create a mild   polite tension that draws your eye to   the screen.


00:13:24
  >> [music]   >> So, if you left the door open and we   were trying to get you to close it,   you'd hear that sound, you'd look up at   the screen, and you'd see a notification   there asking you to close the door. The   rest of the time, you know, we want you   to lean back and enjoy the rides. We're   very judicious about how we use those   notifications.


00:13:44
  So, so far I've talked a lot about the   rider experience inside our cars,   but our design challenge doesn't end at   the car window.   It extends into the living, breathing   machinery of a city, where we design for   the safety of everyone sharing the   street.   In 2021, we graduated from the wide,   sort of predictable roads of Phoenix   into the dense urban environment of San   Francisco.


00:14:12
  And that's when we started dealing with   15 times more pedestrians in the   neighborhoods   and 50 times more pedestrians in the   financial district. So, we had to learn   how to talk to the world outside the   car,   what our industry calls other road   users.   So, every day on a city street, humans   engage in these micro interactions.


00:14:31
 Who   goes first? Do I cross now? Do they see   me? In a traditional car, you resolve   that ambiguity through body language.   So, if a driver's wheels are turned to   the right, but their head is turned to   to the left to check traffic, a   pedestrian instantly reads that posture   and thinks, "Okay, they're not looking   at me. I better wait.


00:14:52
"   But when you remove the human driver,   you erase the eye contact and the body   language, and so we had to invent a   design proxy for those human cues.   So, in robotics and animation, this is   often achieved by motion. So, movement   enables the inference of intentions.   So, we do this at four-way stops.


00:15:14
 It's a   good example. So, the vehicle deliberate   deliberately nudges forward to signal   that, you know, it plans to go next. It   plans to take our turn. So, this little   nudge is a way that we can kind of   communicate using motion about in terms   of what we're about ready to do.   But, in a dense urban environment like   San Francisco, there are a lot of times   where our cars are completely   stationary.


00:15:40
 So, we might be yielding to   a lot of pedestrians or something that's   happening on the street, and so we stop.   And how do you tell if the Waymo sees   you and it's okay to cross when the   vehicle is not in motion?   So, to solve for this, we turn to our   lidar dome on top of the vehicles, which   doubles as a 360°   external display.   Now, our first use case was purely   operational.


00:16:08
  It displays the rider's initials so they   can spot their specific Waymo when   there's more than one. And so, we asked   ourselves, how might we leverage uh this   to increase the legibility of the car's   intent?   And so, we spent a lot of time, we did a   lot of iterations, a lot of user   research into figuring out what makes   for a good signal.


00:16:30
  And there's a lot of research out there   as well in into this, and it boils down   into three principles.   A A good signal needs to be legible. It   needs to be easy to learn, and it needs   to be glanceable.   And so, when a Waymo is at a stop sign   like you see here with pedestrians that   are wondering if it's okay to cross,   the external display emits a soft,   forward-facing visual pulse that   communicates, "I see you. Go ahead.


00:16:55
"   Now, simultaneously, it projects a   targeted signal backwards to the human   drivers that are behind us. So, it's   clearly broadcasting that we're stopped   to allow pedestrians to cross in front   of us. So, we aren't just communicating   with the person in front of us, we are   also closing the loop for the entire   ecosystem.


00:17:20
  And once you realize your technology has   the capacity to protect the broader   ecosystem, you start to look for other   blind spots where design can make things   smoother.   So, consider dooring. Those unfortunate   cases where someone opens a car door   directly into the path of an oncoming   cyclist or scooter.


00:17:40
  Because our vehicles can see   360° around the vehicle, we can actually   solve this.   So, we've built a safety buffer right   into our exit flow.   So, if a bike or scooter is approaching   from behind, the cabin alerts you with a   directional chime, a clear graphic on   the screen, and a gentle audio reminder   to look before you exit.


00:18:04
  >> You're here. Please make sure it's clear   before exiting.   Scooter approaching.   >> So, in this moment, the interface isn't   just serving the rider, it's actively   keeping the person outside safe as well.   So, when you design for safety and   predictability, something really nice   begins to happen.


00:18:24
 Trust leads to more   trust. In Phoenix, not so long ago, we   launched Waymo teen accounts for riders   between the ages of 14 and 17. So, as   you can imagine, putting a teenager into   a car with an empty driver seat is a   massive responsibility.   To support that level of trust, our use   user experience had to solve for two   users at once.


00:18:47
  For the teen, we designed for freedom   and a stranger-free environment.   And for the parent, we designed for   reassurance, including real-time   location tracking and an easy connection   to rider support during their teen's   trips.   And here, design became less about the   user interface and more about creating a   silent, trusted partner for busy   families.


00:19:12
  So, we've built a lot of trust, and we   find that once people understand and   trust the car, they inherently want to   converse with it. And this is at the   heart of where we want to go next. In a   human-driven car, if you see it's   starting to rain, you don't open the app   and drag the pin on the map, you know,   to be dropped off, you know, to a spot   maybe is closer to shelter.


00:19:30
 You just say   to the driver, "Hey, can you pull up in   front of the red car?"   And so, imagine doing that here with   your Waymo. If you want to say the same   thing, "Hey, just as natural as as   telling that human driver, pull up in   front of the red car." And in the   future, we'd like to bring that exact   natural conversational ease to the   autonomous to autonomous transit.


00:19:54
  So, when UX achieves perfect legibility,   it becomes invisible and conversational,   and dare I say, more human. You stop   watching the steering wheel spinning on   its own. You stop checking the the   orange cones on the passenger screen,   and you just relax.   We realize that the true luxury of this   technology isn't the AI itself.


00:20:13
 It's the   freedom it returns to us.   The freedom to take a nap or to call   your mom, or become in being completely   secure in the knowledge that the journey   is handled.   And so, as you leave Config today, I   want to ask you,   what are your empty driver's seats in   your user journeys? What are moments   where users might be waiting for a   signal of intent?   What are the orange cones that tell   them, "You've got this?"   And in what ways can you speak in the   musical key of E?   You don't have to build autonomous   vehicles to take a page from this   playbook.   Whatever you're building, stop designing   to educate your users on features,   and start designing to earn their trust.   Thank you very much.

