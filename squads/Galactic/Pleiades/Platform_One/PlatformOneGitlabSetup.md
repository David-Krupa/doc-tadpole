# Platform One & GitLab Setup Procedure

## Platform One Setup

- Set up an account for PlatformOne using BrainGu email address at this link: <http://login.dsop.io/>
  - Affiliation = Contractor
  - Pay Grade = N/A
  - Company Name = BrainGu

## GitLab Setup

- Ask someone to file a ticket for you to receive access to the WIDOW project on GitLab
  - [<u>https://jira.il2.dso.mil/servicedesk/customer/portal/73/create/419</u>](https://jira.il2.dso.mil/servicedesk/customer/portal/73/create/419)
    - Application URL
      - [<u>https://code.il2.dso.mil/platform-one/products/widow</u>](https://code.il2.dso.mil/platform-one/products/widow)
    - What Environment/s do you need?
      - IL2
    - Approver/s
      - Jinoo Jain
- Visit GitLab to create an account: <https://code.il2.dso.mil>
- Ask Jinoo add you to the WIDOW group
- You should now be able to access the two main WIDOW repositories located here:
  - Frontend: <https://code.il2.dso.mil/platform-one/products/widow/widow-react>
  - Backend: <https://code.il2.dso.mil/platform-one/products/widow/widow-python>

## Cloning the repos on your local machine

- Setup Personal Access Token on GitLab
  - Click your user icon on the top right of the screen → Setting
  - Click Access Tokens on the left navigation bar
  - Add a personal access token
  - **Make sure to copy the access token to somewhere safe before leaving the page!**
- Git clone these two repositories from Gitlab
  - $ git clone &lt;’Clone with HTTPS’ URL from repo&gt;
    - Username: enter your GitLab username
    - Password: enter your personal access token copied from the last step

## Steps to run WIDOW locally

- Open Terminal
- Navigate into the widow-python directory
- (Big Sur only) - Install homebrew and then run `brew install postgres`
- Run the following commands to start the backend:
  - $ git pull
  - $ python3 -m venv venv
  - $ source venv/bin/activate
  - $ export SYSTEM_VERSION_COMPAT=1 (Big Sur only)
  - $ ./start-dev.sh
- In a new terminal window, navigate into the widow-react directory
- Check if you have node installed on your machine with the following command:
  - $ node -v
- If you don’t have node installed on your machine, download Node here: <https://nodejs.org/en/download/> (v.12.20.0)
  - After downloading, run the previous command to ensure it is properly installed. It should output the current version of Node.
- Run the following commands to start the frontend:
  - $ git pull
  - $ npm install
  - $ ./start-dev.sh missioncommander
- The last command should open up WIDOW in your default browser
  automatically (you might need to give Terminal permission to do so)

## **Change Log**

| **DATE** | **AUTHOR**     | **CHANGE DESCRIPTION**                       |
| -------- | -------------- | -------------------------------------------- |
| 12/14/20 | Jinoo Jain     | Initial draft                                |
| 12/29/20 | Matt Shaver    | Updated the links for the repos              |
| 1/4/21   | Matt Shaver    | Added details to Platform One Setup          |
| 1/27/21  | Noopur Shreyas | Added red color to copying access token step |
| 1/30/21  | EJ Perrault    | Added the change log                         |
| 3/3/21   | Chris Walz     | Add node version and Big Sur caveats         |
| 03/16/21 | Justin Trout   | Updated run command for front-end            |
| 4/29/21  | Jinoo Jain     | Migrated to Confluence wiki                  |
