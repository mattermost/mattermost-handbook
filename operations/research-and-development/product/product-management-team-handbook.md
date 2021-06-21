---
description: 1% DRAFT
---

# Product Management Team Handbook

## Overview

The purpose of this handbook is to provide more details on the Product Manager role, processes, and relations to other functions within the organization to foster success for employees in this role. This handbook may be shared with other functional areas so they may gain a better understanding of the Product Manager role, and develop a greater understanding for responsibilities and interaction areas.

[Product Management Areas of Ownership](operations/research-and-development/product/product-ownership-areas.md) 
[Product Manager Onboarding](operations/research-and-development/product/pm-onboarding.md)


## The Product Manager Role

Product Managers are organized within the R&D area of Mattermost; however, they have interactions with all departments and areas to ensure success of the product.

### Strategic priorities

Product Managers are responsible for carrying out the strategic priorities of the product. They are tasked with ensuring the product is profitable by meeting customers and users existing and future needs. Understanding that each client and user have their own set of specific requirements, use cases, and preferences; a Product Manager must understand the patterns across a broad range of input and focus on exploiting value in the areas that will provide the greatest return for the largest audience.

### Core Areas of Responsibility

| Responsibility | What does this mean?| Actions taken for this responsibility|
| :--- | :--- | :--- |
| **Problem Definition** | Listen to current, prospective, and target customers and users to understand their problems and other solutions available to address their problems. Have a deep understanding of what the problem is, their use case, what's a “must have” to resolve the problem and what's a “nice to have”. Understand where the problem is with the deep context of a user/customer experience. | <ul><li>Document problem statements and use cases from interviews and feedback channels.</li> <li>Conduct competitive analysis and market research.</li> <li>Determine demand for a solution by validating propensity of problem or use case within our broader customer/user bases and market.</li> <li>Document what is required by users or customers to solve the problem.</li><li> Draft 1-pagers and PRFAQs.</li> </ul> |
| **Strategy Alignment** | Determine how problem statements align with direction and mission of your area of ownership and strategy of Mattermost. Determine priority of solving the problem and the scope at which it needs to be solved. Drive alignment and agreement on importance of priority. Say "no" when something does not align. | <ul><li>Score and prioritize features by impact, gain alignment from MLT, teammates, and GTM on the priority and scope of the required solution.</li> <li>Document and share decisions and alignment discussions.</li> </ul> |
| **Solution Definition & Validation** | Work with design and engineering to find solutions. Represent the voice of the user/customer to ensure must-have requirements are addressed. Coordinate external functions that need to be consulted in definition of solutions. | <ul><li>Write spec documents and produce low fidelity wireframes and user flows.</li> <li> Determine packaging based on how the solution fits the needs of ICs, Managers, or Executives. </li> <li> Validate solutions with users and customers to ensure they meet their use cases and requirements.</li> </ul> |
| **Solution Scheduling & Development** | Work with developers, designers, and QA team to negotiate scope of functionality, resolve challenges, and ensure features meet quality standards. Represent resources and be the coordinator of collaboration across all functions and Eng teams. | <ul><li>Expose and resolve challenges between functions.</li> <li>Test features to ensure key use cases are solved. Update stakeholders with expected timelines and changes to solution scope.</li> </ul> |
| **Solution Release** | Work with Release Manager and Marketing to prepare customer and internal enablement and announcement materials. Ensure go-to-market and operations are prepared to accommodate adoption of new functionality. | <ul><li>Prepare release announcement from finalized 1-pagers/PRFAQs, record a demo of the feature, update public facing roadmaps and forums with release updates. </li> <li> Complete product documentation and changelog information with assistance from Tech Writers.</li> <li> Ready operational and customer-facing teams with training and enablement materials.</li> </ul> |
| **Solution Adoption** | Advocate for adoption of the new value added to the product. Monitor feedback and iterate on improvements to improve experience.  | <ul><li>Track feature usage and feedback through qualitative and quantitative data gathering.</li> <li> Demo and share features with existing customers and users.</li> <li> Iterate on feature with additional feedback from customers/users. </li> </ul>|

### Guiding principles for the PM role \(WIP\)

* [Company Values](https://handbook.mattermost.com/company/about-mattermost)
* [Mindsets](https://handbook.mattermost.com/company/about-mattermost/mindsets)
* Recommended Reading
* * What fundamental philosophies are predominant?
  * Pragmatic Marketing: “Your opinion, although interesting, is irrelevant.”
    * It’s all about the customer/user/buyer’s opinion/want/need
* [FAQ](https://handbook.mattermost.com/operations/research-and-development/product/product-management-team-handbook#frequently-asked-questions-faq)
  * How do we make packaging decisions?
  * Prioritization framework
  * Tips on working with customers
  * Tips on working with the contributor community
  * Experimental, Beta, and General Availability of Features



## Product Manager Duties

### Product planning

#### Customer and feature research

* Interview and ask questions to clients and prospects
* Document findings and requirements
* Share findings with designers and developers
* Coordinate kick-off for planning activities of new features

#### Product vision and roadmap

* Roadmap creation - what to add to roadmap and why
* Socialize vision and roadmap internally and externally
  * Participate in Roadmap meetings

#### Prioritization and release planning

* Capture SWAG estimates from design and developers to determine length project
* Facilitate prioritization decisions in sprint and release planning meetings
* Keep [Release Plan](https://mattermost.productboard.com/feature-board/1097526-release-tracking-internal) up to date with features queued for the release

#### Feature design

* Define requirements and coordinate design resources for features
* Prepare and manage spec documents to organize planning, design, and stakeholder input of features
* Ensure cross-collaboration between designers, developers, and QA
* Create Jira tickets for features and bugs
* More complete information on the Design process can be found [here](https://docs.google.com/document/d/1PMGeoh95CyLZ2lfAjOh6p2HuFrysx5HXit8XoOrm8Pg/edit)
* Ensure designs follow our [UX guidelines](https://docs.mattermost.com/developer/fx-guidelines.html#fast-obvious-forgiving)
  * Fast, Obvious, Forgiving
* Determine feature availability: Team Edition or Enterprise Edition
  * [Stewardship principles](https://docs.mattermost.com/developer/manifesto.html#stewardship-principles-for-the-mattermost-open-source-project) that we use to guide whether a feature belongs in TE
  * [TE vs EE from Ian](https://community-release.mattermost.com/private-core/pl/m1o63kk3h7numxw3z116ft4ffw)
* Determine Packaging/SKU \(E10 & E20\)
  * TE OR EE
    * [https://docs.mattermost.com/overview/product.html\#mattermost-editions](https://docs.mattermost.com/overview/product.html#mattermost-editions) 
  * In-Code: if \(this.props.buildEnterpriseReady && this.props.isLicensed\)
  * Review with PM team and get approval from other leads as required

### Feature development and the release process

#### Triage

* Validate “Won’t fix”, “Won’t do” tickets. Provide a final comment of approval so ticket can be closed by QA
* Assist in identifying [Help Wanted tickets](https://handbook.mattermost.com/contributors/contributors/help-wanted)
* Update Fix Version to “help-wanted”, which will run an automation that will automatically create a corresponding issue in GitHub

#### Release feature roadmap

* Provide updates to current release roadmap in PM meetings
* Review and provide input on release announcements
* Provide updates to Release manager on deprecated features, features being promoted from experimental or beta, and any breaking changes within a release

#### Pull Requests in GitHub

Review Release PRs and Community PRs to ensure the feature meets requirements for design and functionality. Approve PRs once feedback \(if any\) is addressed by developers.

* Label = PM Review
* Test for user experience, use case, design, corner cases, and bugs
  * May need to create Spinwick server by adding label = “Set up cloud test server”. The server is created in a few minutes
  * Add QA and UX resources as required
  * If there are config setting changes you will need to ask Development to change the setting for you
  * If you need to test email notifications, you can set the email configuration based on on settings contained on [GitHub Internal Information Repository Platform-Private](https://github.com/lindalumitchell/platform-private/blob/af19e46ab3f6561e36a2b01b44edc6a0232d4755/config/spinmint-email.txt)

#### Sprints \(Sprint Planning/Retros\)

* Work with developers to ensure the sprint work accomplishes highest priority bugs and projects on release plan/roadmap
* Jira is the system used to manage work items to be completed by the development and QA team
  * More information on how Jira is used can be found [here](https://docs.google.com/document/d/1PMGeoh95CyLZ2lfAjOh6p2HuFrysx5HXit8XoOrm8Pg/edit)
* Ensure tickets are available for features
* Prioritize bugs
* Answer questions posted by team members in planning or on tickets

#### Testing

* Test features and provide input on PRs from Developers and Community members

#### Security and dot releases

* Inform Release Manager and QA team of any changes that need to be released as a dot release \(security or critical bug fixes\)
* Participate in any testing or validation required to verify fixes
* Ensure fixes are moving through development and review processes efficiently
* Provide Release Manager with information for changelogs and release announcements

#### Release Retrospectives

* Participate in Release Retrospectives \(see example [Release Retrospective Doc\)](https://docs.google.com/document/d/1TFSj6jOZ96nJXgS83DL0-3bFurcXuOyeUm7cP6TWfsY/edit)
  * Provide feedback from PM perspective and offer ideas for improving the release process

#### Product evangelism

* Provide feature demos on customer calls, for customer training initiatives and for Mattermost Academy
* Participate in events and conferences

#### Documentation

* Update/create documentation for features/PRs
  * Maintain documentation on feature proposals \(reference all design and development documentation\)
  * Release notes should be written targeting an international IT Admin
  * Guidelines for [documentation](https://handbook.mattermost.com/operations/research-and-development/product/product-technical-writing-team-handbook#submitting-feature-documentation-pms)
    * Any in product instructions or documentation should never contain hard-coded links
    * A redirect page from about.mattermost.com should be used in product instructions. \(See instructions [here](https://handbook.mattermost.com/operations/research-and-development/product/product-management-team-handbook#how-do-i-create-redirects-for-in-product-documentation)\)
* Maintain product accuracy on mattermost.com/product and roadmap
* Author [Forum](https://forum.mattermost.org/t/community-design-meeting-folded-reply-threads/6729/10), [blog](https://mattermost.com/blog/mattermost-launches-mattermost-superstars-program-for-contributors/) and [release announcement](https://mattermost.com/blog/mattermost-release-v5-25/) posts
  * Example \(link to Eric’s permissions post\)
* Other Marketing \(e.g. future webinars, event participation, etc\)

### Customer and Community Success

#### Customer Success

* Provide Roadmap status updates for Enterprise clients
* Assist with Customer Support
* PMs should be on sales/customer calls often; if not on at least a couple per week then request to be added in the CSM:PM channel and Pre-sales channel
  * Document and post feedback in [Salesforce](https://handbook.mattermost.com/operations/customer-success#logging-a-customer-feedback-in-salesforce)
  * Add/update Jira tickets to capture feature requests
* Participate in and contribute updates via the Customer Request Triage meeting
* Verify bugs reported by customers
* Answer customer questions in Premier Support \(PS: Customer name\) Channels and in internal channels by CSM and Sales

#### Customer requests

Feature and improvement requests from our Enterprise customers are logged by Customer Engineers, Customer Success, and Support in [productboard](https://mattermost.productboard.com/feature-board/1097524-master-feature-list).

Please encourage colleagues to file feedback in productboard when they are discussing requests in Mattermost channels, so that we have single source with all requests. PMs are responsible for reviewing the productboard feedback, and assigning it to relevant feature ideas. As they are reviewing the requests, PMs may also:

* Work with Customer Success and Sales to clarify use cases, root issues, and pain points as well as the priority of the request to the customer
* Propose alternate solutions and workarounds when they are available
* Provide feedback on whether it's a "Won't Do" feature that we are unlikely to add to the product
* Update the feature idea to link any implementation or design tickets
* Update the **Effort** for the feature with a SWAG from the Engineering team
* Update the feature idea to have a release timeframe (3 months, 6 months, future) or release version if the feature is planned

After adding the feedback to the relevant idea in productboard, the PM comments and mentions the reporter so they are aware the feedback has been processed, and then marks the item as **Processed**.

#### Community Success

* Ensure devs are aware and included on community contribution projects
* Prep Help Wanted tickets with specifications on feature and designs as needed
* Help teams come up with and prepare community contribution campaigns
* Answer questions and coordinate resources to community contributors
* Review community contributed PRs

#### Mattermost Forum

#### Twitter rotation

Product Managers are mentioned to assist in answering product question escalations on Twitter. Twitter is monitored by the marketing team, and they will @mention the PM team in the Twitter channel when they need to escalate a question. PMs should respond to questions in their area of ownership. 

### Organizational improvements

* Increase productivity of department
  * Make progress on quarterly goals and OKRs for department
* Enable other departments
  * Training
  * Develop features for internal systems
* Increase community awareness
  * Research and propose additional ways to engage with existing community and identify new opportunities for community engagement

## Meetings - WIP

### PM Weekly Sync 

| Attendees | Objectives | Time | Meeting Prep | During Meeting | Post Meeting |
|:-----|:------|:----|:------|:-------|:-------|
| <li> Senior PM Managers</li> <li>All PMs</li> <li>Release Manager</li> | <li>Update progress on features for current release</li> <li>Triage unassigned Customer Requests</li> <li>Share team updates and best practices</li> <li>Gather input from PM colleagues on proposals to uncover blindspots</li> | Wednesdays from 9:00am to 9:30am Palo Alto time. | <li>Post agenda items directly in the meeting agenda (linked in the meeting invite).</li> <li>Provide supporting documentation for advanced review. Confidential information should be posted in the PM:Private Channel.</li> <li>PM on the Customer Request Rotation should have assigned all obvious unassigned requests prior the meeting.</li>| <li>Release Manager: Get updates from PMs on items scheduled in the Release Plan.</li> <li>Queued agenda items. Some agenda items that take a large amount of time may be time-copped based on other agenda items queued.</li> <li>Note action steps for agenda items, especially when there is follow up required for PM who did not queue the item.</li>| <li>Provide updates on action steps posted against previous agenda items.</li> <li>This may include providing a follow up agenda item for a future meeting.</li> |

### Monthly Product:Sales call

| Attendees | Format | Time | Meeting Prep | During Meeting | Post Meeting |
|:-----|:------|:----|:------|:-------|:-------|
| <li> All PMs</li> <li>Optional: Sales, BizOps, Marketing departments</li> | <li>PMs share roadmap highlights: Focus is on features with clear release timelines, and a clear benefit to customers, so Sales knows what is coming up soon they can talk to customers about.</li> <li>Demos, PRFAQs, and designs are shared as needed to illustrate the benefits</li> <li>Open Q&A</li> | Monthly meeting on 1st Monday of the month from 9:00am - 10:00am Palo Alto time. | <li>Prepare a list of features you'd like to showcase during the meeting. The agenda of features PMs are presented are typically coordinated a few days in advance.</li> <li>Prepare a short demo of the features. Show prototypes or designs if a demo environment is not available.</li> <li>Prepare information that the team may need to be aware of regarding feature, and be prepared to answer questions about the feature.</li>| <li>Present your demos and share any other important information regarding features or upcoming product changes.</li> <li>Answer questions from the team. It may be necessary to time-cop a particular topic to ensure we can share all the demos on the agenda.</li>| <li>Share recoring post meeting.</li> <li>Share feedback survey post meeting.</li>|


## Frequently Asked Questions (FAQ)

### How do I create redirects for in-product documentation?

Documentation that is linked in-product should always use a redirect from www.mattermost.com instead of the docs.mattermost.com site, to ensure links are not broken in the event that they are moved on the docs site.

To set up a redirect, you must have admin access to www.mattermost.com. Marketing can assist with this access or @jason.blais or @katie.wiersgalla can add a redirect for you.

If you have access, follow these steps:

1. Log in to the administration panel for www.mattermost.com
2. From the left-hand sidebar, go to **SEO > Redirects**
3. On the top of the screen, ensure you are on the **Redirects - Yoast SEO** page header on the **Redirects** tab
4. Under **Type**, choose `301 Moved Permanently` option (this is the default option)
5. In the **Old url** field, enter in the new direct you want to use in-product in the format of `/pl/default-page-description`. Update the page description with your page information
6. In the **Url** field, enter in the full URL to the page on docs.mattermost.com
7. Click the **Add Redirect** botton and verify your entry is added to the list. You may need to page through to find your entry
8. Test your redirect URL. This will be the URL in the format of `https://www.mattermost.com/pl/default-page-description`
