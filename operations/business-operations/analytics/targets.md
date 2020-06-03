# Targets

## Targets in Data Warehouse

Targets are stored in our Data Warehouse to automate **Target vs Actual** & **Attainment** tracking.

* **Target vs Actual** compares targets set for a given period to the actual values reached.
* **Attainment = Actual / Target**

### Existing Targets

* Top Line Level
  * [ARR](https://handbook.mattermost.com/operations/business-operations/analytics/metrics-definitions#arr-annual-recurring-revenue)
    * ARR by Month
    * ARR Churn by Month
    * ARR Expansion by Month
    * ARR New by Month
  * [Bookings](https://handbook.mattermost.com/operations/business-operations/analytics/metrics-definitions#bookings)
    * Bookings by Month
    * New Bookings by Month
    * Expansion Bookings by Month
    * New & Expansion Bookings by Month
    * Renewal Bookings by Quarter
* Segment Level
  * New & Expansion Attainment by Segment by Month
    * New & Expansion Attainment = New & Expansion Bookings + Leftover Expansion
  * Renewal Bookings by Segment by Quarter
* Rep Level (AE/CSM)
  * New & Expansion Attainment by Rep by Month
    * New & Expansion Attainment = New & Expansion Bookings + Leftover Expansion

* ### Upcoming Targets

* TEDAS 7 Day
* Renewal Bookings by Rep by Quarter

### Requesting a New Target

Reach out to us in [BizOps](https://community.mattermost.com/private-core/channels/bizops)

## Updating Existing Targets

### Requirements

* Access to Mattermost GitHub Organization
  * Confirm by finding your name [here](https://github.com/orgs/mattermost/people)
* Access to Mattermost Data Warehouse Private Repo
  * Confirm by trying to access [this link](https://github.com/mattermost/mattermost-data-warehouse-internal)
* You must be listed as one of the owners of a target

### Updating an Existing Target

1. Find the file in our [repo](https://github.com/mattermost/mattermost-data-warehouse-internal) with the target you need to update
2. Click into the file
3. Click the pencil that says "Edit this file"
4. Update the file
   * Do no update the first line of the file
   * Make sure you are using csv formatting
5. Scroll down
6. Select "Create a new branch for this commit and start a pull request."
7. Name your branch "update\_\[name of file you updated\]"
   * If you updated _arr\_by\_mo.csv_, name it "_update\_arr\_by\_mo"_
8. Click "Propose file change"
9. Name PR "Updating \[name of file you updated\]
   * If you updated _arr\_by\_mo.csv_, name the PR "_Updating arr\_by\_mo"_
10. You do not need to fill out anything in the "Write" section
11. Click "Create pull request"
12. Notify us in [BizOps](https://community.mattermost.com/private-core/channels/bizops) that you have submitted a PR



