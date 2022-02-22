# MLT Metrics

This section outlines metric definitions maintained by finance for reporting to investors.

1. These are metrics for MLT discussions.
   1. Any metrics shared by a department with the MLT will be asked to work with business operations to define the metric to be listed on this page under standardized naming and MLT definition checklist.
2. Definitions center around ARR, GMA Magic Number, and NPS.

MLT definitions checklist

1. Qualifiers precede metrics names
   1. i.e. use ""Gross Margin Adjusted Magic Number" instead of "Magic Number, Gross Margin Adjusted" to avoid ambiguity when label names are truncated.
2. Metric names should only have one possible interpretation.
3. All MLT Metrics should have a unique acronym shorter than 8 characters.
   1. Metrics will inevitably be shortened, pre-emptive definition avoids collision.

## ARR

### Revenue Metrics

_50% complete_

* **New ARR**: ARR from new logos signed, with license start dates in the respective period.
* **Expansion ARR**: ARR from existing customers with a cross-sell/upsell deal, with license start dates in the respective period \(e.g. increased licensed seat count, upgrading from E10 to E20\).
* **Contraction ARR:** Reduction in ARR from existing customers, but where they are still paying Mattermost based on date of license change.
* **Churn ARR**: Reduction in ARR from an existing customer where they are no longer paying Mattermost based on the license end date.
* **Total ARR:** Total ARR ending in a specific period.
* **IARR: Incremental Annual Recurring Revenue**: \(New ARR + Expansion ARR\) - \(Contraction ARR + Churn ARR\)
* **Count of New Logos** \(1%\): Count of new logos signed, with start dates in the respective period.
* **Count of Churned Logos** \(1%\): Count of logos lost where an existing customer is no longer paying Mattermost.

### Active Servers

_50% complete_

* **Monthly Server Downloads**: Number of successfully completed unique TE + EE downloads by unique client IP address per month, from mattermost.com. Includes web browser and wget / curl downloads.
  * Note: Excludes GitLab Omnibus downloads, Docker \(Dockerhub\) downloads, and Bitnami or other cloud image downloads, as we don’t currently have a good way of measuring these downloads.
* **Monthly Enterprise Account Server Downloads:** Number of Monthly Server Downloads among companies and organizations with over 5,000 employees.
* **New Monthly Server Downloads from Named Enterprise Accounts** \(1%\)**:** The first contact or lead from a Named Enterprise Account who were attached to an opportunity either manually by an AE or by Marketo, and who provides a business email on mattermost.com/download after downloading the Mattermost server binary. Excludes Salesforce account types equal to Customer or Partner.
* **TEDAS:** _Telemetry Enabled Daily Active Servers:_ ****Number of unique servers that have “Error Reporting and Diagnostics” or “Security Alert” enabled in System Console, and send telemetry “activity data” \(such as number of users\).

### Active Users

_10% complete_

* **Total Active Users**: The total number of user accounts created on a single Mattermost server. Excludes deactivated accounts, deleted accounts and bot accounts. This is also the “Total Active Users” measure shown in **System Console > Site Statistics**.
* **Registered Authorized Users**: Same as **Total Active Users**.
* **Total Registered Users**: The total number of user accounts created on a single Mattermost server, including deactivated and deleted accounts.
* **DAU**: _Daily Active Users:_ The total number of users who viewed the Mattermost site in the last 24 hours. Excludes bot accounts. This is also the “Daily Active Users” measure shown in **System Console > Site Statistics**.
* **TEDAU:** _Telemetry Enabled Daily Active Users:_ The total number of users averaged over the last 7 days, who viewed the Mattermost site in the last 24 hours from servers that have “Error Reporting and Diagnostics” or “Security Alert” enabled in System Console, and send telemetry “activity data” \(such as number of users\). Excludes bot accounts.
* **MAU**: _Monthly Active Users:_ The total number of users who viewed the Mattermost site in the last 30 days. Excludes bot accounts. This is also the “Monthly Active Users” measure shown in **System Console > Site Statistics**.
* **Active User Count**: A measure of the number of active users last 24 hours. **Legacy measure, do not use this for analysis or decision-making.**

## GMA Magic Number

### Gross Margin Metrics

_1% complete_

* **GMA Magic Number:** _Gross Margin Adjusted Magic Number_ \(1%\): Net New ARR in a period multiplied by Gross Margin in the period, divided by total Sales & Marketing expense in prior period.
* **NGMA Magic Number:** _Non-Gross Margin Adjusted Magic Number_ \(1%\) 
* **Gross Margin**: Net sales revenue minus cost of goods sold
  * **Net Sales Revenue:** 
  * **Cost of Goods Sold:** 

### Website traffic

_50% complete_

* **Organic Traffic:**
  * **Organic Web Traffic:** Monthly unique visitors to \*.mattermost.org, \*.mattermost.com who originate from non-paid sources.
  * **Organic Search Traffic:** Monthly unique visitors to \*.mattermost.org, \*.mattermost.com who originate from an organic Google search.

### Qualified Leads

_1% complete_

* **Enterprise Trial Requests:** Number of trial license requests via [https://mattermost.com/trial](https://mattermost.com/trial) from Named Accounts or Enterprises with 5,000+ employees, in America, EMEA, Australia, or Japan.
* **Enterprise Contact Us Requests:** Number of contact us requests via [https://mattermost.com/contact-us](https://mattermost.com/contact-us) from Named Accounts or Enterprises with 5,000+ employees, in America, EMEA, Australia, or Japan.
* **MQL:** _Marketing Qualified Lead:_ 
* **PQL:** _Product Qualified Lead:_ Installed free TE/E0 version from a Target Account interested in EE features.

## NPS

### Contributors

_10% complete_

* **90s Hiring vs Goal \(P0, P1, P2\)**: Difference between hiring plan and hires broken out by priority level \(P0, P1, P2\), function and time.
  * P0 - Roles which hiring managers have flagged as high need.
  * P1 \(1%\) - Roles which hiring managers have flagged as medium need.
  * P2 \(1%\) - Roles which hiring managers have flagged as nice-to-have.
* **Monthly Active Contributors:** Number of unique contributors in a given month who have posted at least one message on the Mattermost forums OR have committed at least one line of code to any of the publicly available Mattermost repositories on GitHub, including Mattermost Staff and those participating in a [paid R&D candidate audition project](https://docs.mattermost.com/process/developer.html#audition).
  * Note: Excludes translators, integration/solution creators and QA/UX contributors, as we don’t currently have a good way of measuring these contributors.
* **Monthly Code Contributors**: ****Number of unique contributors in a given month who have committed at least one line of code to any of the publicly available Mattermost repositories on GitHub, excluding members in the Mattermost GitHub organization.

### Product

_50% complete_

* **Product NPS**: The product net promoter score \(Product NPS\) measures user satisfaction of the product, calculated based on single question “How likely are you to recommend Mattermost?”. The score is based on a -100 to 100 scale, with the [calculation detailed here](https://en.wikipedia.org/wiki/Net_Promoter#How_it_works) ****gathered through in-product survey.
  * **End User Product NPS**: The Product NPS calculated among end users only \(ie. not among Team or System Admins\).
  * **System Admin Product NPS**: The Product NPS calculated among System Admins only.
  * **EE Product NPS:** The Product NPS calculated among all users in licensed E10 or E20 servers only.

### Customer success

_1% complete_

* **Customer NPS**: Customer satisfaction of the product, calculated based on single question “How likely are you to recommend Mattermost to a friend or colleague?", sent two days after booking or renewal is closed. The score is based on a -100 to 100 scale.
* **Support Metrics \(E10 and E20\)**: Metrics calculated based on Zendesk tickets opened by E10 and E20 customers. Tickets opened by non-subscribed organizations are not counted towards these metrics.
  * **Tickets Created**: Number of net new Zendesk tickets created.
  * **First Response Time \[Median, hours\]**: The median number of hours from when a ticket was opened in Zendesk to when the first response was sent to the customer.
  * **% First Response &gt;8 Business Hours**: % of newly opened Zendesk tickets whose first response time is greater than 8 business hours as defined in https://mattermost.com/support/.
  * **Resolution Time \[Median, hours\]**: The median number of hours from when a ticket was opened in Zendesk to when the ticket is resolved.
  * **% Resolution Time &gt;7 days**: % of newly opened Zendesk tickets whose first resolution time is greater than 7 days.
  * **% Resolution Time &gt;14 days**: % of newly opened Zendesk tickets whose first response time is greater than 14 days.
  * **Number of CSAT Responses**: \# of new CSAT \(Customer Satisfaction\) survey responses from customers whose Zendesk ticket was resolved.
  * **Customer Satisfaction Score**: % of newly submitted CSAT survey responses who responded “Yes” to the question .

For technical analytics definitions not covered here, see the [Analytics Playbook](https://docs.google.com/document/d/1__65LymlUfXLzOiSKD-G56j16Jlx1fRaIu714s3yxDU/edit#heading=h.sowg5wp7n9lk).

### Best practices

To be added.

DRI for this page is Jason Blais
