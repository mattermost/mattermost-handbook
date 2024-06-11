# Creating New Jira Bug Tickets

Bugs are any “obvious errors” on how the product or a feature is functioning as well as any UI issues. If you’re not reporting an obvious error, please file a Story ticket instead. Errors on [unsupported platforms](https://docs.mattermost.com/install/software-hardware-requirements.html) are not considered bugs.

## 1. Check that you have permissions to create tickets in Jira

* If you don't already have a Jira account or permissions to create Jira tickets, you can request access through [the Mattermost IT helpdesk](https://helpdesk.mattermost.com/support/home).

## 2. Confirm you’re filing a new issue

* Search existing tickets in Jira's "Mattermost" project to confirm your issue isn’t already filed by someone else.

## 3. Confirm the bug is not a confidential issue

* If your issue involves security or if it involves confidential information or customer information, please mark the bug ticket as internal.

## 4. Information needed on Mattermost bug tickets

* **Steps to reproduce:** How can we reproduce the issue.
* **Expected behavior:** Describe what you’re expecting to see.
* **Observed behavior:** Describe your issue in detail. What did you see happen? Please include relevant error messages and/or screenshots.
* **Severity:** Choose appropriate severity from the drop-down. Severity levels and descriptions are documented [here](https://handbook.mattermost.com/operations/research-and-development/product/development-process/new-bug-tickets/bug-severity-guidelines).

## 5. Additional helpful information

* **Labels:** Add a `customer-bug` label if the ticket is based on a customer bug report. Add a `community-bug` label if the ticket is based on a community bug report.
* **Environment:** There is an ``Environment`` field with drop-down options to choose whether the bug was found in Cloud test servers, Cloud production servers, Self-Hosted test servers, Self-Hosted production servers, Desktop app, Mobile app, or in Master/PR testing.
* **Attachments:** Please include screenshots and/or videos of any helpful error messages and snippets of what you are seeing.
* **Possible fixes:** If you can, link to the line of code that might be responsible for the problem.
* **Regression:** Please re-test your issue \(if possible\) on the previous Mattermost version at [https://prev.test.mattermost.com](https://prev.test.mattermost.com) to see if the bug is a recent regression.
* Add any additional relevant details if it helps make the bug more clear. For example, you can add details on Mattermost server and version, OS and version, Mattermost mobile app version, Mattermost desktop app version, and any notable Mattermost configurations \(such as HA, Elasticsearch, image proxy, SSO\).

## 6. Assigning new tickets to a team

* If you know which team would own fixing the bug, you can assign the ticket directly to that team.
* Otherwise, you can leave the team ``Unassigned`` and the Program Manager assigns the ticket. The Program Manager follows the ~Bugs channel on a daily basis.
