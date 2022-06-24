# What to do Once You Have Platform 1 (P1) Access

## Purpose

Document what a developer should do once they have received access to P1.

## Request Access to Pipeline Tools

In order to resolve pipeline issues, you will need access to the P1 pipeline tools.
Submit a ticket to request access for each of the appropriate project(s) SonarQube code quality, SonarQube dependency, and Fortify checks for each of the Repos listed under the Genisys project.

1. Click on the [Mission Application Access](https://jira.il2.dso.mil/servicedesk/customer/portal/73/create/419) link at the [P1 Customer App Support portal)](https://jira.il2.dso.mil/servicedesk/customer/portal/73/group/112) portal.

2. Enter all the applications you need access to on one line. i.e. **SonarQube Code Quality, SonarQube Dependency, Fortify, ArgoCD**

3. Input the url of the specific project's Gitlab repo page into the "Application URL" field.  You will need to fill out a new form for each repo

3. Be sure to select all of the environment you have access to (IL2, IL4, etc)

4. Type **matt.shaver** in the "Approver/s" field and select Matt Shaver as the approver, and then click the "**Create**" button.

## Cloning Repos 🚧

### Personal Access Token

You'll need a Personal Access Token in order to checkout GitLab repositories. Visit this URL to create one:

https://code.il2.dso.mil/-/profile/personal_access_tokens

_Note: you'll want to replace the `il2` above with whatever environment is relevant_

You can fill the checkboxes out as follows:

![Screen Shot 2022-01-14 at 1 27 00 PM](https://user-images.githubusercontent.com/97055993/149566715-205810f2-f1d9-42b7-95c0-093ec3820eae.png)


