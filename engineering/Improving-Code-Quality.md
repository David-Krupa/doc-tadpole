<img align="right" src="https://github.com/braingu/tadpole/blob/master/images/TLP/TLPAmber.png">

## Code review

Ideally, when you’re diving into a review, there are already a number of things done for you; your [CI pipeline](https://docs.gitlab.com/ee/ci/pipelines/) would have already run quality tests like unit tests and linters and automated testing. By the time you’re reviewing, all those things should have passed. That way, you can deploy to a development environment and there should be no reason it immediately breaks. Integration issues, sure, but not basic build/run/syntax issues.

Focus on changes made in that particular commit or merge. Ask yourself what’s been changed, how does it affect dependencies? Focus on architectural impacts, ramifications, pros and cons. Figure out what decision led to this change, and why did it happen?


#### Peer code review vs. vertical?

[Best Practices for Code Review | Learn Code Review](https://smartbear.com/learn/code-review/best-practices-for-peer-code-review/)

Usually, code is reviewed within a team of peers. One person is lead on a given issue or objective or bug; the rest of the team is responsible for reviewing that and making sure it fits in well with the rest of the project, and that it’s a good decision, fix, or feature.

The funnel is the fact that you need eyes, not necessarily a given set of eyes. If he sees something could be done better, he’ll suggest they do it that way. If it’s wrong, he’ll teach the reasons why. He’ll accept good enough if it’s maintainable, and if the time vs payoff factor is correct.


### Basics



*   Naming

    Defer to the group. I’m pedantic about some things, but not necessarily about the name. If there’s a style guide or standard, great, but not a biggie. Things must be syntactically correct. Has to fall in line of the style of the group.

*   Structure

    Just stick to the style guide. Human readability is important. Someone at some point is going to have to line by line, so human readable is a huge win there. Things should be reusable as much as possible. Less code to do more. If you can take something and make it a module or reusable function, you should do that. BUT! Effort vs. Payoff factor.

*   Comments

    Inline comments — if you think something needs an explanation, it should have a comment. If you’re doing hacky things, record why. Explain why what you did worked, what you were doing to do in the future to fix the hacky stuff, so anyone could contribute.

    Write comments to note the interesting and important, plus todos. Think of it as leaving notes for your future self.


### Testing

What do you test?

*   Test every commit, ideally. If you don’t have a functioning CI pipeline (and you should), at least run functional tests, linting, etc.

*   You ABSOLUTELY need to pass all your tests before you can commit. If necessary, force folks to use the CI pipeline and to use merge requests rather than pushing to master, to force test use/passing. Ideally, no one should be able to merge unless the tests pass.

*   Your testing tools are wholly dependent on whatever tech you’re testing. [Molecule for testing Ansible](https://www.ansible.com/infrastructure-testing-with-molecule). Wraps in a whole bunch of tests in one framework — linting, unit, idempotency, functional… whatever you configure it to do.


If you can automate it, you should be performing it, and as often as possible. Upon every code commit, you should be testing that code. [GitLabCI](https://docs.gitlab.com/ee/ci/) makes it super easy. Testing should be done at the server, not local, except for running a linter locally before commit, just to check your own work. You can use Molecule to test locally if necessary because the GL/CI doesn’t have the capability to run the tests/framework desired.

*   Unit testing
    Absolutely automate and do them. Tend to be in contracts. Code coverage 95% for unit tests in reports in contract.

*   Integration testing
    Definitely do it, as close to your production environment as possible, as close to production data as possible or it doesn't apply. Due to restrictions on the data (data spread) sometimes it doesn’t work. System, Acceptance, and Service Layer/API testing are part of this.

*   GUI tests
    Not usually done in their work. [Cypress](https://www.cypress.io/), maybe?

### Specifics

  *   Static Code Analysis (SAST) (whitebox)
      *   Code coverage
  *   Dynamic Code Analysis (DAST)(blackbox)
      *   A little more difficult
  *   Dependency Scanning (GitLab?)
  *   License Compliance? Does this even enter into your world?
      *   Not as important as other things
      *   You’re in house, not releasing to the public
  *   Credential leaks
  *   Config issues


### Error messages

*   Do you pay any attention to quality of error messages?

  It’s important, but most of the time, because of his history with parsing logs, Sam uses an [ELK stack](https://www.elastic.co/what-is/elk-stack) to capture everything and parse all the logs. If there’s no common format for error messages out of an application, it’s impossible to search, alert, etc.
*   Error messages should contain contextual info. Not really his wheelhouse, though. Sam’s mostly doing scripting or declarative, and the framework handles errors.


### Syntax and Style (linters)

*   [Yamllint](https://pypi.org/project/yamllint/)
*   [Jsonlint](https://jsonlint.com/?code=)
*   [Flake8](https://pypi.org/project/flake8/)


### Best practices



*   [https://www.fabian-keller.de/blog/documenting-architecture-decisions/](https://www.fabian-keller.de/blog/documenting-architecture-decisions/)
*   [https://adr.github.io/madr/](https://adr.github.io/madr/)
*   [https://www.writethedocs.org/guide/writing/beginners-guide-to-docs/](https://www.writethedocs.org/guide/writing/beginners-guide-to-docs/)
*   [https://chromium.googlesource.com/chromium/src/+/master/docs/documentation_best_practices.md](https://chromium.googlesource.com/chromium/src/+/master/docs/documentation_best_practices.md)
*   [https://www.youtube.com/watch?v=ZsHMHukIlJY](https://www.youtube.com/watch?v=ZsHMHukIlJY) (Kevlin Henney. Long, but really good)
