# How to resolve Fortify issues in the pipeline

Fortify is a plugin from Jenkins that essentially classifies the code quality issues in terms of its security impact on the solution
The purpose of this doc is to guide a fellow 'Gu-vian on how to resolve a Fortify issue that is blocking the pipelines

1. Go to https://fortify.il2.dso.mil/
 - If you don't have access, you will have to ask for access into the Fortify dashboard with a P1 Mission Application access request: https://jira.il2.dso.mil/servicedesk/customer/portal/73
 - Type which application you need access to and paste this url (https://fortify.il2.dso.mil/) as the application URL. Write a short message describing why you need access -- being nice can go a long way!
2. You should be met waith a dashboard that looks like this:
![image](https://user-images.githubusercontent.com/14915286/150607916-63ac77b2-2ca3-4ff3-a6ad-34410be750a0.png)
3. Click on the application version you're interested in

![Screen Shot 2022-01-21 at 5 28 47 PM](https://user-images.githubusercontent.com/14915286/150608562-563dba7b-b0b6-49cf-bdaf-ba01b4f56412.png)

4. Look for the items in the list that have a Criticality of "Critical". Ideally we would want to resolve all security vulnerabilities, but these critical ones are the issues that are blocking your pipeline
![Screen Shot 2022-01-21 at 5 29 29 PM](https://user-images.githubusercontent.com/14915286/150608622-1ce76f35-60da-48f8-a844-314d4c3f3c1d.png)
5. Go into each critical issue. Identify if it is indeed a security vulnerability or a false flag
- If it is indeed a security vulnerability, go into your codebase to fix this. Once fixed, the next time you run the pipeline, fortify should automatically update and the issue should be gone
- If not, go into the issue on Fortify to explain to the best of your ability why this isn't a security vulnerability
![Screen Shot 2022-01-21 at 5 47 49 PM](https://user-images.githubusercontent.com/14915286/150610186-78f99890-ca87-4827-95fb-fa5d23a66923.png)

 a. Assign an analysis from the dropdown and leave a comment why.
 
 b. Leave a comment why this isn't a security vulneability
 
 c. Go to P1 help desk to submit a pipeline exception request: https://jira.il2.dso.mil/servicedesk/customer/portal/73
 
 d. This doc has information on how to submit a pipeline exception request: https://github.com/braingu/doc-tadpole/blob/master/squads/Galactic/Pleiades/Development_Process/ResolvingSQIssues.md
 
Just be sure to add a link to to your specific fortify issue and remember to ask nicely
 
 
 
# Known Fortify false-positives
 
1. "Key Management: Hardcoded Encryption Key" in a react app

Sometimes Fortify will flag the "key" react HTML attribute as a vulnerability. I was able to resolve this on January, 2022, by explaining that "key" is not a security-related field, but rather a prop from React that ID's an HTML element

![Screen Shot 2022-01-21 at 5 32 17 PM](https://user-images.githubusercontent.com/14915286/150608840-5c3a5454-a044-405f-a730-dcc9b73a96a1.png)



