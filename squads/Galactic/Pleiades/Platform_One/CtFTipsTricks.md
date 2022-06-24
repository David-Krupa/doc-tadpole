# CtF Tips & Tricks

## SDElements

- Puckboard shared their CtF SDElements responses to help out other teams, this is a handy reference when filling out your SDElements:
  - [Message on IL2 MM](https://chat.il2.dso.mil/platform-one/pl/71f99bks97gjfy6iejtriu3fhe)
  - [Actual documentation on IL2 Confluence](https://confluence.il2.dso.mil/display/TRON/SD+Elements+Reference)

## Coordination with P1

- When filing tickets with P1 regarding CtF, you should include CtF in the title of your ticket because they have a fast track for CtF tickets in their triage process
- If you don’t have one already, I would recommend asking P1 to set up a channel specifically for your CtF process. This channel was a very handy spot to communicate directly with the relevant parties at P1 regarding the process. The title of the WIDOW channel is CtF - P1 - ABMS - WIDOW

## Pipelines

- All your pipelines need to be working (all stages need to be green)
  - The two exceptions are the E2E test and Pen test steps
  - However, P1 requires that you do have some form of E2E tests working, even if you just run them locally. WIDOW uses Cypress for our E2E testing framework.
- For the Fortify findings, you will need to address the High and Critical issues that are labeled "Suppressed" and "Hidden". (You can see these by going to the "PROFILE" button on the top right in Fortify and checking the boxes")
  - You need a comment on those issues found verifying they are not an issue or they are False Positives
- For SonarQube findings, whitelist issue documentation should include the information mentioned in this document <https://braingu.atlassian.net/l/c/hetMZg3b>

# Path to CtF

_Document templates for product teams who are in the CtF process are found in this repository._

## Prior to onboarding with Cybersecurity a team should:

1.  Submit an onboarding questionnaire.
    - NOTE: Until further notice, drop the completed questionnaire in the
      [Guild - Cyber](https://chat.il2.dsop.io/platform-one/channels/team---cyber)
      MM Channel.
2.  Already have the product repo established
3.  Already have the product pipeline(s) established.

## All product teams must comply with the below in order to achieve a Platform One Certificate to Field (CtF).

##### **The CtF process consists of 4 phases:**

1.  ONBOARDING
2.  WORK
3.  ASSESSMENT
4.  FINAL CtF REVIEW

**NOTE:** Rate of completing the Path to CtF will be dependent on product team and willingness to complete CtF work.

## ONBOARDING

For a product team to be on-boarded, they must have a completed a pipeline build and deployed within GitLab CI. Next, the team will fill out the Onboarding Questionnaire and request onboarding with the Cybersecurity team. Cybersecurity will prepare the SD Elements (SDE) survey for the product team, link Fortify/SonarQube to SDE, create a chat channel to facilitate Path to CtF communications, and schedule the onboarding meeting. The Product team Anchor and PM must be present for survey to be completed. Survey should take no longer than 30 minutes to 1 hour to complete. Once the onboarding meeting is complete, the Product Team will move into the WORK phase.

## WORK

During this phase, the Product Team will work on their product. In order to move on to the ASSESSMENT Phase, the Product Team must complete the Assessment Readiness Self Eval section of CtF Checklist (items 3-6). This includes completion of:

- Document Preparation • GREEN Pipeline • Product Scan Reviews • SD Element Tasks

Upon completion of the above, the Product team will notify Cybersecurity via the Product CtF channel that the Product is ready for the ASSESSMENT Phase.

## ASSESSMENT

Upon notification that the Product Team has completed the Assessment Readiness Self Eval, the Cybersecurity team will review the documents, pipeline, scans, and SDE tasks to identify and notify the Product Team of any issues. Issues identified by the CyberSecurity team will need to be addressed by the Product Team before moving on to the next phase.

Once all issues have been addressed, the Cybersecurity team will hold an internal review with the Platform One ISSM. If the ISSM is satisfied with answers/mitigations in place at the time of the review, the product will advance to the next phase in the Path to CtF. The ASSESSMENT Phase is estimated to take 2-3 weeks to complete.

## FINAL CtF REVIEW

As the final check prior CtF issuance, a mitigation plan MUST be in place if there are still risks associated with the application.

**NOTE:** The CISO, CTO, ISSM, ISSO, Product & Platform Medics will be present for this review. During the Final CtF Cyber Review the following will be reviewed accomplished:

- Fortify (SCA) • SonarQube (SCA) • TwistLock (DAST) • Cypress (E2E
  Test) • OWASP ZAP (Pen Test) • Unit Test • SDE Tasks • Mitigations

**Once the CISO is satisfied that all NIST security controls have been met, mitigations have been put in place if necessary, and the application has sufficiently adhered to the standards of the C-ATO, they will issue a CtF.**
