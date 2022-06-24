## ADR 1 Version 0.0.2

## Drafted: 3.22.21
## Approved: 5.3.21
## Last Updated: 11.1.21
## Effective Date: 5.3.21
### Author: Ian Mullins, Business Analyst; Chris Antonio, Learning + Development Manager

* [Key Insights](#key-insights)
* [ADRs Y-statement](#adrs-y-statement)
* [Problem Statement](#problem-statement)
* [Gains](#gains)
* [Alternatives Considered](#alternatives-considered)
  + [Why](#why)
  + [Problems with the Tribal Knowledge non-construct](#problems-with-the-tribal-knowledge-non-construct)
  + [Enable Gurus to adopt improvements to the company at scale](#enable-gurus-to-adopt-improvements-to-the-company-at-scale)
  + [What](#what)
  + [How](#how)
  + [Who](#who)
  + [When](#when)
  + [Where](#where)
* [Conclusion](#conclusion)
* [Status: PROPOSED](#status-proposed)


## Key Insights

* Tribal knowledge transfer works at 10 employees, not at 100 -- ADRs provide context and clarity surrounding decisions at BG

* Examples of things we might make ADRs for:  "Adoption of Rippling as BrainGu's HR information system", "Education budget improvement proposal", "Adoption of the Squad Model at BrainGu"

* The Board will act as the decision-making body for newly proposed ADRs


## ADRs Y-statement

As BrainGu continues to grow by leaps and bounds, we have identified the increasing need to document our decisions, record process and policy, and create a mechanism for submitting and group-vetting changes to the company. We have determined that the ADR model widely used in our industry is a rather elegant way to capture and document improvements to The Gu. If we hope to stay on the same page with one another, and if we want the org to continue to improve upon itself over time, we need a robust way to record and change our policies.


## Problem Statement

BrainGu is becoming a more complex and multi-layered organization. As we grow, so does our diversity of thought and our need to document company decisions. **Enter the Architectural Decision Record (ADR).**

## Gains

Much of our early process and procedure was tribal. Rhyme and reason became less situational and more encoded in practice over time. As we bring on new talent and we start to teach them how to do things, it’s important that we are able to offer a transparent and consistent experience. Being able to refer to ADRs allows everyone to be on the same page.

ADRs also open improvement of our policies and procedures up to a more democratized and structured process. As an example, If an employee has a good idea on how to make an improvement to a process, they can draft and submit an amended ADR to be considered by the leadership. If it is supported, it will be adopted and the record of that evolution is well-documented and transparent for future Gu-generations.



## Alternatives Considered

### Why

### Problems with the Tribal Knowledge non-construct

From the founding days of the company, we have struggled with sufficient knowledge capture and share. Our employees have just been so busy getting their hands deep into the work!

*   When we had 10 employees it was quite easy to agree on common sense policy and procedure. The MO of the olden days was to disrupt technical work as little as possible.
*   Today, we are going on 70 full time employees, and pushing rapidly toward BrainGu at 175.
*   It no longer suffices to introduce New Gu to the company with a Tribal Knowledge Dump.
*   Additionally, there are a lot more policies and procedures to be aware of for the average employee today than there were in the past.


### Enable Gurus to adopt improvements to the company at scale

*   The ADR model will "open source" BrainGu's culture so that employees will be able to propose improvements to and get buy-in across the company. Decisions about which direction to take the company, including decisions based around policy and procedure will be codified in an ADR. Previously, no such mechanism existed.


### What

ADRs should have the following general construct:

**Title: **Name of the Decision

**Version:** “0.0.2”

**Key Insights:** Pull TL;DR info front and center -- Because we intend for the ADR system to be universal at BrainGu, many stakeholders will need to skim lots of ADRs, and others will need to read and understand deeply.  In the Key Insights section, use descriptive and informative bullet points to provide an MVP of the ADR for a speedy reader! 

**Y-Statement/Summary:** Our If/Then Statement. We will include a brief of the problem being solved and the solution hypothesis here and we will elaborate more in the “Why” section.

**Problem Statement:** The author of the ADR or ADR-Amendment should use this section to provide context for the problem that the ADR will solve. This section describes the forces at play, including technological, political, social, and project local. These forces are often in tension, and that should be identified as such. The language in this section should be value-neutral and should be focused on simply describing facts.


**Gains/Consequences:** This section should list out the pros of making a particular decision a certain way. The section should also describe the resulting context, after the decision is applied. All consequences should be listed here, not just “positive” ones. A particular decision may have positive, negative, and neutral consequences, but all of them affect the team, company, or project in the future.


**Alternatives Considered:** This section is for listing out the other potential solutions that were considered or should be considered.


**Why:** Why is the decision being made?


**What:** What do the concretes of the decision look like?  What will the consequences of the decision be (positive, negative, and neutral)?


**How:** How will the decision be implemented? — this section is worthy of a lot of detail


**Who:** Who will implement the decision? Who will be responsible for knowing it? Who does the decision affect?**


**When:** What is the Execution Date? The Effective/Approved Date?


**Where:** Where will the decision record be stored and published for employee reference?


**Conclusion:** A summary statement (if applicable) that wraps up the thoughts of the author and summarizes the actions to be taken as a result of the decision.

**Status:** A decision may be **proposed** if the decisions stakeholders haven’t agreed on it yet, or **accepted** once it is agreed upon. If a later ADR changes or reverses a decision, it may be marked as **deprecated** or **superseded** with a reference to its replacement.


### How

1. A problem or improvement to how we do things is identified
2. An ADR is drafted and submitted to the relevant stakeholders
3. The relevant stakeholders discuss and deliberate, making changes and reaching consensus
4. The ADR is amended to reflect any committee changes
5. The ADR is socialized to the population of employees affected by the ADR and comments are requested
6. Employee comments are addressed and the ADR is modified if necessary
7. The ADR is submitted for approval
8. The ADR is adopted and published on the company TadPole Wiki
9. The ADR goes into effect on the scheduled date and time
10. *Amendments* an amendment to an existing ADR follows the same process as above.


### Who

As an initial jump, all ADRs will be considered and approved or rejected by the Board.

Because this model of documentation has wide application implications, we expect for ADRs to affect everyone in the company in some capacity. A technical ADR might only affect Technical Staff, while an HR ADR might only affect HR staff and how they do their jobs. These are just broad examples.

It is important to note that once we have adopted an ADR, that ADR then becomes the official guide on how we do whatever the ADR is about.

**Note:** It is the responsibility of the author of the Amended ADR to document the list of changes when making an amendment to an existing ADR.


### When

Once Adopted, this ADR for creating ADRs will go into effect on the date of approval.


### Where

All ADRs will be published to the company Tadpole Space. Linkbacks to the page will be embedded into each ADR as well as a full edit log of changes.


## Conclusion

In the long-term, we hope that this model for ADRs will serve as an elegant and effective way to organize ideas, adopt and change policy, augment the onboarding experience at the company, and provide greater context for what is driving our decisions, so that our employees feel included and heard.


## Status: APPROVED
