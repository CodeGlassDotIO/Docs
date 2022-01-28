---
title:  "Hello world, it has been a long road!"
date:   2022-01-03 17:32:21
categories: CodeGlass Blog
badges:
---

# It has been a long road

I want to welcome CodeGlass to the world with the story of how it came to be.

It all started as my university graduation project that I got to do with the HoloLens (generation 1) and was asked to make something that would help developers by using the HoloLens. <br/>
Then, I was already working at the company where I was doing my graduation project and was debugging a program that was not well maintained and walking through a long and complicated call stack and ran out of screenspace fast.

Then I imagined being able to render the call stack of a running program on the HoloLens as it would show me how the application worked, and I was not limited by screen space but the space around me. 

So development started on what would, in the end, grow into CodeGlass began early 2018.
I created a data collection [profiler](../_docs/features/CodeGlassProfilers.md) that would collect data from Visual Studio, creating a Unity (Game Engine) project as [client](../_docs/features/CodeGlassClient.md) to run on the HoloLens and making a [hub](../_docs/features/CodeGlassHub.md) as the hololens and visual studio would be 2 different machines. 

In the middle of 2018, I graduated with a working prototype that could render 100 calls per second and was pretty happy with this "gimmick."<br/>
And this was what CodeGlass was supposed to be; a "gimmick" that rendered the call stack of a running application. <br/>

However, it did not end up this way.

Instead of getting employed full-time, I was offered a 24 hours contract due to financial trouble at the company I worked at.
I agreed with it as I could use the other hours to finish my project and release it to the public.

Looking back at that period, I notice that it has been a waste of time; the 24 hours were spread over five days, preventing me from focusing on the project and making no real progress. <br/>
I did learn better methods to improve it, but again, I did not have time to commit to those new directions.

So early 2019, I decided to take half a year of unpaid leave to focus on the project entirely and its release; I had enough saved up to support the development.

Together with two friends who were also enthusiastic about my idea, we implemented those methods and developed two different profiler prototypes.
With these new profilers, we would reach ~200.000 calls a second, a 200x performance gain, and many more statistics we could use in CodeGlass to help developers.

Of course, this also did not come without its problems.
- I did not build the hub to handle that kind of load.
- I  did not build the unity client to render that kind of load.
- We managed to push our network card to the limit of 1000 Mbps
- I did not build the hub and client to handle two types of runtimes.
- And many more.

We managed to fix most of them, but after a while, I was again on my own tackling this problem and extended my unpaid leave for another half year.
And while we made it multi-runtime compatible, I decided to focus on our .Net Profiler for now.

One of these problems, where a lot of time went into, was facing that it was tough to use the unity client to display other kinds of data and text (like our [statistics](../_docs/features/RealtimeDataCollection.md#statistics)). 
Known controls like tables and tree views would prove an almost impossible challenge as emulating these controls would cause enormous performance penalties.
A game engine was not meant to be used like that, a game developer could probably make it work, but I am not a Game Developer.

So I decided to divide the clients up, a Unity render client to render the real-time call stack and a WPF client to show the other data.
It was not a friendly solution, but it worked.

2019 was nearing its end, managed to fix all issues, and once again had a working prototype that would only need some finishing touches to bring to market.

I also made it that I could load the Unity render client as an inline view in WPF, which was heavy to run but made the HoloLens, not a hard requirement.

Without meaning to, I ended up with a desktop application, a real-time underdeveloped profiler with call stack rendering. However, it still felt like a gimmick because of how I integrated Unity.
And getting rid of Unity by making the call stack render native in WPF would be an unknown endeavor.

So I was at a crossroad, I could either: 
- Finish this and go back to work knowing that I made something fantastic, but it would probably not become more than that, and a lot of time spent on other functionality like multi runtime support would go to waste; or
- I could continue, picking up some side jobs to fund it and try to make it render native in WPF, making it a full profiler and finishing the other profiler prototype. 

I choose the latter.

At this point, I was entirely in unknown waters; I reached a point that Stack Overflow would no longer be a source of information.
I had to make most of the functionality from scratch and work from blogposts of people doing deep-dives into topics, like rendering in WPF, and even those would never give the complete answer. They were bugged, outdated, not working anymore, and always prototypes.
But it gave me ground to work on to make my functionality from scratch.

In these deep dives, I also uncovered unknown network optimizations by accident (I don't know if they are still unknown). With my implementation, I reached over 4.000.000 calls a second, an x20 performance gain.
And as you may guess, all the problems all over again.

At this point, I entirely shifted away from doing things client-side as then, in the future, it would never become a bottleneck. 

I also implemented other types of rendering:
- [call tree](../_docs/features/RealtimeRendering.md#realtime-call-tree-rendering)
- [call stack](../_docs/features/RealtimeRendering.md#realtime-call-stack-rendering)
- [grouped call stack](../_docs/features/RealtimeRendering.md#realtime-grouped-call-stack-rendering)
- [heat map](../_docs/features/RealtimeRendering.md#realtime-code-heatmap)


You might wonder why it still took so long to get to this point. Well, building an application on this scale on your own without supervision for so long, you are bound to make (a lot of) mistakes, so I learned a lot, most noteworthy the following:
1. Keep maintainability at the highest, choose best solutions over quick and simple and common, I still have to understand functionality I wrote one year ago.<br/> <br/>
And really, the others below are primarily methods to do so.
1. <p style="text-decoration: line-through; margin-bottom: 0;">You do not talk about keeping maintain...</p>
1. Think from another developer's perspective, as this other developer is you in a year. This means when you write code think about how another developer would use it and break it and make it that they can't. And if you cant prevent it, make it that the developer would think twice before using it by giving it a strange name and then adding a summary there.
 I choose to use a default naming scheme that informs me that I am probably doing something wrong (e.g. "Proxy_{Name}()") and hid them in proxy interfaces.
1. Do not try to make a solution for a problem that you do not have yet, or create a generic solution while you only have one use case.
1. Keep it simple stupid. Yes, some patterns are cool, but a simple statement is enough 99% of the time.
1. Decide when performance should factor in your decision. Short answer: only bother with it if a profiler says it is your bottleneck (Code is really fast); don't bother with it, and always take the best solution to the problem. Even I do not pull out every trick in CodeGlass; I only do that in the so-called hot path (Path that processes the 4.000.000+ calls per second), and yes, then I ignore rule 1.
1. Keep the code clear and followable even when it is not running, so clean code, no magic code, no auto mappers, no triggers (things that change your program without being able to see what caused it).
1. SOLID principles, no, not just what it means, but really what it entails and why it matters, especially in an extensive program like this, but understand that it is a principle, not a rule, that is why it is in this place.
1. Always work towards MVP, and accept that sometimes that means that not everything is up to your liking; this prevents you from getting lost in the many features you want to have and support.


Well, and that is the story of  how CodeGlass came to be. I hope to build this company around it and hope you will support me in this endeavor, and if it doesn't, I still learned a lot. <br/>

That is also why if it might ever happen that there is nobody to support CodeGlass anymore, I will make its source code available to everyone, so someone else can learn from it ♥ and you do not have to worry about losing it.


And if you are wondering what happened with the HoloLens Client, well, we still have it; it just did not make MVP. <br/>
Oh, and the same happened to the other profiler prototype; as I said, I learned a lot...


~Tyrone Krieger, Lead Developer and founder of CodeGlass

