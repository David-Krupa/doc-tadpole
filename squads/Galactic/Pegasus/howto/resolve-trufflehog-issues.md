# How to resolve Trufflehog issues in the pipeline

TruffleHog runs behind the scenes to scan your environment for secrets like private keys and credentials, so you can protect your data before a breach occurs.
Uniquely, Trufflehog is the only step of our pipeline process (as of Jan, 2022) that doesn't have a designated dashboard such as Sonarqube and Fortify. Thus we are forced to work closely with the pipeline job report through gitlab in order to resolve its issues.

First let's go to the last pipeline run where trufflehog fails

1. Go to your gitlab repository
2. CI/CD (on left menu bar) 
3. Click on "Pipelines"

![Screen Shot 2022-01-21 at 6 06 08 PM](https://user-images.githubusercontent.com/14915286/150611378-525f1d83-d6ac-4e44-a195-0e7d57e5f971.png)

4. Identify the desired pipeline run and click on the "Trufflehog" step to view the scan report
5. Read through the report to find "Trufflehog gate check findings" - my report looks something like this:
```
Trufflehog gate check findings - 
    "path": "public/assets/F-16C.gltf",
    "line": "241",
    "path": "public/assets/F-16C.gltf",
    "line": "249",
    "path": "public/assets/F-35.gltf",
    "line": "415",
    "path": "public/assets/F-35.gltf",
    "line": "407",
    "path": "public/assets/F-35.gltf",
    "line": "403",
    "path": "public/assets/F-35.gltf",
    "line": "419",
    "path": "public/assets/F-16C.gltf",
    "line": "245",
    "path": "public/assets/F-35.gltf",
    "line": "411",
Trufflehog gate check Failed with finding count -  8
Uploading artifacts for failed job
00:01
Uploading artifacts...
.ci_artifacts/trufflehog/: found 2 matching files and directories 
Uploading artifacts as "archive" to coordinator... ok  id=3411905 responseStatus=201 Created token=hPsSrPQ2
ERROR: Job failed: command terminated with exit code 1
```
6. Each "path" and "line" combination will denote where the flags were raised in your application. Navigate to these flags to identify why Trufflehog thought we were potentially revealing secret keys
7. Once you have identified each flags... if secret keys are indeed being exposed, put them elsewhere more secure so that our secrets aren't exposed to the rest of the world
8. However, if this is a false-positive on Trufflehog, we have to submit a pipeline exception request. Go to P1 help desk to submit a pipeline exception request: https://jira.il2.dso.mil/servicedesk/customer/portal/73
9. This doc has information on how to submit a pipeline exception request: https://github.com/braingu/doc-tadpole/blob/master/squads/Galactic/Pleiades/Development_Process/ResolvingSQIssues.md
10. In the request, you can say: "Please exclude {{list_of_project_files}} from trufflehog scans as they are not exposing any secrets"
11. You will also need to verify that each of the called out lines are actually not exposing any secrets in code.
12. Once the ticket has been submitted and a P1 member replies, you will have to add him/her to as a member of your repository for them to resolve your request



