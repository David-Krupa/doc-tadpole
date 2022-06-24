# Developer Work Flow

## Purpose

Document Widow Continuous Development Workflow.

## Prerequisites

Developers must have access to "Widow Staging" which is the Widow
application at the staging URL <https://widow.staging.dso.mil/#/> This
is required so that developers can test their changes

Developers can obtain access to Widow Staging by submitting a Platform 1
"Mission Application Access" ticket at
<https://jira.il2.dso.mil/servicedesk/customer/portal/1/group/38?groupId=38>.
An example of the request details is shown below.

> **For which application, are you requesting access?**
>
> Access To Widow Staging URL
>
> **URL**
>
> https://code.il2.dso.mil/platform-one/products/widow/widow-react
>
> **Environment/s**
>
> IL4
>
> **Comments**
>
> Hello, I need to be able to run the Widow application at https://widow.staging.dso.mil/ for testing.
>
> **Approver**
>
> Matthew Shaver

**Note**: it takes approximately half a workday for the ticket to be
resolved. You will receive updates on your ticket at your email address.

## Continuous Development Workflows

### **<u>Issue Resolution, Bugfix, Hotfix Work Flow</u>**

**Purpose**: This is the normal workflow developers will use to create code to resolve issues. It encompasses any changes made to the application’s code regardless of issue priority.

**Flow**:

- **MASTER** → Create an Issue Branch → Develop on Local Machine → Push development work to Issue Branch → Submit MR to **MASTER** → Review → Approval → Merge to **MASTER** → Verify that the issue has been resolved at the staging URL once the Master pipeline has been completed. A successfully completed pipeline is shown below:

- **NOTE**: The **MASTER** branch is not available at the staging URL until the "Deploy to Staging" portion of the **MASTER** branch pipeline is completed successfully.

### **<u>Post Master Merge Steps</u>**

After an issue branch has been merged to **MASTER** the following process happens:

1.  The P1 pipeline runs on **MASTER** branch
2.  Master pipeline completes successfully
3.  The branch's creator should change the branch’s status to QA:Staging on the sprint board
4.  Team member selected according to the "Tiered Approval System" section QAs the feature at the staging URL. That team member provides feedback to the developer or QA approval as appropriate.
5.  The team member that did the QA approval in step 4 pushes the "release patch" button
6.  The same team member posts a message in the \#iig-widow-dev channel indicating the feature released to production
7.  The same team member changes branch status to QA:Release on the sprint board
8.  Product Manager QAs feature in production. Additionally, original QA and dev should attempt to QA the feature in production if able.
9.  Finally, the feature developer announces in the \#iig-widow-dev Slack channel that the feature is available in production if applicable. The announcement post should include a picture or video of the feature if it resulted in visible changes to the app.

### **<u>Tiered Approval System</u>**

The person performing the Staging QA, Push to Production, and Changing Branch Status to QA steps is determined by a tiered system. The goal of this system is to avoid single points of failures and blockages in the process of making development work available in production.

The QA and release items in "Post Master Merge Steps" fall to the next available level if the previous level is not available.

1.  Product Manager, Team Leads
2.  Developer Senior
3.  Developer Mid
4.  Developer Associate
