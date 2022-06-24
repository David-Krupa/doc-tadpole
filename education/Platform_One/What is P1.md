<img align="right" src="https://github.com/braingu/tadpole/blob/master/images/TLP/TLPAmber.png">

# What is P1?
In short, Platform One (P1) is an organization that tries to make developing software for for the DoD easier and more secure.

P1 has grown into quite a large organization that provides several products: 
- Big Bang: Infrastructure as code for Kubernetes clusters that follow the [DevSecOps Reference Architecture]()
- Party Bus: a Platform as a Service that provides development tools and managed environments
- Iron Bank: a source for approved container images

Let's start with some background on typical DoD dev to see how and why P1 has become influential.

## Authority to Operate (ATO)
Software that runs in DoD production environments require an ATO, which is a certification from a trusted official (the Authorizing Official, or AO). The AO personally vouches for the environment - they accept the risk of putting sensitive DoD data into it, so they want to be confident that data will be safe.

Typically the process to convince an AO that your software is worthy of trust can be intensive. Often, AOs will want to review _every change to the system_ to make sure it doesn't introduce more risk. As you can imagine, this slows down the pace of software development.

## Continuous ATO (C-ATO)
P1's early innovation was something called the Continuous ATO - a comprehensive set of policies and procedures governing everything from how developers write code, to the architecture of the environment they deploy it to. They were able to convince their AO that this set of policies made it safe to push updates to code _without reviewing each one_.

So how does this work?

P1 has "shifted security left", meaning it happens earlier in the process. Instead of doing a security check right before pushing to production, there are security checks (and practices that promote security) all through the development process.

You can read about the [C-ATO]() for more detail on what that actually means in practice. At this point, the important thing to know is that teams who use P1 are making a trade - they do more work up-front before getting to production, and don't have as much freedom as they would on their own, but they are able to push updates quickly once they get to production.

## How P1 fits into the DoD
An increasing number of groups within the DoD want to stand up [Software Factories](https://software.af.mil/software-factories/) that use P1 tech. Software factories develop software for a specific set of users. For example, LevelUP works with cybersecurity-focused groups and Space CAMP works with space-related groups.

P1's role is to listen to community feedback and develop solutions that fit their needs. At the same time, P1 is realizing that demand exceeds what they can supply. Their Party Bus offering is a good option for simple applications that can run on Kubernetes (e.g. those that have a frontend, backend, and database). Monolithic legacy applications, data science tools, and products using tech stacks outside of a handful of popular web programming frameworks are not well-suited to Party Bus. P1 is recommending that groups with these needs set up their own Big Bang.

To that end, P1 has open sourced the Big Bang projects.

## How BrainGu fits into the P1 ecosystem
Standing up a Big Bang is not simple. There is more involved than just running a cluster and deploying apps onto it - the apps need to be developed in a pretty specific environment (remember the C-ATO), Day 2 support is essential for production software, and Big Bang won't answer every requirement, so teams will have to customize their own deployments.

BrainGu has been involved at P1 in almost every level: as users (developers of WIDOW, one of the first apps to get a CtF), as support staff (embedded into P1 teams), and as contributors (teams deploying Big Bangs and contributing fixes).

BrainGu has many contracts that involve helping customers work within the world of P1. In the future, we expect to have projects to help teams set up, maintain, and optimize software factories.

