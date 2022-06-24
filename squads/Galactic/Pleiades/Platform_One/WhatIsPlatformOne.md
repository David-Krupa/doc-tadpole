# What is Platform One?

The content below is from [Christopher Walz](https://braingu.atlassian.net/wiki/people/602d194f1bf1ce006bb2a680?ref=confluence)'s notes from a Platform One Immersion Day. This can serve as a scaffolding for us to improve & add information as we go along.

## Briefing

### Why are we doing this?

- Status quo for DoD software sucks. The barrier to entry is high
- Open source is good
- Airmen/Guardians need good software
- 94% of projects either completely fail or are over budget or behind schedule

### Solution

- DevSecOps (Platform One)

### P1 Products

- CNAP: "front door of P1"
- Iron Bank: container level security. 600 containers available (amazon, elastic, grafana etc.) <https://ironbank.dso.mil/repomap/products>
- Big Bang: Has deployment packages.. \[missing some notes here\]
- Party Bus: Hooks up to gitlab or GitHub. Multi-tenant DevSecOps. Most popular. Provides: **Continuous ATO** (cATO) instead of Authority to Operate (**ATO**) . This is what makes Platform One awesome. cATO Authorizes the platform, process, and the team that produces the product under a continuous monitoring process that maintains the residual risk within the risk tolerance of the Authorizing Official (AO). \[Removes the need to constantly require re-approval of ATO. In relation to this is CtF which means an application is certified for deployment.

Widow got a shoutout for it's speed of deployment

- 4 weeks to MVP
- 148 improvements from user feedback
- 71 critical bug fixes
- \~4000 commits
- Over 75 missions planned
- Platform One runs on Cloud One (AWS)

### **Innovation for Small Businesses for Air Force**

<https://www.afwerx.af.mil/>

According to their Acquisitions team, it sounds as if they want a diverse set of vendors/contractors

### **P1 Crada**

<https://tier7.us/what-is-crada/>

### **P1 Customer Success Form**

<https://jira.il2.dsop.io/servicedesk/customer/portal/36/create/202>

### **Cybersecurity of Platform One**

<https://confluence.il2.dso.mil/spaces/viewspace.action?key=P1CYBER>

### **CNAP**

- Single point of ingress/egress
- VPN
- Zero-trust
- Firewall
- Logs / auditing
