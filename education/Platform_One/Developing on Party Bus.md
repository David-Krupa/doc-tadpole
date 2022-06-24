<img align="right" src="https://github.com/braingu/tadpole/blob/master/images/TLP/TLPAmber.png">

# Quickstart for devs on P1
If you will be developing an app on P1, here are some things you should be aware of.

## Do you need a CtF?
Not all apps that use P1 dev tools will get a CtF under the C-ATO. If you intend to deploy onto Party Bus production, you'll need a CtF. You can read more about what that means for you as a dev on the [C-ATO doc]().

If you only need to deploy to staging, for example if you're building a proof of concept, or if you will deploy somewhere where the C-ATO isn't recognized, you'll still have to go through the P1 onboarding process described below, but won't need to go through the CtF-specific steps.

This document focuses on what devs need to care about. For PM info (submitting tickets, who to talk to to get things unstuck) see the [PMing on Party Bus doc]().

## P1 Onboarding
P1 onboarding has a few phases:

### 1. Customer Success / Tech Fit

Customer Success starts off with a tech fit meeting to make sure what you're asking for is supported. Be thorough when listing tech you need, and how you need to use it, because customer success isn't technical and won't know how to dig in.

For example, if you say you need S3, they may tell you that MinIO is available. However, it's not exposed outside of the cluster - your app can communicate with it, but your users can't. If you're asking whether a feature is available be very specific with what you want. Some features are available at a given IL and not at others.

After confirming that Party Bus can/is willing to provide support for your app, P1 customer success will work with your government POC to secure funding. Once that's done, you can move to the next step.

### 2. Mission Apps DevOps / Pipeline Setup

Once customer success signs off, P1 Mission Apps DevOps will set up pipelines for your team. You can do a couple things to make this easier and faster:

- follow the [P1 guidelines here](https://confluence.il2.dso.mil/display/P1PARTYBUS/Party+Bus+-+Project+Settings+Enforcement). In brief:
  - use an approved docker image as your base image (or the base for the last stage in a multi-stage build)
  - put your Dockerfile at the root of the project
  - keep `master` as the default branch
  - protect the master branch (only maintainers can push, and nobody can push to master)
- try to respond promptly to P1 questions. If the ticket gets stale, it will end up in the blocked column on the kanban board and will sometimes not get traction until it resurfaces

P1 will run an automated tool called Autobot that will do the following:
- set up a CI/CD pipeline for your microservices
- add variables into each CI/CD config that let it upload results to scanning tools (Fortify, SonarQube, Twistlock)
- set up a standard Kubernetes manifest that includes all of your services and a DB, if you requested one

A few notes:
- your manifests will live in a project under your team's subgroup called `<your prj name>-manifests`
- your CI/CD config will live in the [pipeline-products]() repo, and will be references from your projects' CI/CD settings
- at first, the scanning and unit test stages will be allowed to fail. The expectation is that the team addresses issues in the first few weeks and then the stages will block the pipeline if they fail

Once this work is complete, your app should be able to pass through the pipeline and deploy to staging. If you only care about staging, you can stop here.

### 3. Prep for CtF

If you want a CtF, look at the [CtF checklist](https://confluence.il2.dso.mil/display/P1CYBER/CtF+Checklist). Once you have completed all the steps, contact the security team using [this ticket template](https://jira.il2.dso.mil/servicedesk/customer/portal/1/create/51).

Most of the work to complete the items in the checklist will be done by getting your pipeline to pass all stages. You will need to create an architecture diagram and a System Security Plan that (among other data) lists the Impact Levels you will deploy to. If you intend to deploy to multiple ILs, make sure they are listed on this document.

SD Elements is an application that generates a set of security-focused questions based on the details of your application (what is the tech stack? do you use a database?). The list of questions will be tailored to the application - if you use a database, you can expect to be asked about how you prevent SQL injection, for example.

Answer the questions in as much detail as you can, and be specific. The cyber team that will review your answers is not technical, so make sure to explicitly connect any dots you can in the answer. If they don't understand how your answer addresses the question they'll put you back into "In Progress" stage, so try to be thorough on the first pass.

Cyber won't begin the assessment until everything is complete.


## General Tips
Party Bus prioritizes tickets over Mattermost messages. If you have a question or an issue, open a [Party Bus ticket on Jira Service Desk](https://jira.il2.dso.mil/servicedesk/customer/portal/1)

