# Metrics Definitions

## Contact Us Requests

#### All Contact Us

* Number of contact us requests via [https://mattermost.com/contact-us](https://mattermost.com/contact-us)

#### Enterprise Contact Us Requests

* Number of contact us requests via [https://mattermost.com/contact-us](https://mattermost.com/contact-us) from Named Accounts or Enterprises with 5,000+ employees, in America, EMEA, Australia or Japan.

## Contributors

### GitHub Contributors

* Members of the open source community with contributions to Mattermost GitHub repositories
  * This does not include internal Mattermost staff
* Definitions:
  * First Time Contributors: The first month someone contributes, they considered a First Time Contributor the whole month.
  * Old Contributors: Anyone that is not a First Time Contributor
  * First Contribution: The first contribution ever made by someone. Any following contributions will not be considered a First Contribution
  * Examples:
    * Person A
      * 2019-01-02 Contribution 1
      * 2019-01-04 Contribution 2
      * 2019-01-05 Contribution 3
    * Would count as
      * 1 First Time Contributor + 1 First Time contribution + 2 Non First Contributions

## CS Account Health Score

Customer Success Account Health Score represents the overall health of a Mattermost SFDC Account

* **Account Has Open Opportunity w/ Renewal Risk Status = 'At Risk'**
  * Account Health Score = 20%
* **Account Has Open Opportunity w/ Renewal Risk Status = 'Early Warning'**
  * Account Health Score = 50%
  
* **_Note - If account has open opportunity w/renewal risk status of At Risk or Early Warning, it will override all other Healthscore metrics._

* **Account Has No Open Opportunity w/ Renewal Risk Status = 'At Risk or 'Early Warning'**
  * _**Account Health Score = Tenure Score + License End Score + Ticket Score + Task Score**_
    * **Tenure Score = 25 \* Tenure Health %**
      * Tenure Health %:
        * Tenure &lt;= 0.5 Years: **10%**
        * Tenure Between 0.5-1 Years: **50%**
        * Tenure Between 1-2 Years: **75%**
        * Tenure &gt; 2 Years: **100%**
    * **License End Score = 25 \* License End Health %**
      * License End Health %:
        * License End &lt;= 15 Days From Now: **10%**
        * License End Between 16-30 Days From Now: **25%**
        * License End Between 31-60 Days From Now: **75%**
        * License End Between 61-90 Days From Now: **90%**
        * License End &gt; 90 Days From Now: **100%**
    * **Ticket Score = 25 \* Ticket Health %**
      * Ticket Health %:
        * Count of Tickets Past 90 Days &gt;= 5: **25%**
        * Count of Tickets Past 90 Days = 0: **50%**
        * Count of Tickets Past 90 Days Between 3-4: **75%**
        * Count of Tickets Past 90 Days Between 1-2: **100%**
    * **Task Score = 25 \* Task Health %**
      * Task Health %:
        * Days Since Most Recent Task &gt;= 90: **25%**
        * Days Since Most Recent Task Between 60-90: **50%**
        * Days Since Most Recent Task Between 30-60: **75%**
        * Days Since Most Recent Task &lt;= 30: **100%**

## Downloads

### **Monthly Server Downloads**

#### All Server Downloads

* Number of successfully completed unique TE \(Team Edition\) + EE \(Enterprise Edition\) downloads by unique client IP address per month, from mattermost.com. Includes web browser and wget / curl downloads.
  * \*Note: Excludes GitLab Omnibus downloads, Docker \(Dockerhub\) downloads, and Bitnami or other cloud image downloads, as we don’t currently have a good way of measuring these downloads.

**Monthly Enterprise Account Server Downloads**

* Number of Monthly Server Downloads among companies and organizations with over 5,000 employees.

**New Monthly Server Downloads from Named Enterprise Accounts**

* The first contact or lead from a Named Enterprise Account who is attached to an Account either manually by an AE or by Marketo, and who provides a business email on mattermost.com/download after downloading the Mattermost server binary. 
  * Excludes Salesforce account types equal to Customer or Partner

### Monthly App Downloads

#### All Desktop App Downloads

* Number of successfully completed desktop application downloads by unique client IP address per month, from mattermost.com. Includes web browser and wget / curl downloads.
  * \*Note: Excludes GitLab Omnibus downloads, Docker \(Dockerhub\) downloads, and Bitnami or other cloud image downloads, as we don’t currently have a good way of measuring these downloads.

## Finance

Financial numbers cater to a wide range of teams. Below you will find information on ACV, TCV, and ARR. **ACV, TCV, Bookings are relevant to Sales/CS and ARR relevant to Finance/CS.**

### TCV \(Total Contract Value\)

_**What the customer bought**_

* TCV measures revenue from across the entire contract a customer signs
* Recognized **only** in the Closed Won Month
* `TCV = Total Contract Value`

### ACV \(Annual Contract Value\)

_**What the customer bought annualized for the first year of their contract**_

* Recognized **only** in the Closed Won Month
* `ACV = (Total Contract Value / (End Date - Start Date)) * 365`

### Bookings

_**Standard financial term used to define how much sales credit is recognized for a deal. This is also the basis for all commission plans starting in FY21.**_

* **If term length &gt;= 1 year, Bookings = ACV**
* **If term length &lt; 1 year, Bookings = TCV**
* **Net New and Expansion only**
* Why would we have deals &lt; 1 year?
  * True-ups
    * Customer owes MM 30K for Q1FY21 
    * Booking would be 30K on the first day of Q2 \(May 1\)
  * Co-Term Renewals
  * Ramped Deals
    * Customer signs a 3 year deal on Feb 28, 2020. Year 1 = 50K, Year 2 = 100K, Year 3 = 150K
    * Bookings
      * 2/28/20: 50K
      * 2/28/21: 100K - 50K = 50K
      * 2/28/22: 150K - 100K = 50K

### ARR \(Annual Recurring Revenue\)

_**What the customer bought normalized for one year length & reoccurs for length of contract**_

* ARR is the value of the contracted recurring revenue of your term subscriptions normalized to a one-year period
* Recognized from **start to end** of contract
* `ARR = (Total Contract Value / (End Date - Start Date)) * 365`
* ARR increases and decreases based on the following categories of change:
  * New: Increase in ARR from $0 to &gt; $0 & New Logo never seen before
    * Caused by a brand new and never before see Account signing a contract
  * Expansion: Increase in ARR by an Account
    * Caused by seat increase, price increase, or product upgrade
  * Resurrection: Increase in ARR from $0 to &gt; $0 & by a known Account
    * Caused by an Account churning and returning to Mattermost
  * Contraction: Decrease in ARR by an Account
    * Caused by seat decrease, price decrease, or product downgrade
  * Churn: Decrease in ARR from &gt; $0 to $0 by an Account
    * Caused by an Account moving completely off of Mattermost

### TCV vs. ACV vs. ARR

Example:

* Opportunity: [Example Opportunity](https://mattermost.lightning.force.com/lightning/r/Opportunity/0063600000eRMmcAAG/view)
* Close Date: 2019-05-07
* Amount = $250
* Start Date: 2019-06-15
* End Date: 2022-06-14
* Metrics Breakdown \(see graph below\):
  * ACV one-time $83 in May 2019 
  * TCV one-time $250 in May 2019 
  * ARR $83 from June 2019 until June 2022

![](https://github.com/mattermost/mattermost-handbook/tree/361ff3b848b21f06fd8587e792144d81efed511e/.gitbook/assets/image%20%2861%29.png)

## Google Analytics

All Google Analytics data in Snowflake is at a **daily** level. See [limitations](https://handbook.mattermost.com/operations/business-operations/analytics/metrics-definitions#google-analytics-limitations).

### Organic Traffic

* Organic Web Traffic is the **daily** unique visitors to \*.mattermost.org, \*.mattermost.com who originate from non-paid sources
* Organic Search Traffic is the **daily** unique visitors to \*.mattermost.org, \*.mattermost.com who originate from an organic Google search

### Unique Pageview \(UPV\)

A **Unique Pageview \(UPV\)** aggregates pageviews that are generated by the same user during the same [session](https://handbook.mattermost.com/operations/business-operations/analytics/metrics-definitions#session). The metric combines the pageviews that are from the same person \(a user in Google Analytics\), on the same page, in the same [session](https://handbook.mattermost.com/operations/business-operations/analytics/metrics-definitions#session), and counts them as one.

* Unique Page Views \(UPV\) are calculated as the **daily** count of distinct pageviews per user per session to view a Mattermost web property webpage \([list of web properties defined in Google Analytics Accounts](https://handbook.mattermost.com/operations/business-operations/analytics/metrics-definitions#google-analytics-accounts)\).

### Session

A **session** is a group of user interactions within a website that take place within a given time frame. A single session can contain multiple page views, events, social interactions, and ecommerce transactions. A single user can open multiple sessions. Those sessions can occur on the same day, or over several days, weeks, or months.

#### Session Expiration

As soon as one session ends, there is then an opportunity to start a new session. There are two methods by which a session ends:

* Time-based expiration:
  * After 30 minutes of inactivity
  * At midnight
* Campaign change:
  * If a user arrives via one campaign, leaves, and then comes back via a different campaign.

### Google Analytics Accounts

1. mattermost.com
2. about.mattermost.com \(old mattermost.com\)
3. mattermost.org
4. developers.mattermost.com
5. integrations.mattermost.com
6. docs.mattermost.com
7. handbook.mattermost.com
8. licensing.mattermost.com
9. mattermost.gitbook.io/jira-plugin
10. pre-release.mattermost.com \(which is old community.mattermost.com\)
11. mattermost.zendesk.com

### Google Analytics Limitations

* [Stitch](https://handbook.mattermost.com/operations/business-operations/data-engineering#stitch-data) is used to pull Google Analytics data into Snowflake
  * Stitch is only able to pull data at a daily level
  * Aggregating up daily level to a monthly level causes double counting of users that may have visited the site more than one time in a given month.

## Hiring

* WIP

## Net Promoter Score \(NPS\)

Net Promoter Score is a standardized measure used by many organizations to measure and understand customer experience. It is a good indicator of customer satisfaction and growth. Mattermost NPS is calculated using user NPS responses provided by users with the NPS plugin enabled on their Mattermost server. Users can submit multiple scores, so in order to accurately represent NPS, the latest score is used when calculating current NPS. To track NPS historically, the latest user score submitted on or before the historical record month is used.

* Net Promoter Score \(NPS\) measures customer experience and predicts business growth
* Respondents are grouped as follows:
  * Promoters \(score 9-10\) are loyal enthusiasts who will keep buying and refer others
  * Passives \(score 7-8\) are satisfied but unenthusiastic customers who are vulnerable
  * Detractors \(score 0-6\) are unhappy customers who can damage your brand
* Net Promoter Score = 100 \* \(% Promoters - % Detractors\)
  * NPS ranges from -100 \(every customer is a Detractor\) to 100 \(every customer is a Promoter\)
* Mattermost's NPS is based off of a 1-10 ranking provided by customers
  * If customers provide rankings 2+ times in a day, the last ranking of the day is used for NPS

## Support Tickets

### Definitions

#### Ticket Status

* **New -** Ticket created that has not been assigned a support agent.
* **Pending -** The support agent asks the customer a question and is waiting for their response.
* **Pending - Do not Close -** Checkbox on the ticket. This is used for tickets that are expected to be open for a long period of time. This stops the clock. Examples are customer requests ticket remain open after a solution is provided, the customer is on vacation, or the customer is out ill.
* **On Hold -** The support agent reaches out to an internal team and is waiting to hear back. Any ticket that is tied to a JIRA ticket is placed on hold. Internal teams include product, development or customer success.
* **Solved -** Support agent provides a solution to the customer. Status in the solved status for 48 hours before it is set to “Closed” status While the ticket is in a “Solved” status any response from the customer will re-open the ticket.
* **Closed -** If no response is recorded a ticket in a Solved status will be set to Closed automatically after 48 hours. A response to the ticket will open a new ticket.

#### Ticket Level

* **Level 1: Critical Business Impact:** Critical issue on production system preventing business operations. A large number of users are prevented from working, and no procedural workaround is available.
* **Level 2: Major Business Impact:** Major issue on the production system severely impacting business operations.
* **Level 3: Moderate Business Impact:** Moderate issue causing a partial or non-critical loss of functionality on the production system. A small number of users are affected.
* **Level 4: Minor Business Impact:** Minor issue on non-production system or question, comment, feature request, documentation issue or other non-impacting issues.

#### Ticket Measures

* **First reply time:** The duration between ticket creation and the first public agent reply on the ticket.
* **Next reply time:** The duration between ticket's first reply time and next reply time, unless otherwise communicated.

**SLA's**

**First Reply Time - Premium and E20 only**

**Premium**

* L1 - 1 hour
* L2 - 2 hours
* L3 - 8 hours
* L4 - 24 hours

**E20**

* L1 - 4 hours
* L2 - 8 hours
* L3 - 24 hours
* L4 - next business day

**Next Reply Time**

**Premium**

* L1 - 2 hours
* L2 - 4 hours
* L3 - 24 hours
* L4 - 24 hours

**E20**

* L1 - 4 hours
* L2 - 8 hours
* L3 - 24 hours
* L4 - 24 hours

## TEDAS

TEDAS stands for _Telemetry-Enabled Daily Active Servers_. It is the count of unique, [production servers](metrics-definitions.md#server-considerations) sending telemetry \(“activity"\) data to Mattermost on a given date. Each component of TEDAS can be described as follows:

* Telemetry Enabled:
  * Servers have “Error Reporting and Diagnostics” or “Security Alert” enabled in System Console.
* Daily Active:
  * Response to Mattermost's call to collect telemetry data recorded on a given date.
    * For a server to respond, it must be online and telemetry enabled.
* Servers:
  * Servers host Mattermost instances for teams & organizations.
  * Each team/organization can have one-to-many servers installed to host their instance.
    * Small/Medium teams typically leverage a single server.
    * Large teams can leverage Enterprise Edition features to create server clusters that allow them to scale their instance.

### Server Considerations

TEDAS only measures the count of active production servers. The Mattermost.server\_daily\_details table is used to calculate TEDAS and only contains production servers. Mattermost.server\_daily\_details is derived from the Events.security table.

The Events.security table logs all server responses to Mattermost's call to collect telemetry data. The Server type responses include test, development, and production servers. Conditional logic is used to filter out non-production servers from the Events.security table and insert them into the Mattermost.server\_daily\_details table.

* Logic to identify production servers within the Events.security table is as follows:
  * Mattermost Version matching recognized format
    * `version LIKE '_.%._._.%._'`
    * Other version formats are not valid because they indicate a test, development, or custom built instance
  * No "Dev Builds" and "Ran Tests" recorded
    * `dev_build = 0`
    * `ran_tests = 0`
  * Registered Users &gt;= Active Users
    * `user_count >= active_user_count`
    * Data anomalies occur causing servers to show  active users &gt; provisioned users - these servers must be excluded.

#### **Non-production servers**

Non-production servers are not included in TEDAS calculations. Test and development servers are non-production servers that can be spun up for testing and various other use cases.

#### Server Age

The age of a server is determined by the server's first active date. This is the minimum date a response to Mattermost's call to collect telemetry data is recorded. It can be thought of as the server's first recorded telemetry-enabled date i.e. first active date. The age of the server is calculated as a function of this date. It is the days between the server's first active date, discussed above, and the current date \(or other relative date being used as a comparison to calculate server age at any point throughout its lifetime\).

* Server Age = Current Date - Server First Active Date

### TEDAS Caveats

There are additional data quality issues within the Events.security table that need to be addressed before inserting the verified production servers and calculating TEDAS. The Events.security table is supposed to contain 1 record per server per day. This is not always the case: ~2% of server id's have multiple rows per day. To select a single record per production server we must:

* Identify the row per production server containing the maximum number of active users on the given date.
  * If the maximum number of active users = 0 then we select the most recently logged row based on the "hour" field value.

## TEDAU

**TEDAU** stands for _Telemetry-Enabled Daily Active Users_. It is a metric that takes the rolling 7-day average of the sum of all "Active Users" logged by [telemetry-enabled production servers](metrics-definitions.md#tedas) on a given date. The TEDAU calculation sums the active\_user\_count column in the Mattermost.server\_daily\_details table, and then averages that value over the last 7 days.

### TEDAU Caveats

TEDAU is the rolling 7-day average sum of active users for only verified production servers that are telemetry-enabled \(described in [this TEDAS section](metrics-definitions.md#server-considerations)\). All other servers, and their active user counts, are ignored as they represent testing, dev, and one-off user case environments that skew the results.

#### Telemetry-Enabled Active Users vs. TEDAU Metric

The distinction between an individual server's Telemetry-Enabled Active Users and the TEDAU metric is important to note. Telemetry-Enabled Active Users are the collection of users hosted by a telemetry-enabled production server, that have visited the Mattermost site in the last 24 hours. The TEDAU metric is the rolling 7-day average sum of these users across all servers.

## Server Activations

A **Server Activation** is defined as the first date a production server sends telemetry data to Mattermost. In order to send telemetry data to Mattermost, a production server must be setup and activated by the end user. When a production server is first activated its telemetry feature is automatically enabled, which sends security diagnostics information to Mattermost via Segment \(soon transitioning to Rudder\). The server will continue to send this information on a daily basis until this telemetry feature is disabled by a system admin. A server activation is only captured and counted on the first telemetry-enabled date associated with a specific server.

## Monthly Active Users

**Monthly Active Users \(MAU\)** are users that have performed an event on or within 30 days of a given date. User events are triggered when a user interacts with the Mattermost platform from their desktop or mobile device. After a user performs an event, that user will remain in MAU for 30 days. After that time the user will fall out of MAU and be classified as "Disengaged".

### MAU Engagement Lifecycle Segments

Monthly active users are categorized into **engagement lifecycle segments**. There are 5 engagement lifecycle segments: Persisted, First-Time Active, Reengaged, Newly Disengaged, and Disengaged. Each segment is derived from the timeline from when a user performs an event. Each Engagement Lifecycle Segment is defined as follows:

* **First-Time Active**: The first time a user performs an event on the Mattermost platform and is classified as a Monthly Active User.
* **Reengaged**: A user performs an event for the first time after &gt;= 31 days of inactivity on the Mattermost platform.
* **Persisted**: A user that performed an event in the last 30 days that does not fall into "First-Time Active" or "Reengaged" MAU Engagement Lifecyle Segments.
* **Newly Disgengaged**: A user, that was previously in MAU, that has not performed an event within 30 days of their last event. A user is only "Newly Disengaged" on the 31st day of inactivity. 
* **Disengaged**: A user, that was previously in MAU, that has not performed an event &gt; 31 days of their last event. A "Newly Disengaged" user becomes "Disengaged" on their 32nd+ day of inactivity.

### MAU Considerations

#### MAU Events

Currently only a subset of possible events, dubbed "whitelist" events, count towards MAU. The reason only a subset of events are captured is a result of exceeding Segment's \(third-party event logging service\) row limit. In the future, event logging will transition to rudder \(another third-party event logging service\), and the list of events that count towards MAU will become more expansive.

## Trials

### Trial Requests

**All Trial Requests**

* Number of trial license requests via [https://mattermost.com/trial](https://mattermost.com/trial)

**Enterprise Trial Requests**

* Number of trial license requests via [https://mattermost.com/trial](https://mattermost.com/trial) from Named Accounts or Enterprises with 5,000+ employees, in America, EMEA, Australia or Japan.

