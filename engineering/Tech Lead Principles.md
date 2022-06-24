<img align="right" src="https://github.com/braingu/tadpole/blob/master/images/TLP/TLPAmber.png">

### Tips from Michael Kahn

## Contents

- [Perception Management](#perception-management)
- [People Management](#people-management)
- [Onboarding to the Contract](#onboarding-to-the-contract)
- [Being Aware of Burnout](#being-aware-of-burnout)
- [Problem-Solving Approach](#problem-solving-approach)
- [Learning Context](#learning-context)
- [How to Find Answers](#how-to-find-answers)
   * [Picking Good References](#picking-good-references)
   * [Recognizing when you’re not getting the whole picture](#recognizing-when-youre-not-getting-the-whole-picture)
- [Critical Thinking Skills](#critical-thinking-skills)
- [Mentoring to Foster Thought Diversity](#mentoring-to-foster-thought-diversity)


## Perception Management

Typically, there’s the customer (whomever the contract is with), whomever you’re reporting to (whomever is paying the bills), other contractors (subcontract?). The first thing is figuring out whose perception matters in what way. So, if you’re coming in doing tech lead work, then we may be reporting to a government program manager, and having other contractors report up to us. In which case, we need to figure out what the program manager’s goals are and how they want to interact with us/them. They’re typically the most important person who needs their perceptions managed. But team morale/teamwork also matters.

We might be working with people who already have opinions, or have never heard of us. May be good, may not be. We have to figure out how to work productively within that.

BrainGu has gotten better at narrowing the scope of what it goes after to reflect the goals that we have. Early on, we had a bunch of take-the-money contracts. That leads to a boom-bust cycle of more than we could take versus having to hustle. In the last year or two, we’ve gotten much better at narrowing the scope of the work we do, and focusing on getting more of that kind of work.

Government is where most of the work started. It’s a much easier market for a cybersecurity company. They started there and expanded into civilian work. Government is much longer term and a lot more stable which makes it easier to plan and manage the sales pipeline. There's a significant difference within the government umbrella. Lots to learn moving around parts. There are enough commonalities that you don’t run into extra overhead for, say DoD versus VA contracts.


## People Management

In both of his contracts, they were subcontracting, but he was leading the team that included employees from the primary. It mostly worked out, but there was lots of pulling in different directions. As long as things are going well, it works out OK. When things start going less well is when those different motivations go in conflict.

It’s difficult if you’re managing the team but you don’t have direct personnel control over the people on the team.

When there’s a technical argument, that's straightforward, and you can gravitate towards that first. But there are also a lot of cases where it may be a technology project, but a lot of the challenges aren’t technical. For example, trying to guide people through organizational change. Or, on the STOR contract, towards the end, there was constant changing of group/budget/mission. A good part of his job was less solving technical problems, more figuring out what the right goals were, and keeping people motivated despite going in circles.

There’s always a need to do the thing you’re told. If we have a good relationship built up, unless it’s like a real hierarchical personality, he had some ability to push back against the counterproductive. Assume that there is some flexibility to make implementation decisions. He tries to make sure they’re delivering something that brings some benefit, not just toiling to build the perfect thing that does not see the light of day. Incremental change that benefits people they know are using the project.

One BrainGu doc says “deliver on timelines, make sure timelines are reasonable.” It takes an initial success to build up trust to make decisions. There are a lot of managers in government contracting who have been burned by contractors who don’t get the job done or are constantly pushing back or don't make timelines.

Some things are more controllable than others. In some cases, if it’s not the case, you have to adapt to the situation, learn more about the customer, and do better next time. To a large extent, if you have influence on it, then it’s something you can make suggestions for, present evidence, and change the situation you’re in.


## Onboarding to the Contract

Onboarding for a specific project or contract is about learning a whole new set of resources to be productive. Project-specific onboarding = orientation. For any given project, they normally need to create onboarding themselves. If it’s a government customer, there’s probably a whole separate process for badges, etc.

There usually isn't adequate documentation. Trying to figure out what is up to date and what was obsolete five years ago is something that anybody new or junior won't easily be able to tell. It may just be institutional knowledge about whether things are useful or not.

It varies largely based on the amount of tribal knowledge still around. Some contracts, there are three people who have been there for 10 years and they know all the answers. But there are also times where you have to see things for yourself.

For knowledge transfer, it’s best if you write a guide with references to important resources.


## Being Aware of Burnout

[The Cyber on Twitter: "Anyone in infosec during this quarantine/pandemic slowly thinking about leaving the field altogether?"](https://twitter.com/r0wdy_/status/1274050973783085061)

## Problem-Solving Approach

Make sure I’m trying to solve the right problem.

In a tech lead or dev lead role, the majority of the problems are not straight technical problems. In a lead role, the majority of problems are trying to integrate some user story type-problem. In an architecture or developer role, it can be a mix. 50/50, or if someone’s doing the architecture not you, you can just debug, which is straightforward.

There’s a distinction between initial development, and developing features, vs. running an existing system, where you’re going to spend more time troubleshooting errors and tech problems than you are solving new features.

New code problems and old code problems can be equally problematic. If it’s your old code, it’s not as big of a deal. If it’s someone else’s, that’s a bigger deal.

Code docs are something to be valued, and are critical for maintainability. They’re hard to keep up with, just because generally the incentive structure for project development is focused on feature release, and/or the minimum viable product (MVP). Unless you have a team and a project manager committed to manageability, good docs don’t always make the cut.


## Learning Context

From a tech level, it’s going to be questions like, where is this being deployed, what kind of environment is it running in, what kind of performance or space or security limitations does it need to run in? Environmental stuff. Unless you’re dropping in somewhere new, you probably already know that. If you’re debugging a production error, what software version, what container environment, how can I recreate that most effectively in a test environment? Trying to control as many variables as you can so your solution works in production.

For less strictly tech problems, it’s like “where did this requirement come from? Users? Organization? Security and compliance? Who are the stakeholders? Do we do this because someone said so, or to improve the product?” Make sure that the solutions you come up with are addressing what people actually need, not what they say they want. But of course if they knew what they wanted, they wouldn’t need consultants.

The first point of contact is the program manager, or the tech lead if you aren’t them. If you’re lucky, they will already know all of the context and will have already done a lot of the legwork. There’s no reason to try to redo all their work.

Second, you need to figure out which requirements will change and which won't. You watch for long enough to see how things change, and whose decisions seem to carry more weight. A lot of it you can tell from looking at document histories, and seeing if you can find a project plan from a year ago, and diff. That gives you a sense of which things are constant and which change.

If it’s not a brand new team and a brand new project, talk to the folks who have been there longest and have the longest institutional memory. In some cases, those people are the most burned-out and cynical, but they have useful knowledge.

You may or may not have direct access to the end users. If there is a process to get feedback from users, then that’s super important to be able to talk to them and understand what it is that they’re looking for. Formal user studies are great but there’s often not budget or management for that. But just knowing who your power users are and who you can go to and say, “we want to make this change, how would that impact your workflow?” is really useful.


## How to Find Answers

[https://www.oreilly.com/content/4-steps-to-solving-any-software-problem/](https://www.oreilly.com/content/4-steps-to-solving-any-software-problem/)

1. Identify the problem.
2. Gather information
3. Iterate potential solutions
4. Test your solution

Or

[https://codeburst.io/10-steps-to-solving-a-programming-problem-8a32d1e96d74?gi=8b82662d3e17](https://codeburst.io/10-steps-to-solving-a-programming-problem-8a32d1e96d74?gi=8b82662d3e17)

Or

*   BrainGu library — good for contextualizing why things are the way they are.


### Picking Good References

*   Stack Overflow is a good thing, ish, because it is full of common questions. But for more obscure errors or something less common, you have to know your exact terms, and whether the answer is going to help you, or not. You can evaluate it based on the qualifications of the writer, or the logical flow of the answer. Answers with more explanation are better than one line of code with no explanation.
*   If the answer is 10 years old, find a newer answer. Look at the date of the post. (which in Stack Overflow needs to be bigger.)
*   Words that sound like what you’re used to dealing with are probably more useful.
*   If you find an answer for an error message on Win10 and you’re wondering why chrome doesn't work, but you find answers that have similar words but Oracle server, keep looking. Sometimes they have the same library… but maybe not. Better to try to find something with more keywords in common.
*   Knowing the right search terms… that’s harder. Having more of a structured background helps you recognize more of the official terms for a given language. If you get a message that’s an obscure Linux code from 40 years ago, you could look up that message, but you will get better references from the base. That skill comes from either having more theory background, or reading a lot of language-specific materials to know how the language is constructed.
*   Wikipedia computer science stuff is fine. Non-CS stuff is hit or miss. If there are enough to care to edit well but not so many that they fight over it, that’s good. You can tell a lot by the editorial quality.

### Recognizing when you’re not getting the whole picture

Trying to get an answer, and realizing that it’s incomplete, or solving a symptom but not root cause. Lots of problems that are caused by SE Linux errors, 90% of the answers you find are “disable SE Linux” and that’s it. But that’s just turning off the subsystem. There are ways to solve all of these problems, but most people who aren’t running in these environments (govt) don’t want to run with it. On the QA side, this is a solution that works for them. On the side of the BrainGu researcher, the key piece of it is understanding the solution. Copy-pasting a solution from the internet shouldn’t be enough; you should understand what you’re pasting. If a command is changing something on your machine, you should do the work to understand what it’s doing.

The process of sorting is like 20 tabs and then triaging the ones that seem most useful. (“seem” also being a thing developed with time). Which ones are more detailed, which have matching terms, which are more recent and apply to the right version of the product?

## Critical Thinking Skills

To the extent that engineers are successful, developing critical thinking skills is critical. An awful lot of engineers end up running the bureaucracy or being in charge of murderous and evil regimes. Oh yes, the person who was running Werner von Braun — you expect us to believe you didn’t know what was going on, and you didn’t question the instructions you were given? So CTS are important to problem solving. You can pretend you don’t understand what you’re doing, when you do have the ability for critical analysis but just don’t care.

Problem solving and critical thinking are not the same things, to the extent that analyzing information for its quality, providence, and accuracy, is a necessary prerequisite for problem solving, but that’s not to say that you’re falling back on ethics to decide that you should. If you’re reflecting on the info for a tech problem, those are the same skills to apply to larger problems as well.

He’s generally hesitant to accept arguments about engineers having a particular set of qualities or skills that are self-selected. It’s all about problem solving. Debugging, editing, writing are similar thought patterns. He doesn’t want to make it sound like “make your brain work a certain way and that’s the only way to succeed.” Along with patterns of thinking and basic concepts, there’s a whole body of knowledge of keywords and resources and application.

Experiential and some is researchable. Which pieces are more amenable to being “taught” vs mentorship and shadowing.

Mostly, he researched on his own, outside academia. Things he researched, standing over people’s shoulders. Specifically, that’s particularly useful in areas where that base knowledge isn’t there. Where “things you know” is less, you can learn a lot by watching people. If it’s an area where you don’t know what the terms or commands or technologies or patterns are, you can pick a lot up by watching. However, the value is predicated on being able to place the info you get into a referential framework. If you have analogies you can fit things into, you can get a lot done by watching. The bootstrapping problem is really, really hard.

## Mentoring to Foster Thought Diversity

Mentoring is hard. We know we need to do it, and we know we’re not always great at it. For people who are above a certain level, or who just think in certain ways already, we can learn a lot from each other and communicate how to do new things and pass knowledge back and forth. But he also feels like on occasion where they've hired junior folks or think in the same ways they do already, we’re kind of at a loss for how we teach them things. We told them the thing they should know and we told them how we do it, and it’s been three weeks and they haven’t figured it out. He doesn’t know how fine a line that is; past it and it works, or we don't know how to push you over, or if there’s a spectrum on it. But in the past, they’ve known within a month of hiring, they’ve known whether they get what they’re teaching or not. To scale, you have to identify fast, or understand how to teach them better.

At the very least, we need to be able to articulate what that line is. Saying that you have a culture but not being able to strictly define it other than “they’re like us,” is dangerous. You end up a company of people in groupthink, lack of diversity, things like that. You have to be able to separate out the parts of your culture you value because they let you accomplish things, and the things people who started the company have in common. It’s necessarily the same thing as that line. One has to reflect on that before they come to that conclusion.

We spent a lot of time trying to nail down what BrainGu culture is. But what is it? Any time that you’re defining a culture for a group, you have to be asking yourself what parts of that culture are good, coincidental, or self-reinforcing in a non-positive way.

It’s hard enough to identify — if you know you’re defining an in group and an out group — you have to be careful about who that in group is. BrainGu is way better than most cases. But it was a company created in government stuff, which is less diverse by definition because you’re limiting yourself to US citizens anyway.

If the reason you’re having trouble getting people across the line is because they learned a different way or have a different background but are capable in a different way, you have to learn to deal with that.
