# Deployment Guide

## Purpose

A place to include the process/steps for updating the deployments as well as the version numbers.

- Deployment steps
- Authorized personnel to issue a deployment
- Who verified staging
- Version deployed / which network (link document to track)

## Understanding Classification Levels

Below are the different classification levels and environments that we deploy WIDOW to. The images below that are helpful to understand Impact Levels.

- IL4
- IL5 = NIPR
- IL6 = SIPR
- JWICS

# Low Side Deployments

Low side deployments mean deploying to unclassified networks - in WIDOW’s case to IL4 and IL5.

To deploy to IL4 / IL5:

- Master branch will automatically push to both of these when you "press play" to release to production
- IL4 and IL5 are essentially the same and use the same URL, but are just deployed on different networks
- Remember to "press play" to release a patch or a minor release in almost all cases. Releasing as a major version automatically triggers a CtF review process.

# High Side Deployments

High side deployments mean deploying to classified networks - in WIDOW’s case to IL6 (SIPR) and JWICS.

### Deploying high side is a very manual process

To deploy to SIPR / JWICS, folks at Platform One actually have to handle
a number of manual steps:

1.  Grab release images
2.  Burn those onto a DVD
3.  Take a snapshot of the database
4.  Install to a network
5.  Do some basic tests to see if the deployment worked
6.  If it didn’t, they need to revert back to the last working version

### Important to keep in mind!

Be cautious about updates to be courteous of their time

- **Do NOT push multiple updates per day unless it’s critical**
- Once a week is acceptable typically
- During exercises: once a day
  - They don’t track version numbers, they blindly do what you ask of them
- If you make a mistake in sending them the wrong version number, they won’t catch it
- They will simply revert the database to the last working version when the deployment fails

### Platform One folks to know

People who are in charge of high side deployments:

- Will Townsend: in charge of the process
- Goran Osim: burns the DVDs for Will
- They are in Mountain time and are usually kicked out of the SCIF by 1600-1700 MT
- During Northern Edge 21, the following people helped out with the process because Will was out of town:
  - Jason Crothers
  - Patrick Pryde

### Communication method

Mattermost channel to communicate about high side deployments:
<https://chat.il2.dso.mil/platform-one/channels/topic---classified-delivery>

### How to request a high side deployment

Procedure:

- Once an MR has been deployed to production, grab the version tag from Gitlab
  - Tags live at the following URLs:
    - <https://code.il2.dso.mil/platform-one/products/widow/widow-react/-/tags>
    - <https://code.il2.dso.mil/platform-one/products/widow/widow-python/-/tags>
- Copy and paste the version tags in the Mattermost channel and tag the folks who will be handling that to ask them to update WIDOW (typically Goran & Will)
- Typically they upgrade both SIPR & JWICS - if you need only one of those updated, you will need to specify that

Example message

## Dangerous POC for deployments

We should have a single POC for Mattermost contact and deployment coordination:

1.  Jinoo: Main POC
2.  Jason: backup 1
3.  Richard: backup 2

## Misc Information

Future improvement on our side: find a way to track compatible versions between React & Python (icing on the cake).

Differences between networks:

- Map URLs are different between NIPR & SIPR/JWICS
- We don’t have a firm data contract between us and P1 - they could change the data they use on any/all networks without notifying us
- However, manifests and environment variables should be the same between networks
  - If we ask them to set an env var in IL4, it should work the same up the chain to other networks
