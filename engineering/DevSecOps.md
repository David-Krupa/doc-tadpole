<img align="right" src="https://github.com/braingu/tadpole/blob/master/images/TLP/TLPAmber.png">

## Development


### Automation

Does automation force accountability? Ownership?

*   A lot of compliance items are enforced by the pipeline (set of automated practices).
*   Business motivations have to be taken into account when making decisions.
    If you lean too far into sec or comp and blow the biz requirements.
*   Set some minimums on the security side, and make those minimums as easy as
    possible for the client to accomplish. Tooling, scaffolding -- there’s no
    excuse not to. Make it not tedious for them. If you’re running DevOps, this
    is definitely part of the job.


### Integration

*   “We were doing this before it had a name.” If a developer didn’t consider
    security in their application, their application wouldn’t make it into production.
    Part of what we do is assist them in setting that up. “Hey, you’re talking to this
    dB, but you’re not authenticating or encrypting those coms…” Help them set
    things up as securely as possible, and keep the security folks looped in for compliance.
*   In some client sites, if you don’t do security, you never get to the Ops phase.
*   BrainGu doesn’t do much in the way of incident response; you want to set up
    logs and metrics to make available to the Ops people.
*   A major part of federal contracts is compliance. The clipboard guy stops the
    show until you give them evidence and justification and support. The same
    mindset should apply to both spaces.


## Security


### Philosophy

BrainGu does compliance-type security more than other kinds, and because most
clients are Federal, it’s the [NIST-800 series](https://csrc.nist.gov/publications/sp800).
    The key there is understanding the requirements and making sure you stay on
    top of those, and on top of providing the auditors with the evidence they need.
    You can hope for standards at the beginning, but because testing/compliance/security
    are subjective, the target moves. Mostly you’re given broad requirements like
    “target environment needs to have these controls,” and you can aim for those.

  Tests might be proscriptive, or they might not. Might be as simple as “prove
  you’re encrypting communications,” so you do a [Wireshark](https://www.wireshark.org/)
  dump. Or it may be “prove that this database doesn’t allow unauthenticated
  credentials.” If their tooling doesn't provide remediation, they probably
  don’t know much, so it’s probably up to you.

### Culture

  There’s a balance in working with people with different focuses and mindsets.
    Everything is at some level vulnerable to some form of attack; you’re going
    to get popped eventually. Your goal is to minimize the likelihood of that
    happening. A professional will understand the business need that “yes, it’s
    vulnerable, but it has to go out, so we have to make it as unlikely as possible
    that it’ll get popped.” It’s not just an exercise in breaking; it’s more an
    exercise in reduction of risk.

  When you’re architecting, security should be involved and pointing out flaws
    before you even have code written down. If you’re coming up with a bad design
    for service communications or opening up vulnerabilities in an authentication
    authorization model, the security folks should be onboard and participating
    in design from the beginning. Continuing that collaboration, making sure what
    you do is accessible to them, so they can break it as you build it.


  The process works best when security is integrated with development right from
  the start. This is often led by management, who understand that there are ramifications for not doing it right. Having that buy-in, making security part of the business need, matters. Within the team, the key to establishing a good working relationship is understanding that breaking shit makes it better, and you’re on the same side. Make sure that security’s grievances are not pedantic. Make sure there is real value to fixing the problem.


  Once the team finds vulnerabilities, you then make a choice to



*   ignore,
*   accept and document, or
*   fix.

Ignore makes security sad, and fix makes the developers sad, so the bit in
    the middle is where you want to keep it. Learn to accept vulnerabilities,
    but document them so that you can circle back and fix as soon as possible.


### Tools


  Community adoptions is one of the biggest metrics for finding the best tooling.
    Are leaders in the field using the tech? Is it so commonplace it’s a no-brainer?


  BrainGu typically works in environments that need more long-term support.
    So look at maintenance. Does the tool have a history of being maintained? Is
    it supported by major Linux distros (RedHat in the federal space)? Is it
    supported by upstream communities? Is there an Enterprise version of the
    thing with contracts and money? That makes it future-proof, which is very
    important in Federal contracts.


### Testing

  *   Static Code Analysis (SAST) (whitebox)
  *   Dynamic Code Analysis (DAST) (blackbox)
      *   A little more difficult
  *   Dependency Scanning (GitLab)
  *   License Compliance
      *   Not as important as other things
      *   You’re in house, not releasing to the public
  *   Credential leaks
  *   Configuration issues


## Operations

Operations is often overlooked until needed. People focus on the immediate
business need, and not the desired end state.

Right now, BrainGu is mostly in pure development space, with no production
environments. But we should all endeavor to design and develop in a way that will
be sustainable, and make decisions with ops in mind (updates, deployment)

Bake orchestration and automation into development. Launch nothing into production
that isn’t as “self healing” and idiot-proof as possible. Things should fail gracefully,
restart, be repeatable. Having a rollback plan is critical, which is easier with
tools like Kubernetes and Spinnaker, which allow for canary-style rollouts.
