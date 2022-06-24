<img align="right" src="https://github.com/braingu/tadpole/blob/master/images/TLP/TLPAmber.png">


## Contents

- [Project Management/Leading a Team](#project-managementleading-a-team)
- [Engineering](#engineering)
- [Efficiency](#efficiency)
- [Psychology](#psychology)



**_“I don't actually have a lot of books that I reference. The majority of my approach/opinions come from experience and exposure to a lot of examples both good and bad.” — Matt Shaver_**


## Project Management/Leading a Team

*   Making sure the team knows the reason “why” things are being done. “What motivates people?” A lot of his knowledge comes from TED talks and articles that come from sociology — how societies work, and how people are creative, and how they should respond to money being an endorser vs. impact being an indorser. How that changes from creatives.
*   Past jobs have had a very dictating way of task management and breakdown for what needs to be done, without explanation for the value. The argument is that “time is valuable” and if you are going to explain to everyone, you’re going to lose a ton of time. For him, coming from someone who is a Myers-Briggs “commander”, he goes with the approach of, it’s easy to dictate the impact something is going to have, vs. why decisions are being made. So for example, timecards should be done daily. In the past, and every single past job, this was hammered in like “this is a company mandate, do this” or there would be negative consequences for not doing this. But when it gets down to recording it, if people aren’t doing it, they don’t know the reason why they should. For WIDOW, putting your time daily isn’t a BrainGu requirement; it’s a legal requirement. We are legally bound to put in our hours daily. If we get audited and we aren’t doing it daily, we could lose our contracts. Not just your project, but all BrainGu projects. Lessons learned; if you want to give people the info and have them do it, they need to be able to hold on to why it’s important to them.
*   If you have a good team dynamic, things impacting the team matter more than the individual.


## Engineering



*   If something is on fire, fixing it immediately may not be the best course of action. You see this depending on experience level. Juniors make a certain set of problems, mids a different set. Best practices, for example, say you're a mid or just into senior engineer, managing a production server. Your client’s info is your responsibility. Something unforeseen happens and something blows up. A mid and early senior reaction would be to go in and fix the issue. It’s in the Best Practices books not to do that with client data because your fix hasn’t been tested. A senior will tell you, rollback your deployment, go through your fallback plan, and analyze the issue and fix it in the next deployment.
*   If you’re not setting appropriate expectations with clients and leaders that deployments can fail, they’ll set inappropriate expectations on their stakeholders. If they don’t know it can happen and that there’s a rollback strategy, they wouldn't give that caution to their stakeholders. Communication matters when dealing with enterprise systems, and building that trust with clients, that something wrong will eventually happen and they have a known measure to correct it.
        *   There’s usually a gradient, from the engineer to the folks making financial decisions. Your PM may understand this, or your PM’s lead, but at the end of the day, they’re not responsible for that financial line of business. That person’s boss hasn’t ever dealt with an enterprise system. If they hear a fix could have been met immediately to meet their obligations, they’ll be mad that it wasn’t.
        *   BrainGu’s model for training around this, is qualitative rather than quantitative, but our process has been the Sith mentor model. Be on the call with the leads that know what they’re talking about as a background player. New leads are in meetings with him for ~3 weeks, and then they talk offline about why he brought up certain things. Then vice versa.
        *   Deployments, engineering requirements gathering.
*   Software is not the same thing as a bridge. There's a reason bridges take years of scoping. There's no failure fallback, but that’s why it takes years.
*   When you have clients who are making decisions based on money, they aren’t looking at the software process. If you abstract that out to the military, this investment gives me this capability. Where you see a lot of success, netflix, amazon, google, where they have a big primary tech biz, and the biz leaders have some tech knowledge. But other than that, they just don’t have that knowledge.


## Efficiency

The guiding principle is efficiency. He has a big bone to pick with anyone who doesn’t use a debugger. Efficiency means you set up your environment so that when you make a change, you see the results of that change within five seconds. We’ve reached a world in DevOps that for the developer experience, people try to abstract it like a production environment. But you should be getting instant feedback on what you’re building. Where he’s seen this go wrong, people spend hours trying to find some weird character misplaced, or typecasting, which through logging is very hard to find. But the value is knowing how to debug something, and whatever your favorite IDE is, a line-by-line level so you can see what’s being executed. You can’t always do that, but those situations are rare — usually only low level cyber stuff that can’t be executed at that level.



*   The majority of the work you do as an engineer is improving or fixing old stuff, not making new stuff. So finding the root cause of issues as fast as possible is priority. Time spent searching isn’t fixing the problem. Engineers get too specific in trying to fix a problem, and don’t go to the actual root cause. You have a system where it should say “Hello, username.” But “username” isn’t popping up. 90% of the engineers he works with will go into the backend, validate that it’s in the right place, validate the steps of the data along the line. And then finally at the end, they’ll say, how’s it getting to the frontend, and they’ll find that the text box for the username field has a typo. Most front end issues are front end issues. The other approach is an academic hangover.
*   You pick up these types of ways to find the root cause and fix them, so … an engineer going to the official docs, before referencing current work within a project. If you do that enough you need to refactor. But people are scared of refactoring, at the detriment of productivity.
*   If you’re coming into an embedded environment and make architecture decisions and refactoring, you need to know the lay of the land before you code. If you’re coming in to put out a dumpster fire, you only need to know how to fix the problem. Where experience comes into play is knowing the tension between those two things, and in recognizing when it’s completely valid and OK to put out a fire, and when it’s valid to review the ecosystem. Putting out a fire has its own consequences. Being a good senior is knowing the pros and cons to both approaches and being able to pivot between them.


## Psychology

*   TED talks — less on the technical side, more on the people side. What motivates people? How to manage and deal with procrastination. How to work with different personality types. As a leader, you need to be able to get at the heart of what motivates people and what empowers them. “You need to empower your people”... but how? You need to break down how people think, and the combo of logic and emotion, and what people’s needs are. He looks for stuff, but it’s usually when he has dedicated time to work on that side of his leadership skills. Sales strategy, business development, that kind of thing too. One of the biggest things he assists engineers with, a lot of people are put off by the idea of sales. You have to recognize that you should only be selling something that you believe in. That’s going to make a quality of life improvement for the organization. We’re not looking for sales. We’re looking for you to have trust and confidence in the solutions you’re building. That has a positive impact, so sales is just talking about that positive impact.  Talking at conferences and all that is just talk about what’s being built and how it can make a difference.
*   Where he goes depends on what problems are arising. If it’s leadership specific, he would go to the Books list first. YouTube channels, articles.
    *   Diversity, which will be an issue. Censorship. Professional workplace. What issues are coming up that are big picture that he can find resources on? Based on that, what connections are there?
