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

_**= Tenure Score + License End Score + Ticket Score + Task Score**_

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

Financial numbers cater to a wide range of teams. Below you will find information on ACV, TCV, and ARR. **ACV & TCV are relevant to Sales and ARR relevant to Finance and CS.**

### TCV \(Total Contract Value\)

_**What the customer bought**_

* TCV measures revenue from across the entire contract a customer signs
* Recognized **only** in the Closed Won Month
* `TCV = Total Contract Value`

### ACV \(Annual Contract Value\)

_**What the customer bought annualized for the first year of their contract**_

* Recognized **only** in the Closed Won Month
* Calculation for deals &gt;= 12 months
  * `ACV = (Total Contract Value / (End Date - Start Date)) * 365`
* Calculation for deals &lt; 12 months
  * `ACV = Total Contract Value`

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

### Bookings

_**Standard financial term used to define how much sales credit is recognized for a deal. This is also the basis for all commission plans starting in FY21.**_

* If term length &gt;= 1 year, bookings = ACV
* If term length &lt; 1 year, bookings = TCV
* Net New and Expansion only
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

![](../../../.gitbook/assets/image%20%2861%29.png)

## Google Analytics

All Google Analytics data in Snowflake is at a **daily** level. See [limitations](https://handbook.mattermost.com/operations/business-operations/analytics/metrics-definitions#google-analytics-limitations).

### Organic Traffic

* Organic Web Traffic is the **daily** unique visitors to \*.mattermost.org, \*.mattermost.com who originate from non-paid sources
* Organic Search Traffic is the **daily** unique visitors to \*.mattermost.org, \*.mattermost.com who originate from an organic Google search

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

* Net Promoter Score \(NPS\) measures customer experience and predicts business growth
* Respondents are grouped as follows:
  * Promoters \(score 9-10\) are loyal enthusiasts who will keep buying and refer others
  * Passives \(score 7-8\) are satisfied but unenthusiastic customers who are vulnerable
  * Detractors \(score 0-6\) are unhappy customers who can damage your brand
* Net Promoter Score = % Promoters - % Detractors
  * NPS ranges from -100 \(every customer is a Detractor\) to 100 \(every customer is a Promoter\)
* Mattermost's NPS is based off of a 1-10 ranking provided by customers
  * If customers provide rankings 2+ times in a day, the last ranking of the day is used for NPS

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

The distinction between an individual server's Telemetry-Enabled Active Users and the TEDAU metric is important to note. Telemetry-Enabled Active Users are the collection of users hosted by a telemetry-enabled production server, that have visited the Mattermost site in the last 24 hours. The TEDAU metric is the rolling 7-day average sum of these users across all servers



## Trials

### Trial Requests

**All Trial Requests**

* Number of trial license requests via [https://mattermost.com/trial](https://mattermost.com/trial)

**Enterprise Trial Requests**

* Number of trial license requests via [https://mattermost.com/trial](https://mattermost.com/trial) from Named Accounts or Enterprises with 5,000+ employees, in America, EMEA, Australia or Japan.

