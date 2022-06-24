# Resolving SonarQube Pipeline Issues

- [Purpose](#ResolvingSonarQubePipelineIssues-Purpos)
- [SonarQube](#ResolvingSonarQubePipelineIssues-SonarQ)
  - [Dashboard Locations](#ResolvingSonarQubePipelineIssues-Dashbo)
  - [Issue Resolutions](#ResolvingSonarQubePipelineIssues-IssueR)
  - [Common Issue: Cognitive Complexity](#ResolvingSonarQubePipelineIssues-Common)
- [SonarQube Dependency Checks (SQDC)](#ResolvingSonarQubePipelineIssues-SonarQ)
  - [Dashboard Locations](#ResolvingSonarQubePipelineIssues-Dashbo)
  - [Issue Resolutions](#ResolvingSonarQubePipelineIssues-IssueR)

## Purpose

The purpose of this document is to provide guidance for resolving issues found by the P1 Pipeline, and when necessary, provide issue justifications that will satisfy the CTF process.

## SonarQube

Sonarqube searches for and reports code-quality issues. For example, the following are some issues identified previously in Widow React and Python. Note that there is a link icon in the upper right that can be used to refer to a specific issue.

###### Example React SonarQube Check Issue
![Example React SonarQube Check Issue](https://user-images.githubusercontent.com/14915286/150436472-b79647f5-2d72-4595-973a-9e9a5d19d955.png)

###### Example Python SonarQube Check Issue
![Example Python SonarQube Check Issue](https://user-images.githubusercontent.com/14915286/150436743-047cd7b3-bf0b-436d-a7a8-cd56437f68d4.png)


#### **Dashboard Locations**

SonarQube results for the most recent branch can be seen at SQ dashboard via the links below:

React: <https://sonarqube.il2.dso.mil/dashboard?id=platform-one-products-widow-widow-react>

Python: <https://sonarqube.il2.dso.mil/dashboard?id=platform-one-products-widow-widow-python>

#### **Issue Resolutions**

Resolve the issue if able by solving the identified problem, otherwise do the following:

First, ensure the affected branch was the most recent one to complete SQ checks. This will ensure that branch’s issue is displayed on the SQ dashboard.

Then, go to the appropriate SQ dashboard and click on the "Issues" tab near the top of the page.

###### Click on the Issues tab to see issues for the most recently run branch
![Click on the Issues tab to see issues for the most recently run branch](https://user-images.githubusercontent.com/14915286/150436786-33529584-c307-4422-84b1-00d51f42283d.png)

After clicking the "Issues" link, you should see the identified issues similar to the images below. Mark the issue as "Confirmed", assign yourself to it, and then add a comment stating why the request should be whitelisted.

Next, submit a "Pipeline Exception Request" at <https://jira.il2.dso.mil/servicedesk/customer/portal/73> to whitelist the issue if the issue is a false positive.

Use "Whitelist SonarQube Finding" as the title. If this request is being made as part of a CTF, prefix "CTF:" to the title like this "CTF: Whitelist SonarQube Finding"

For "What project is this in reference to?" use either "<https://code.il2.dso.mil/platform-one/products/widow/widow-react>" or "<https://code.il2.dso.mil/platform-one/products/widow/widow-python>"

Here is a sample description. Note that it includes a link to the specific issue in SQ.

> <table>
> <thead>
> <tr class="header">
> <th><p><em>Hello,</em><br />
> <em>Please white-list this SQ complexity finding:</em><br />
> <a href="https://sonarqube.il2.dso.mil/project/issues?id=platform-one-products-widow-widow-react&amp;issues=AXuESaFdOWhY_cB1nKy2&amp;open=AXuESaFdOWhY_cB1nKy2"><em><u>https://sonarqube.il2.dso.mil/project/issues?id=platform-one-products-widow-widow-react&amp;issues=AXuESaFdOWhY_cB1nKy2&amp;open=AXuESaFdOWhY_cB1nKy2</u></em></a></p>
> <p><em>branch: mui-time-fix</em></p></th>
> </tr>
> </thead>
> <tbody>
> <tr class="odd">
> <td>Example body for SQ Check whitelist request</td>
> </tr>
> </tbody>
> </table>

Make sure you include the branch name so that the P1 tech that resolves the ticket can run the branch to confirm that their resolution works if they want to. Each push to a branch in Gitlab results in SQ running a new check, and the results of one branch’s check will overwrite the results of the previous SQ check. Including the branch name connects the branch to the ticket.

Also, include a picture of the issue from SQ to help specify the applicable issue.

#### Common Issue: Cognitive Complexity

An issue with SQ version prior to 9.x results in an inability to properly calculate cognitive complexity for React functional components. This is a known issue that is documented here: <https://community.sonarsource.com/t/sonarqube-counts-incorrect-cognitive-complexity-for-react-functional-components-bug-no-functionality/30852/17>. Resolving this type of issue involves first reviewing the identified component and attempting to logically reduce its complexity while following React best practices. However; if that is not possible, submit a whitelist request as shown above.

## SonarQube Dependency Checks (SQDC)

SonarQube dependency checks look for vulnerabilities in packages used by a project.

###### Example React Dependency Check Issue
![Example React Dependency Check Issue](https://user-images.githubusercontent.com/14915286/150436948-54231030-d6d2-4c2f-8229-4c34940a44bd.png)
###### Example Python Dependency Check Issue
![Example Python Dependency Check Issue](https://user-images.githubusercontent.com/14915286/150436968-8dee710d-ee86-4081-8545-f682aa188054.png)


#### **Dashboard Locations**

The SQDC results for the most recent branch can be seen at the links below:

React: <https://sonarqube.il2.dso.mil/dashboard?id=platform-one-products-widow-widow-react-dependencies>

Python: <https://sonarqube.il2.dso.mil/dashboard?id=platform-one-products-widow-widow-python-dependencies>

#### Issue Resolutions

Resolving a dependency check issue is a multifaceted process based on the type of issue.

**Issues with** react-scripts

For React issues, run npm ls \[package name\] to determine where and how the package is used. Many of the issues SQDC identifies with the react project are for dependencies used by the react-scripts package. Running the npm ls command will let you see if that is the case for an issue.

Here is the output of running npm ls for the "tar" dependency shown in the React vulnerability above.

###### Result of npm ls command 
![Result of npm ls command](https://user-images.githubusercontent.com/14915286/150437084-4791b6ef-9a11-4090-b3bc-f21e2e158457.png)

Note that react-scripts is a just under widow in the dependency tree. This tree shows that ultimately we’d have to update react-scripts to have a chance to remove this issue. Unfortunately, react-scripts latest version as of summer 2021 is 4.0.3 so that is not an option.

Fortunately, issues related to react-scripts can be easily resolved by submitting a whitelist ticket as demonstrated above. In this case, the comment should include text similar to what is shown in the following image:

![image](https://user-images.githubusercontent.com/14915286/150437201-edce2095-8fc1-45fa-aab6-a5b6bc0ae60f.png)

This ticket should include a screenshot of the confirmed and commented issue from the SQ Dashboard of the dependency tree produced by `npm ls`. Additionally, it can include a link to this article detailing the problem with npm audits products like SQ and react-scripts <https://overreacted.io/npm-audit-broken-by-design/>

Similarly, issues with other build tools that are non-user facing such as Enzyme, React Testing Library, and their dependencies can be resolved in the same way.

**Other Issues & Techniques**

- Research the vulnerability by Googling the CVE number. This may result in finding justification on why the issue is not relevant, a conversation pointing out an updated version resolving the problem, a statement on why the package maintainer won’t fix the issue, etc.
- Determine if the vulnerability is user-facing. Issues with packages that are used only during the build step can be whitelisted for the same reasons as issues with react-scripts
- If possible, update the dependency. This is most safe to do with a patch or minor version changes for packages that follow [semantic versioning](https://docs.npmjs.com/about-semantic-versioning). Don’t forget to check the code for the updated package to see what was changed to determine its effects on the app.
- If none of that works, submit a whitelist request pointing out that the latest version of the library is being used, and that the issue will be revisited when an updated version of the package is available. CTF pro-tip: revisit these issues to confirm the reason for the white-list request is still applicable.
