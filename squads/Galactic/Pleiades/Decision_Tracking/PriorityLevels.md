# Priority Levels

# Background

- WIDOW’s current priority rankings are only for bugs: Minor, Major, & Critical. This does not allow us to standardize our prioritization across bugs and feature requests.
- Minor, Major, and Critical don’t have enough granularity to help us prioritize the many items in our repositories.
- Below are the proposed priority rankings that will help guide future efforts in classification, prioritization, and expected responses.

# Priorities

## Priority 0: Outage / Safety

**Expectation**

Drop everything and work continuously to resolve. An outage means that there’s some piece of infrastructure that the community relies on is down. A P0 issue is _more_ urgent than simply blocking the next release.

**Example P0 issues**

- System-wide production outage
- Any issues impacting Mission Safety

**Response**

Nights & weekends up to 24/7 rotations depending on severity & impact

## Priority 1: Critical

**Expectation**

Critical item that should be assigned when created and jumps the priority queue to the top of the list. Continuous status updates.

**Example P1 issues**

- Deadline risk
- Critical use case failing for users with no workaround
- Data loss error
- Horrible user experience / user interface - weighted by the number of users affected and importance of use case
- Major performance regression
- Security-related issues (CVEs)

**Response**

Nights / OT / weekend depending on severity & impact

## Priority 2: Default

**Expectation**

Most tickets fall into this priority. These can be planned and executed by an appropriate team member. No special urgency is associated, but if no action is taken on a P2 ticket for a long time, it indicates it is actually just P3 / nice to have.

**Example P2 issues**

- Typical feature request
- User experience improvement
- A bug that affects some use cases but doesn’t make a component nonfunctional
- Minor performance issues

**Response**

Standard effort

## Priority 3: Nice to have

**Expectation**

- Nice to have improvements
- Small UI/UX tweaks
- Non-ideal performance

**Example P3 issues**

- Feature requests that are nice to have
- Tickets filed as a P2 that no one makes time to work on

**Response**

Standard effort when time allows.
