<img align="right" src="https://github.com/braingu/tadpole/blob/master/images/TLP/TLPAmber.png">

_Configuration as code is the formal migration of config between environments, backed by a version control system._

IaC — instantiating resources (building something)

CaC — applying settings to said resources (setting something up)


## Tooling


### IaC

*   [Terraform](https://www.terraform.io/) — Sam does everything here because it’s “cloud agnostic.”
*   [CloudFormation](https://aws.amazon.com/cloudformation/)
*   [ARM (Azure formation)](https://docs.microsoft.com/en-us/azure/azure-resource-manager/)
*   [GCP](https://console.cloud.google.com/getting-started?pli=1) (Google)
*   [https://www.pulumi.com/](https://www.pulumi.com/) — Sam hasn't personally used it, but i know it exists and is gaining traction
*   SDKs for doing all of this (imperative vs. Declarative)


### CaC

*   [Ansible](https://www.ansible.com/) (Sam's go-to)
*   [Puppet](https://puppet.com/) (used to be)
*   [Chef](https://www.chef.io/configuration-management/) — worth knowing about as a potential solution.
*   [Salt](https://www.saltstack.com/) — worth knowing about as a potential solution.


## Ansible

*   [https://www.ansible.com/use-cases/configuration-management](https://www.ansible.com/use-cases/configuration-management)


## Jenkins

*   [https://www.jenkins.io/projects/jcasc/](https://www.jenkins.io/projects/jcasc/)
*   Leverage this to deploy your config or IaC
*   Sam dislikes Jenkins because it’s the original platform, and a lot of legacy
    things have been brought along with it. Powerful because pluggable, but also
    not super friendly. You used to have to config through a UI, but now declarative
    scripting language, (groovy w/poorly-documented things added to it.)


## GitLab

*   [https://about.gitlab.com/](https://about.gitlab.com/)
*   Preferred tool. GitLab is easier to grasp and work with; less churn to get
    it to do what you want it to do. Not a scripted thing — extremely declarative.
    “I want to apply this, and it does it.”


## Approach


### Best Practices

*   [https://www.slideshare.net/DougSeven/devops-practicesconfiguration-as-code](https://www.slideshare.net/DougSeven/devops-practicesconfiguration-as-code)
    The DevOps movement, like its Agile predecessor, is focused on improving the
    communication and collaboration between the development and operations teams
    responsible for different aspects of an app throughout its lifecycle. While
    successful DevOps initiatives start and end with organizational and cultural
    change, there are also common practices that are enablers and/or tools used
    in support of DevOps.
*   Often overlooked esp with Ansible — [idempotency](https://en.wikipedia.org/wiki/Idempotence) (Run as provisioning, which isn’t the best approach.)
    If you’re running [Molecule](https://molecule.readthedocs.io/en/latest/) for running tests, it has to pass that.
*   [https://www.reddit.com/r/devops/comments/gbkqz9/monthly_getting_into_devops_thread_202005/](https://www.reddit.com/r/devops/comments/gbkqz9/monthly_getting_into_devops_thread_202005/)


### Philosophy


#### Championing Change

*   Be aware of opportunities to be more consistent, more beneficial.
*   Where docs don’t exist, figure stuff out from source code. And once you figure
    it out, make sure you champion or create the documentation you needed.
*   Exemplify best practices, driving towards CI/CD.
*   Show, don’t tell.
    *   “This is how it works for me, and so this is how I’d approach the problem.”
        This only works once you’ve produced the work.
    *   Showing of trust — I can get this done.
    *   Example — The customer required deployments on 10PM on Tuesdays. We were
        just starting, so had not established policies. These things were quite
        manual and required rollbacks, troubleshooting, and QA. No one enjoyed this.
        If there was a problem, they’d bring the Devs in. We came up with better
        policies and practices, and would roll out an update any time any day, and
        mostly it was seamless, because everyone had followed the practices. And
        it was not done by hand! Click and watch the logs.

*   A huge part of DevOps is bridging the gap between siloed workflows. Help the
    developers get their code on their infrastructure. Then, help infrastructure
    get their environment running right. Then, help security get their stuff right.
*   Listen to requirements and make sure they’re met.


#### Driving Connection

*   Seeing how the pieces connect, and creating those connections, is more important
    than expertise. You’re supposed to be relying on the client or the SMEs for
    their expertise. You may know more about how it integrates with those projects
    than they do.
*   If a developer doesn’t know policy exists, you have to help them out and share the
    info. You assist with properly communicating the rules for the environment.

#### Driving Adoption of Best Practice through Results

*   Put in CI pipelines that force developers to use linting. Can't merge without
    unit tests. Give them strict guardrails to follow to be successful. Surprised
    and happy once when he said “I know this sucks, but what do you think?” “It
    used to suck but it is easier now.” Resistance, but then into it after the results.
*   Getting them to see that we're doing these things to make their lives easier.
    People get a little anxious when you tell them you want to change how they do their work.
*   It got to a point where they trusted his judgment. (how? Time, quality work,
    good decisions in the past. Past performance. The big thing was, he was doing
    the workload of a whole team, so he proved that with good tooling and consistency,
    automation makes the workload a one-person thing.)
