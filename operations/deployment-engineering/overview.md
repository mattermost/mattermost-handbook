# Deployment Engineering: Overview

Deployment Engineering provides expertise on how to run and deploy Mattermost and the platform as a whole, and act as extensions of R&D supporting customers in partnership with post-sales and revenue retention teams.

## Team mandate

The team's primary mandate is to increase customer seats deployed.

We collect [seats deployed data](https://docs.google.com/spreadsheets/d/1ZnjJHWIsT9hIxotCYrSG66XIWsf_usf258Ll8HgVmzU/edit#gid=423031054) on a quarterly basis where available, and prioritize initiatives based on a) underdeployment with low customer adoption (e.g. 50% of users are active on a monthly basis), and b) customer ARR >$50,000.

## Q2 Priorities (May - July)

The Deployment Engineering team has three key priorities for this quarter:

1. Establish itself as a new team supporting post-sales & revenue retention, including AORs, processes & workflows.
2. Completing the deployment of the Mattermost solution for Microsoft Teams in a customer environment.
3. Completing a loadtest scenario of a Sev0 outage scenario in a customer environment, where up to 15,000 users logs in to the system within 15 minutes.

## Areas of Responsibility (AORs)

The team's primary mandate is to increase customer seats deployed, deeply understanding technical/engineering bottlenecks, and solving for them. Moreover, we are responsible for creating reference architectures, supporting non-standard deployments with complex technical problems, and providing engineering support to post-sales teams with >$50K customers on critical escalations, one-off custom solutions & integrations based on requirements defined by the CSMs/TAMs.

A complete list of AORs is included below:

1. **Customer Seats Deployed**: Seats deployed data for our customer base is [tracked in this spreadsheet](https://docs.google.com/spreadsheets/d/1ZnjJHWIsT9hIxotCYrSG66XIWsf_usf258Ll8HgVmzU/edit#gid=423031054)

  - **Technical onboarding**: Help customers deploy in non-standard environments, such as configuring and running loadtests, writing documentation for gold standard deployments, complex data migrations, integration configuration and setup, and guiding customers with deployment KPIs to measure long-term ROI.
  - **Server upgrades**: Support customers with non-standard server upgrades, run system integrity diagnostics before/after upgrade to detect anomalies, create database migration scripts in preparation for upgrades
  - **High scale documentation**: Enable successful customer deployments at scale, including amendments to deployment documentation, troubleshooting guides, how-to guides & videos, answers to general technical questions on the platform, Mattermost architecture diagrams, and documented deployment KPIs to measure long-term ROI.
  - **Customer health checks**: Ensure deployments meet recommendations, review performance metrics and share back with R&D to help improve loadtests

2. **Reference Architectures**: In partnership with core platform team, with a [complete plan in this document](https://docs.google.com/document/d/1kAxel327wsJwg35Y7EYNzHlbEnRN2Brn3Im9M4Rf82Q/edit#)

  - **Loadtest Deployment Tooling**: Create a script/guide (e.g. Terraform, Ansible, whitepaper) to automate the use of the loadtest framework, which includes AWS set up, keys, auth, and more. TAM team acts as the first customer, with the plan to support this script in other customer environments.
  - **ESR usage & ceiling tests**: Run usage & ceiling tests against ESRs (twice a year). Share observations to Server Platform teams and recommend architectural/docs changes, if any.
  - **Expand reference architectures**: Continue to expand on available reference architectures, with [GitLab’s documentation](https://docs.gitlab.com/ee/administration/reference_architectures/) as a north star

3. **Custom Solutions**: _<Repository or page of custom solutions built for customers to be added>_

  - **Custom solutions**: Workarounds for unique requirements, one-off integrations (e.g. MS Teams integration), one-off solutions (e.g. legal hold). 

4. **Customer Escalations**:

  - **Technical line of defense for deployment escalations**: Ensure customer environments have what we need to help (e.g. system diagnostics, performance monitoring), perform deep troubleshooting and data collection, end-to-end handling of some incidents, escalate and partner with R&D for incidents that require more support.

For other references, see [this document for customer reliability engineering](https://docs.google.com/document/d/1KS2Kt_gujCynK-Rl9vHN7zb6UfPe5kNeaUOYpQHMOcs/edit#), and [these slides for post-sales & revenue retention AORs](https://docs.google.com/presentation/d/1d00K-er3B15UFW9OkZrC0Y03htolYn6K874ZBucCAJo).

## Links to Key Documents

- Jira board: https://mattermost.atlassian.net/jira/software/c/projects/MM/boards/127
- Confluence page of deployment engineering solutions https://mattermost.atlassian.net/wiki/spaces/~557058c88c3d11b60143deaba6d3d018132127/pages/2461925377/Deployment+Engineering+Solutions
- Deployed seats data: https://docs.google.com/spreadsheets/d/1ZnjJHWIsT9hIxotCYrSG66XIWsf_usf258Ll8HgVmzU/edit#gid=423031054
- Services request template https://docs.google.com/document/d/1EbP4Ab7N2hEAv--DRCcZHk0XtlG1MFP8F8F0viaTM7I/edit
