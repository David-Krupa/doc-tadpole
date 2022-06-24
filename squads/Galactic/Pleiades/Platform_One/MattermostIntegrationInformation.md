# Mattermost Integration Information

## Purpose

The purpose of this document is to provide information related to Mattermost (MM) authentication, how Puckboard is able to integrate with P1 MM, how that compares with Widow’s MM integration, and information about potential courses of action to enable Widow MM to work properly.

## Bottom Line Up Front

Widow Integrated chat consists of two separate components:

1.  The backend component is responsible for the following:
    1.  Creating new mission-specific channels when new missions are created
    2.  Adding Widow users to the mission channel when they open a mission
2.  The front end component provides a subset of the functionality that is provided by the official Mattermost client:
    1.  Send chat posts
    2.  Receive chat posts
    3.  Respond to chat posts via threads
    4.  Create DM and group messages, as well as private channels if a user tries to create a DM with more participants than the eight-person (including the user) limit that MM enforces
    5.  Rename private channels created by the user
    6.  Update user status
    7.  Receive updates to other users’ statuses, new channel creation, new messages, new "@" messages to the user, all user broadcast messages, and other "push" events from the server

In order for the Widow Integrated Chat client (or any full-featured chat client) to work with the P1 MM server we need the following:

1.  P1 to provide applications the ability to obtain MM authentication credentials from the P1 MM server
2.  P1 to enable authenticated apps to use the MM servers APIs and websockets

## Background

#### Mattermost Authentication Requirements

Mattermost authentication is documented here:
<https://api.mattermost.com/#tag/authentication> It shows that a successful login to a Mattermost server returns a token that is used to authorize subsequent API requests to the server.

On P1, this token is obtained via a successful login to https//:chat.il4.dso.mil via the "Baby Yoda" login page. A login request is shown in the image below. Note that even though I went to the IL4 Chat page in the browser, I was redirected to login.dso.mil since I had not already completed an SSO login.

A successful login is followed by a redirect to the originally requested chat.il4.dso.mil page at which point we receive the necessary MM credentials via HTTP cookies. The value referred to as a "token" in the MM authentication document linked above is received as a cookie and is shown in the following image with the name "MMAUTHTOKEN"

Additional values are set in the cookie and it is saved to the browser’sstorage for this web page.

All of this cookie information including the MMAUTHTOKEN is sent as a Request Header for calls to the MM server’s API. The image below shows a message post request to IL4 MM chat; note the underlined MMAUTHTOKEN.

#### What About Puckboard?

Puckboard creates channels and makes posts via the backend. This can be done by using a MM Bot on the backend which has credentials to make API calls as itself. The fact that it is posting as the bot can be seen in the user name of the bot that made the post in the demo video that was posted here: <https://chat.il2.dso.mil/platform-one/pl/9kor1jht37nczp9m5oi43uusoa>

Additionally, the demo does not show two-way communication between MM and the Puckboard application. This is required for a chat application.

The bottom line is the Puckboard Bot has the credentials to interact with the MM API; however, it interacts as itself, not another user.

Additionally, these credentials are safe on a backend server. Static credentials on a front-end client could be exposed to a malicious user.

#### Widow MM Integration

MM integration in Widow consists of a chat client that lets a user send and receive posts as themself as well as send threaded responses. Additionally, a user can create a direct message, group message, or private channel. They can also rename the private channel.

This functionality works correctly when interacting with a MM server in a container on the developer’s machine.

Widow’s MM client is built on top of the "mattermost-redux" package provided by the Mattermost development team. They state "We encourage you to use mattermost-redux to power your own Mattermost clients or integrations." The Widow MM client provides a custom user interface that interacts with the networking code provided by this package.

## Problem

The problem encountered with integrating Widow Integrated Chat and P1 Mattermost is summarized below

1.  Access to Mattermost APIs and websockets is required to build a MM chat client.
2.  Mattermost credentials are required for access to Mattermost APIs and websockets.
3.  Apps other than Mattermost do not have an approved way to retrieve full MM credentials for MM users.

#### Official P1 MM Options

Justin Lowry stated that Widow has two options:

**Option 2 - Webhooks:**

Webhooks are not an appropriate solution to Widow MM integration as shown in the documentation for Incoming and Outgoing webhooks is located here:

- <https://docs.mattermost.com/developer/webhooks-incoming.html>
- <https://docs.mattermost.com/developer/webhooks-outgoing.html>

There are several issues that prevent incoming webhooks from providingthe functionality Widow needs. One of them is shown below.

For outgoing webhooks, the documentation states that we can "Use outgoing webhooks to post automated responses to posts made by your users." Basically, a bot can look for incoming messages that follow a certain format and respond to them automatically. This is also not appropriate for a chat client.

**Option 1 - Widow MM Server:**

Since P1 will not provide API access, creating a Widow MM server (WMSS) appears to present the best option for achieving complete integration between the IC client in Widow and a Mattermost server.

Steps:

1.  Create IL4 Widow MM Server (WMMS)
    1.  Option: create pre-prod server that is accessible via the Widow staging for testing
2.  Expose WMMS via URL
3.  Transition Widow MM to the new WMMS
    1.  Create accounts for existing Widow MM users
    2.  Provide "redirect" information for items that cannot be transferred
4.  Update Widow IC to access WMMS
