Issue Lifecycle

# Purpose

This document outlines the different stages of the "lifecycle" of an issue for Team Pleaides as it goes from inception through being closed. The goal is to create a clear process and outline the requirements for an issue as it progresses through each stage of its lifecycle.

# Lifecycle

## Creating an Issue

- which tags we should use
  - NRE, Pleiades, Priority, etc

## Refinement

- Product backlog prioritization
- Refinement
  - weight, details, etc
- Other labels (blocked, refinement needed, UX/UI, other teams…)
- Selecting an issue for a sprint

## On Deck
These are issues that have been reviewed, planned for the sprint and placed in descending order by priority.
- These items have not had any work done on them EXCEPT for when an issue is blocked and been placed back in this category  
### **To Progress:** 
  - Read the issue and ensure that you understand what is required. Follow up with stakeholders if more information is required.
  - Add yourself as an assignee.
  - Create a branch with the issue number starting the branch name. (frex: `1533-twilson-tactical-chat`)
  - Move the issue from the `Lane: On Deck` column to the `Lane: Dev` column.

## Dev
These are the issues that are currently being worked on. There should not be more than one issue in development for each developer on the Project.
### **To Progress:** 
  - Consider your approach. Before writing any code, have a strategy for what you are doing. Consider the size of the issue you are working on. Depending on the complexity, you could spend the majority of your time investigating, researching and planning your approach.
  - Be thorough in your documentation. Leave comments explaining the decisions you made while doing this work. Remember you may not need to return to this file for 6 months.  Will Future You remember all the super smart thoughts Current You had?
  - Create an MR to merge the associated branch into master. 
    - Start the name of the MR with `#<issue number>` to associate the MR with that issue. (frex: `#1533: Tactical Chat, part 1`)
    - Write a detailed description of the work you did. If time allows, try to explain your decisions on each file you worked within.
    - Assign yourself as the Assignee
  - Monitor the pipeline for your branch. When the pipeline has passed, post a link to the MR in [#darkmode-sgal-widow-dev](https://braingu.slack.com/archives/C011QBDCV5J).
  - Move the issue from the `Lane: Dev` column to the `Lane: Code Review` column.

## Code Review
- These issues are ready for peer review.
- As an assignee:
  - As you move an issue to Code Review, note other issues in the same column. If any are in need of a reviewer, consider reviewing it to keep the process moving.
  - Get up. Take a walk. Come back and sit down and review your own code.  All changes you have made will be visible in the diffs. Save reviewers time if you find problems. Leave comments for others to review. Ask for others' thoughts on the solutions you found.
- As a reviewer: 
  - Assign yourself as a reviewer on the MR. 
  - Reply to the Slack thread where the issue was posted. 
  - Check the pipeline for the branch. If it is not green, the MR fails code review.  Mark the MR as `Refinement Needed` and notify the developer.
  - Run the test suite and check for error messages or warnings in the tests. In an ideal world, we'll have none of those.
  - Read the changes in the MR itself. Do they make sense? Did the dev explain themselves in the MR and in their comments?
  - Check for debugging `console.log()`s and commented out code.
  - Approve the MR, or mark it as `Refinement Needed` and return it to the developer.
-   **To Progress:** 
  - Merge the changes into `master`.
  - Observe the `master` pipeline. If it has successfully deployed to `staging` you may proceed. If not, begin investigation on the pipeline.
  - Move the issue from the `Lane: Code Review` column to the `Lane: QA - STG` column.

## QA Staging
- **To Progress:** 
  - Check to ensure the changes have arrived at [widow staging](https://widow.staging.dso.mil/#/).
  - Check the behavior and presentation of the changes and any adjacent features on [widow staging](https://widow.staging.dso.mil/#/)
  - Post a notification on  [#darkmode-sgal-widow-dev](https://braingu.slack.com/archives/C011QBDCV5J) that you will be releasing new code into production.
  - Open the `master` pipeline. If the behavior and presentation of the changes on Staging are as expected, click the appropriate release button.  This is almost always `release patch`.

  - Move the issue from the `Lane: QA - STG` column to the `Lane: QA - PRD` column.

## QA Production
- **To Progress:** 
  - Check the behavior of the changed code and adjacent code on [widow production](https://widow.apps.dso.mil/#/)
  - As you finalize your QA, make a record of the changes. This can be screenshots for simple changes or video for more complex changes.
  - If the behavior and presentation of production are as expected, post the record of the changes to the Replay thread for the sprint on [#darkmode-sgal-widow-dev](https://braingu.slack.com/archives/C011QBDCV5J). 
  - Move the issue from the `Lane: QA - PRD` column to the `CLOSED` column.


## Closed
  - Add the `Lane::User Acceptance` label to the issue to flag for UAT.
  - Jinoo tests in production, gives it thumbs up



