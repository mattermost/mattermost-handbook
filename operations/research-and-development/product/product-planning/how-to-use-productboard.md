---
description: 'https://mattermost.productboard.com/'
---

# How to use productboard

Productboard is used by Product Managers and Customer/Sales Teams for:

* Feedback collection
* Feature validation
* Requirements gathering
* Feature prioritization/roadmap planning

When a feature moves to "planned" the Product team pushes it to Confluence and Jira (or wherever each team decides) to define the scope/spec and track work.

Specifically, productboard is used to decide what to build (and when), while other systems like Confluence or Jira are used to communicate and design on what exactly is being built at individual feature level.

**Roles**

**Makers:** Product Managers and Product Management leadership
**Contributors:** Customer Engineers/Customer Support/UX/Dev Leadership
**Viewers:** Everyone else with @mattermost.com email address

## 1 A day in the life of a Product Manager

### 1a Reviewing new feedback from users and customers

New feedback from users and customers is sent to the [Insights Board](https://mattermost.productboard.com/insights). Typically these are submitted by fellow Product Managers, Support, Customer Success Managers, or Sales through integrations with email, Zapier, Zendesk, or others.

When in the Insights Board, you can either go to your [Personal Inbox](https://mattermost.productboard.com/insights/my-inbox) or a [Shared Team Inbox](https://mattermost.productboard.com/insights/shared-inbox) to review feedback. When you find something relevant to your initiatives, highlight it in the notes and click the pencil icon to attach it to a feature.

![](../../../../.gitbook/assets/image%20%2857%29.png)

You can either link the feedback to an existing feature request, or create a new one.

Finally, you'll choose how important this request is for the user or customer. For feedback coming from customers, this is typically shared by the appropriate team member in the customer team who has first-hand knowledge of the criticality of the request.

![](../../../../.gitbook/assets/productboard-link-feedback.png)

Linking feedback directly to features lets you easily capture and organize ideas. It also attaches customer information and request details automatically from the call notes to the detailed product feedback \(dependent on available integrations, one for a two-way native Salesforce integration is coming soon\).

### 1b Prioritizing features in the Features board

Second critical element is prioritizing features in the Features board.

Usually you would start from the [feature organization view](https://mattermost.productboard.com/feature-board/1097524-feature-organization) which has all features broken in a [product hierarchy](https://www.productboard.com/blog/product-hierarchy-set-up/) by feature teams, components, and features.

* **Feature teams** is the top-level category and refers to the corresponding R&D team, such as Apps, Platform, and Integrations.
* **Components** are identified by a symbol with four square, are categories or high-level themes such as “Compliance” or “User Experience”.
* **Master features** (often become epics) are top level features with customer facing business value such as “Legal Hold & e-Discovery” or “Improve Reply Threading”.
* **Sub-features** (typically match up with user stories) contribute to the business value of the master feature and should positively impact the end-users, the System Admins, or other users/stakeholders. Examples: “Lock messages and files for legal hold” or “pop-out windows for reply threads”.

In this view, you can filter and sort by various fields, and create custom views that you can refer back to later. Available filters include:

* **User Impact Score**, calculated based on number of requests, weighted by how important it is to them. [Learn more how the score is calculated here](https://help.productboard.com/en/articles/882615-use-the-user-impact-score-to-surface-your-top-requested-feature-ideas).
* **Drivers and prioritization scores**, including market demand, product strategy and operations. [Learn more here](https://help.productboard.com/en/articles/1552014-use-drivers-and-prioritization-scores).
* **Segments**, including OSS community, banking and finance, and government.
* **Tasks**, such as the status of designs or development.
* **Releases**, which identifies an internal target for which release the feature is scheduled.

Two other commonly-used views include the [Top Requests View](https://mattermost.productboard.com/feature-board/1097530-top-requests) which automatically filters all feature requests to those with highest user impact scores, and a [Prioritization Matrix](https://mattermost.productboard.com/feature-board/1097533-prioritization-matrix), which provides a 2x2 visualization of the value a set of features gives to an objective against the level of effort.

![](../../../../.gitbook/assets/image%20%2834%29.png)

With these views, including custom ones you can create, you can prioritize features and surface priority requests in the Features board. Based on the prioritization, you can change the feature status to a Candidate for roadmap or Planned for roadmap.

![](../../../../.gitbook/assets/productboard-feature-status.png)

Once the feature is in progress or released, you can update its status in productboard accordingly.

Note that each time you update the status of a feature or add a comment, anyone who is a watcher will receive an email notification. In the initial roll-out, watchers are limited to Mattermost team members only.

### 1c Organizing features in the Master Feature list

1. Search for your roadmap features and add any that are missing under the appropriate category to the Master Feature list.
2. Make sure all features that fall under your area of responsibility are assigned to you.
3. Add any important detail about the feature that is missing or that would be valuable to others that might need to help you validate or gather requirements for the feature. 
4. **Assign Releases:** Features can have one or many releases assigned as they may appear on different roadmap/planning views for different purposes. Below is an outline of our current structure of releases in productboard:
 * **Exact Releases:** (when known) Examples: 5.22, 5.24, 1.30, Mattermost 6.0.
 * **Sequence:** Now, Next, Later.
5. **Setting the Status:** There are six statuses throughout the life of a feature:
 * **Idea:** When you have a single request or an idea for a feature it starts out in this status. As new customer insights come in, you'll be able to attach them to this idea to validate and measure demand.
 * **Under Consideration:** This status is used to identify features that are demand validated, but we remain undecided if we'll build them (for various reasons).
 * **Planned:** Features that we've validated and decided to build are planned. These features should all have a release assigned (if scheduling is unknown, assign to the release called **backlog**.
 * **In Development:** All features actively being worked on by UX or R&D belong to this status.
 * **Postponed:** If a feature is cut from a release, followers of the feature need to be notified. Currently, productboard only notifies followers when a status changes or they're explicitly mentioned. We've added this status to ensure followers of a feature can stay informed when features are cut.
 * **Won't Do:** This is a status often used after the **Under Consideration** status if we decide for any reason not to build a feature that is demanded by the market. It's important to keep track of for future cases of demand. If you set a feature to this status, please be sure to provide the reason we won't do it. This reason should be in a format that can be shared with propspects/customers.
  
### 1d Pushing/linking features in Jira

We've enabled the productboard Jira integration which allows us to both push features to Jira as new tickets as well as link existing Jira tickets to features. This is done from the detail view of a feature.

Two very important notes regarding this integration:

* Once linked, if you update the details (most importantly, the description) in either Jira or productboard, they are synced and both will update.
* If you are linking an existing Jira ticket, be aware that your source will overwrite your destination.

#### Do’s and Don’ts

**Do's**

* Do reorder your features and play around with scoring your features.
* Do add sub-components if you feel they are appropriate and do not exist anywhere else.
* Do create your own feature views with custom prioritization scores (using existing drivers).
* Do post requests for all of the following in the [productboard channel](https://community.mattermost.com/core/channels/pm-feature-request-and-roadmap-tool).

  * New drivers or edits to driver names.
  * New top level components.
  * Renaming, removal or reorganization of top level components.

* Do feel free to reach out to Dennis, Jason, or Aaron for any questions.

**Don'ts**

* Do not reorder top level components - learn more about components, subcomponents, and features.
* Do not remove/rename any components or sub-components.
* Do not rename or adjust others' prioritization score models.
* Do not remove or rename drivers.

![](../../../../.gitbook/assets/productboard-prioritization.png)

### 1e Setting driver values

To help score and evaluate priority of features, you can calculate and communicate “the why” in a prioritization view (it's recommended to set up a custom view for your team's features). In addition to the **User Impact Score**, there are two custom score columns that we set up as examples. _Note: You'll likely want to setup your own custom scores based on your area's priorities._

* **Happiness:** Delighters & requests/problems to solve coming from prospects or customers.
* **Ops & Strategy:** Test infrastructure, technical debt, performance, maintenance, support cost reduction, packaging and pricing, feature discovery, branding, etc.

Each of these custom score columns has its own specific drivers that you can rate from 1 - 5. The more data you include here for each feature, the more accurate and useful the prioritization board will be.

### 1f Publishing features in the Internal portal

To be added \(ETA May\).

### 1g Publishing features in the public portal

To be added \(ETA Q2/FY21\)

### 1h Key links in productboard

* [Insights](https://mattermost.productboard.com/insights)
  * [My inbox](https://mattermost.productboard.com/insights/my-inbox)
  * [Shared inbox](https://mattermost.productboard.com/insights/shared-inbox)
* [Features](https://mattermost.productboard.com/feature-board)
  * [Master Feature list](https://mattermost.productboard.com/feature-board/1097524-master-feature-list)
  * [Release tracking view](https://mattermost.productboard.com/feature-board/1097526-release-tracking-internal)
* [productboard Support](https://help.productboard.com/en/)

## 2 A Day in the life of a Customer Support Manager, Customer Success Manager, or Solution Architect

### 2a Stay up to date on feature status updates

Staying informed of status changes and comments on a feature is easy in productboard:

 1. Locate the feature on the [Master Feature list](https://mattermost.productboard.com/feature-board/1097524-master-feature-list).
 2. Click on the feature name to open the feature details card.
 3. Add yourself as a follower by clicking on the **+** symbol in the bottom left corner of the feature details card.

![add-followers2](https://user-images.githubusercontent.com/20331166/83704445-f6be5d80-a5c6-11ea-9ce5-6daf1f7b55ac.png)

[Learn more about productboard notifications](https://help.productboard.com/en/articles/1252670-how-do-notifications-work).

### 2b Adding feedback

New feedback from users and customers is sent to the [Insights board](https://mattermost.productboard.com/insights). Typically these are submitted by Product Managers, Support, Customer Success Managers, or Sales through integrations with email, Zapier, Zendesk, or others.

### 2c Creating notes

You can add a new note to capture feedback from a customer call. This is used to help identify customer problems, wants/needs, feature shortcomings, and any other areas for improvement that stem from interacting with customers. Essentially, think of this as a place to communicate the most important takeaways from customer calls that the Product team can help you with.

Important points about notes:

* Notes are specific to a customer/prospect.
* Notes can include multiple requests (Product Managerss can apply multiple elements from the note to different features if necessary).
* If you are not sure if the request or feedback should apply to an existing feature, you can simply capture the feedback as a note, assign it to the Product Manager overseeing that area, or leave it unassigned.

### 2d Adding insights directly to an existing feature

As a **Contributor** in productboard, you have access to view the [Master Feature list](https://mattermost.productboard.com/feature-board/1097524-master-feature-list). This is the view where the Product team organizes and prioritizes new features and functionality that is being considered or planned for Mattermost.

You can search and browse all features and ideas and even read the notes and portal cards from Product Managers for a detailed description of the feature/idea. In the case of planned features, you'll have complete insight into the status of the feature and a rough idea of where it sits on the roadmap.

Within the detailed view of individual features, you can view the full list of insights added by other Product Managers, Customer Success Managers, Customer Engineers, or Support Engineers. You also have the option to add insight directly to the feature itself.

![](../../../../.gitbook/assets/productboard-insights-master-feature-list.png)

### 2e Adding feedback (via Chrome extension)

Using the official [productboard Chrome extension](https://chrome.google.com/webstore/detail/productboard-make-product/mlpbdkpkicfkhgagnoamdcimmhdkakni) you can add notes from any page within Chrome (including SFDC, Zendesk, GitHub, HackerNews, Mattermost web, etc.) and streamline your workflow dramatically.

As long as you are logged into productboard, the connectivity to the Mattermost insights board is secure and seamless.

![](../../../../.gitbook/assets/productboard-chrome-extension.png)

**Pro tip:** If you keep your call notes in a browser app (such as Google Docs), you can highlight the sections related to feedback and quickly send them over to productboard with the extension.

## 3 A day in the life of a Dev Lead

### 3a Viewing the Master Feature list and customer insights

As a **Contributor** in productboard, you have access to view the [Master Feature list](https://mattermost.productboard.com/feature-board/1097524-master-feature-list). This is the view where the Product team organizes and prioritizes new features and functionality that is being considered or planned for Mattermost. You can search and browse all features and ideas and even read the notes and portal cards from Product Managers for a detailed description of the feature/idea. In the case of planned features, you'll have complete insight into the status of the feature and a rough idea of where it sits on the roadmap. Although only Product Managers are able to modify the **Effort** estimate, it's highly encouraged for you to review and provide your feedback to your Product Manager as well!

Within the detailed view of individual features, you can view the full list of insights added by other Product Managers, Customer Success Managers, Customer Engineers, or Support Engineers.

### 3b Monitoring the release schedule

You'll also have access to the [release tracking view](https://mattermost.productboard.com/feature-board/1097526-release-tracking). From here you can monitor progress of all features company-wide (by release). This will be especially useful when a release is nearing to ensure that reporting of your team's progress (which features are on track or at risk) is communicated accurately.

## 4 A Day in the life of a productboard viewer (everyone)

### 4a Next 3 months, next 6 months, future candidates in the Portal view

The portals will serve as our internal (and, in the future, external) communication of our product roadmap. You'll have access to all internal product portals where we outline what we've released, what we're working on now, next and later.

To view the Portal, log in to [mattermost.productboard.com](https://mattermost.productboard.com) using your OneLogin account then click on the fourth icon in the left-hand navigation):

![](../../../../.gitbook/assets/productboard_portal_nav.png)

## 5 Frequently Asked Questions (FAQs)

### What's the difference between Confluence and productboard?

Productboard is for ideation, validation, prioritization, and requirements gathering. It will help us with all of the following:

* Deciding **what** to build and **why**.
* Deciding **when** to build it (and the order in which to build it).
* Sharing our planning progress with internal and external stakeholders.

The Enterprise team uses Confluence for communicating in detail both the **what** (requirements we gathered) and the **why** (problem/use cases we're solving for) to the dev team - after we've decided to build something. They'll determine the how. They'll also spec it out further in Confluence, and track progress in Jira.
