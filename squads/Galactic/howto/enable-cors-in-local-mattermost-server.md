### How to Enable CORS in Local Mattermost Server

## Purpose:

The pupose of this document is to show how to enable CORS in a local Mattermost Server in order to facilitate development.

## Steps:

1. On System Console search for oauth, go to Integration Management
1. Set Enable OAuth 2.0 Service Provider to true and hit Save
1. Go back to the team
1. Click on the App icon thing at top left and go to Integrations
1. Go to Oauth 2.0 Applications
1. Click Add Oauth 2.0 Application with the following details:
  - Is Trusted: Yes
  - Display Name: WIDOW
  - Description: WIDOW OAuth
  - Homepage: http://localhost:3000
  - Callback URL: http://localhost:8000/authorization/callback
  - Click Save
7. Copy Client ID to set value located in 282 in widow-python/widow/settings/base.py
8. Copy Client Secret and set value located in 283 in widow-python/widow/settings/base.py
