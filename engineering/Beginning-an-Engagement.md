<img align="right" src="https://github.com/braingu/tadpole/blob/master/images/TLP/TLPAmber.png">


_(Note: This doc integrates some content from [Tech Lead for Dummies](https://docs.google.com/document/d/1CFEG8Wqjh_ARxlpzEEp7ieI-24zpUivOns5HSvXpv7s/edit?usp=sharing). That document is more about managing from a client perspective, and is about the how, while this document is more about managing from a team lead perspective, and is about the why.)_


## Starting a new project


### Assessment

How do you set about forming judgments about the situation? Gather as much intel as possible.

*   **Contracting docs** — SoW, project plan, roadmap
*   **Project Plan** — If there is already a project plan, that’s essential for knowing what’s expected of you. If not, define your own.
*   **People of interest** — knowing who the customer is, org charts, people that have a lot of say in the program, SMEs. Identify and seek out tribal knowledge.
*   **Pain points** — identify so as to go around.
*   **Communication** — Figure out if there are important meetings, points of contact, or system accounts that you should be added to.
*   **Resource constraints** — Budget, staffing, procurement, timetables?

Gather those things, and then look for the gaps in the documentation. Look for parts that don’t make sense or are impossible or at risk. If there are huge gaps or problems with the roadmap, bring them up ASAP, providing evidence, reasoning, and solutions/alternatives. It’s always better to have a fix to recommend than it is to just complain. Anything that stands out as wrong or interesting gets attention.

Probe any gaps in the documentation. Ask people, “Is there more? Is there something I missed?” Try to scrounge up what you’re missing. If it doesn't exist and you need that knowledge, figure it out yourself. Read upstream docs, code, whatever. Then make sure you contribute those docs back to the project.


### Communication style

Be sure to keep in mind who you’re working with/talking to, and adjust communication accordingly (inside/outside the shell — see the Confluence doc). The clients live in a completely different world, and need things presented in a different way. It’s typical of the personality of the folks BrainGu hires to be more blunt/direct/truthful than they maybe should be in a client environment. So always remind yourself of whether you’re inside or outside the shell.

If the client requests that you justify your time, break it out and track hours. You can also use Jira or GitLab issues for metric collection.


### Problem/Situation prioritization

Always hit your timeline.

In order to prioritize correctly, you have to strike a balance between what we think, what the customer sees, and the timeline. Do the bare minimum to meet the timeline, knowing you’ll need to come back and do things properly. For example, if you could spend more time to automate a thing, but the timeline is tight, it might make sense to do it manually once, and then come back or ask for more hours to get it automated. In the last week of the month, make sure you haven’t exceeded contractual time limits.

Having a win is important to management, to team morale, and to the customer. So an easy way to get a win is to pick the low hanging fruit, do the easy tasks that demonstrate value.


### Reducing tedium through process and automation

Project management is an attempt to make the client’s job easier, or to allow them to focus on more important things. We’re not replacing people; we’re reducing tedium.

Teaching the client how to leverage that automation (Ansible slide deck reference). They were doing stuff manually. He revamped their current tooling and they were happy. But he also tried to show them how to do it better. Trying to give them the control over that automation.


### Engaging with teams

If it’s a brand new engagement, work closely with the existing developers to get their vision of how the development project is going to function; figure out what practices they see themselves using, what tooling they see themselves using. It’s their show; they know more about development than we do. But while you’re gathering that, also build a relationship and interject your own views.

If everyone understands the organizational objective and everyone is communicating, the lines between teams (Dev, Sec, Ops) tend to blur. Homogeneity is the goal. Sometimes your largest daily contribution is shuffling info between people in different silos, with different objectives, and making sure that they’re understanding what’s going on. People get focused on daily tasks or discrete objectives, and forget or don’t have time to look at the bigger picture.

Be sure to identify talented individuals and maintain a relationship with them. Recruiting is a thing, but we can’t necessarily hire folks due to contractual stipulations, so therefore we cultivate relationships with excellent talent.


## Keystones

### Communication

Meetings between team leads can trigger to talk about silo-busting, about not stepping on toes or doing things better. Being involved in launch processes helps communicate to the dev team how to communicate with the infrastructure team. Being part of deployments exposes a lot of issues that the developers aren’t thinking of.


### Involvement

Try to get everyone as involved in planning and architecting as possible. Constantly request feedback and ideas. Sometimes you have to really press. This communication is a relationship/trust thing. Don’t shit on ideas is how you get more ideas. Accept and appreciate, but be very explicit about why you go with another. Be collaborative rather than authoritarian. Make people think they and their input is valuable.


### Red Flags

Be aware of when you’re being asked to follow policies and procedures that the client is not following themselves.  This can create a situation where political capital is expended to make everyone fall under one team’s methods and use their design and architecture and codebase as the single source, which implies that ego is being prioritized over best practices.

Check to make sure that the solution being proposed works not only on a specific use case, but throughout the ecosystem. Single-use solutions create downstream problems in maintenance and sustainability.


### Success in an Engagement

On a business level, make sure the client is happy and their business needs are met. On a personal level, your success is being able to contribute in a meaningful way. The BrainGu team tries to be force multipliers, to allow the client team to do excellent work. Ideally the team will be able to sustain progress without the BrainGu team afterwards. Sustaining work is the result of doing all the things -- great docs, great code, great process.


## Dev, Sec, Ops?

Sometimes all three teams exist. Sometimes not.


### Which first: Tooling or Methodology?

Get them to start using the tooling. Maybe they don’t know why, or what the end goal is, but when you improve stuff that way, they start to understand why you want things to happen a particular way. A lot of people think they understand the concepts, but putting it into practice is daunting or tedious. If you can reduce the pain point of the tooling, that reduces the effort required to follow the concepts. If you can assist the teams in overcoming barriers to entry, they’re more likely to adopt.


### Which first: Sec or Ops?

It depends. If there’s an immediate business need, you address that first. You keep funding coming in, so you can keep working. But you can’t abandon anything else. You have to understand business needs and policy requirements. You have to find a balance there. There's also a difference between compliance and security that you have to factor in. Usually no one is paying attention to actual security.
