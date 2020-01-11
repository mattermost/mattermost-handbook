---
description: 1% Draft
---

# Technical Writing Team Handbook

The Technical  Writing team focuses primarily on the User Guide, Admin Guide, and Developer documentation.

## Areas of Responsibility

### @justine.geffen:

* [Administrator's Guide](https://docs.mattermost.com/guides/administrator.html)
* Admin-facing UI Content, such as the System Console
* Feature documentation for:
  * Cloud team \(Mattermost Cloud, Kubernetes, operator, helm, ..\)
  * Enterprise team \(SAML, compliance, permissions, ..\)
  * Platform team \(CLI, config settings, ..\)
* GitLab
  * [GitLab Mattermost docs](https://docs.gitlab.com/omnibus/gitlab-mattermost/%20)
  * GitLab helm chart docs
* Google Analytics/Documentation metrics
* Community and doc review process
  * Process for Doc Up plugin
  * Docs review and coordination with @amy.blais
  * Community Help Wanted doc issues
  * Documentation Handbook and Style Guide maintenance

### @\[To Be Hired\]:

* [Integration's Guide](https://docs.mattermost.com/guides/integration.html)
* Feature documentation for:
  * Integrations team \(Jira, GitLab, Jenkins, ..\). This may involve some light admin docs to configure integrations/plugins.
  * Toolkit team \(Plugin framework, developer toolkit, …\)
* Developer documentation for:
  * [developers.mattermost.com](https://developers.mattermost.com), including Contribute, Integrate and Extend sections
  * [api.mattermost.com](https://api.mattermost.com)
  * general developer experience docs, e.g. code samples. Exact details TBD
* Developer-facing UI Content, such as the Integrations backstage
* Community and doc review process
  * Exact split with Justine to be determined

Note: Few areas not listed above, such as the [User's Guide](https://docs.mattermost.com/guides/user.html), will remain a collaborative effort between Product Managers and Technical Writers. Please assume @jason.blais as the directly responsible individual.

## Processes

The processes around documentation, such as SLAs for issues and requesting documentation assistance are detailed below.

### **Contributing to Documentation**

The basic outline for getting started with contributions is provided in the [README](https://github.com/mattermost/docs/blob/master/README.md) of the docs repo. If you have write access to the repo, you can create a branch off master and work on that. 

Once complete, submit your Pull Request \(PR\). Ensure that you assign appropriate approvers and labels. You can read more about the review process [here](https://developers.mattermost.com/contribute/getting-started/code-review/) - it applies to various types of contributions including documentation.

### DocUp/Documentation Issue Process

Requests for documentation can be made within [community.mattermost.com](https://community.mattermost.com), using the DocUp plugin embedded in the post menu.

![Access the Doc Up plugin by hovering over a message and clicking the &quot;...&quot; menu.](../../../.gitbook/assets/image%20%2810%29.png)

When you select DocUp, an issue is generated in the GitHub docs repo, and added to the issues list. 

#### Turnaround Time

When the issue has been created, please follow these guidelines to assign appropriate labels: [https://developers.mattermost.com/contribute/getting-started/labels/](https://developers.mattermost.com/contribute/getting-started/labels/). This ensures that the issues are prioritized appropriately. 

You can expect the following approximate turnaround times:

* Urgent issues \(bug, customer request/dealbreaker\): Acknowledged within 24 hours.
* General issues: Acknowledged within 48 hours.

There are a number of variables at play and providing a hard and fast time-frame for completion. A rough guideline is between 3 and 5 days for most work and 2 - 3 weeks for larger projects. Larger projects might be moved to Jira if appropriate. 

_\(To do: Add more labels to doc repo around priority/urgency? Add labels for different areas and add labels for things like “customer request” “release related” “bug” etc?\)_

_Suggestions:_

* _In progress/Taken_
* _Priority: Urgent_
* _Priority: Next release_
* _Priority: Customer issue_
* _Bug_
* _Editing/Review_
* _Content Request/New Content_
* _Area: Feature Documentation_
* _Area: Customer Education_
* _Area: API_
* _Area: Mobile_

_Labels used in other doc-related repos that may be helpful if applied across repos:_

* _Content_
* _Needs Documentation_
* _Up for Grabs_
* _Docs/Needed_

#### Assignees

Documentation does not have to be written by the Technical Product Writer/s. You can raise an issue, complete the requirement, and submit a Pull Request.

For less urgent work, if no reply has been received within 48 hours, please ping @justinegeffen in GitHub. 

#### Community Involvement

We really want the community to own the docs as much as possible. In light of this, please mark your issue as “Help Wanted” so that community members are able to identify work that they’re able to assist with. 

If your documentation request/issue applies to a repository other than mattermost/docs, you can use the Editor Review label and/or ping @justinegeffen.

## General Contribution Workflow

### Jira Tickets

The Technical Writing Jira board is located here: [https://mattermost.atlassian.net/secure/RapidBoard.jspa?rapidView=51](https://mattermost.atlassian.net/secure/RapidBoard.jspa?rapidView=51). Feature and release writing is planned three sprints in advance. This ensures that ad-hoc work can be taken on. 

If you have a documentation requirement, please create a ticket and include the following fields:

* Label: Documentation
* Team: Documentation 
* Assignee: Justine Geffen

Depending on what is required, please also include a sprint as well as a fix version.

#### Jira Turnaround Time

If the Jira ticket is for documentation related to a release, the documentation needs to be complete at least 10 days prior to release. Please ensure you allow sufficient time for your request to be completed or it will be moved to the next available slot. 

If the Jira ticket is for general documentation, depending on the current workload, you can generally expect it to be completed within five business days. 

### Editing Requests

The Technical Product Writer/s form part of the PR review/approval process. When submitting a PR for documentation, please add the “Editor Review” label. Once the editor has signed off on the PR they will remove the label. 

### Formatting and Style Guide

The [Documentation Style guide](https://docs.mattermost.com/guides/core.html#documentation-style-guide) and [UI text guidelines](https://docs.mattermost.com/process/documentation-UItext-guidelines.html).

### Community Documentation Involvement

Every month, the Mattermost community plans, builds, tests, documents, releases and supports new product improvements for Team Edition to benefit the user community, and the Mattermost Enterprise Team does the same for Enterprise Edition to benefit the subscriber community.

A critical part of this development is documentation, and this documentation ranges from feature documentation to FAQs, guides, and tutorials. 

#### Feature Documentation

Feature documentation is generally written by the technical product writers, within a specific time-frame aligned with releases. Community members are welcome to assist, if the time expectations are manageable. 

Feature request documentation is usually located here: and here: and labelled as “Docs Needed”. As these are tied to a release \(and a deadline\) it’s best to only take on the work if you’re sure you can complete it on time. It’s expected that community members contribute in their available time, which is why this type of documentation isn’t usually the best option to take on. 

#### Help Wanted Tickets/Doc Issues

Help Wanted tickets are generally not linked to a release and are more flexible in terms of timeline and delivery date. You can find the documentation Help Wanted tickets [here](https://github.com/mattermost/docs/labels/Help%20Wanted). To start working on one, you can assign it to yourself, comment add a comment indicating you’ll be working on it, and get started. 

#### Engineering/Developer Documentation

Most, if not all, contributions have a documentation impact. As part of the development and submission process, it’s recommended that the relevant documentation be updated and included in the PR. This provides consistency and accuracy in communicating the changes/new feature and cuts down on having multiple issues and PRs for related documentation.

However, the documentation can be as detailed or concise as deemed necessary - consider it an MVP which can be refined at a later stage. 

When submitting your PR, please include the \*\*Editor Review\*\* label and add @amyblais or @justinegeffen in GitHub as an approver.

