# Cloud Cost Optimization Reports
Early each month, a cost report is prepared with the spent of the previous month.
This report gets inputs from AWS monthly billing and Zesty cost per AWS account information.
That information is incorporated into various sheets, from which diagrams are created that are
embedded inside the monthly cost report.

## The reports - presentations
The Cloud Cost Optimization Reports can be found in Google Slides [here](https://docs.google.com/presentation/u/0/?tgif=d&q=Cloud%20Cost%20Optimization%20Report). Each month a new one is created, For example the one for the January 2024 is the [Cloud Cost Optimization Report #37](https://docs.google.com/presentation/d/1XsZHIQkfbet0uo_olQGZHWKr-qkHzCdvtHG8bD71jC0/edit?usp=sharing).

## Sheets and tools to create the reports
- The sheet where the all information is combined and then populated into the cost reports: [FY24 Cost tracking AWS accounts](https://docs.google.com/spreadsheets/d/1Gseyt1ByiiSC3fNyC1PI0cLByOJrkLhefEnP98LHNLQ/edit?usp=sharing)

- [Zesty's report with the savings per account](https://docs.google.com/spreadsheets/d/1OJ-khBQGHwucy_oqLHufPEl4NWJfnt78I-58qRp5Dmk/edit?usp=sharing)

- From that sheet, the older cost reports were populated and now it is used for the average cost per workspace [Monthly costs per environment](https://docs.google.com/spreadsheets/d/1S6qcnBa4eDpzR-74EzjVc11itoe1oUSanH0TRzHUP0k/edit?usp=sharing)

- Show the costs analysis in Cloud Production per type, such as S3, ELB, VPCs, NAT etc.
[Cost analysis by type](https://docs.google.com/spreadsheets/d/1zkYtsMO7PGp-5uJVmzUrKUiceIMZtKnGoqzc_Kaa--w/edit?usp=sharing)

- How much each [Cluster costs in Production](https://docs.google.com/spreadsheets/d/1r11NL6wxLJELTT_ln4fM4NoPB3yTZ8bhWWJZn4RQ78k/edit?usp=sharing)

- Shows the [AWS Cost Projection](https://docs.google.com/spreadsheets/d/1ANAiIinqb_MMBJ0KDcHodyBr0kL_Wl283SFra0dqYgQ/edit?usp=sharing)


# Cloud Infrastructure Cost KPIs

The Cloud SRE team uses certain KPIs to monitor cloud infrastructure costs from the engineering standpoint. These KPIs are used to help the business and the Cloud SRE team to set goals for cost optimization.

As of July 2021, the goals for the SRE team are to:

* Decrease the Average Cost Per Workspace \(APWC\).
* Keep development and test environments costs \(DM\) below 20% of total costs.
* Increase the WB fraction \(ratio of paid workspaces relative to total workspaces\).

Below are the primary and secondary KPIs used to measure each.

## Primary KPIs

### Average Production Workspace Cost

* **Description**: The fraction which compares the amount of Production Environment costs with the number of workspaces which are active in a given month of the Cloud Infrastructure service. Production Environment will be defined as the environment where we host all our customers, including paid and free workspaces.
* **Formula**: APWC = Production Environment Costs/Number of Workspaces

### Average Production Freemium Cost

* **Description**: An approximation of what free workspaces cost us. The fraction compares the amount of Production Environment costs with the number of active free workspaces.
* **Formula**: APFC = Production Environment Costs/Freemium Active Workspaces

  **Note:** Until February 2021 we measured all workspaces as active. Hibernation functionality was introduced in the last three days of February 2021.

### Average Subscription Workspace Cost

* **Description**: The fraction which compares the amount of Production Environment costs with the number of workspaces that have 11 or more users within a given month of the Cloud Infrastructure service. A paid workspace is defined as successful receipt of payment for the time period \(e.g. payment for the previous month completed, when measuring ASWC for the previous month\).
* **Formula**: ASWC = Production Environment Costs/Paid Workspaces

### Development Metric

* **Description**: The fraction which compares the amount we spend on environments related to our features testing with the total Cloud infrastructure costs.
* **Formula**: DM = \(Test Environment Costs + Dev Environment Costs\)/Total AWS Cloud Costs

### Customers Platform Balance Metric

* **Description**: The fraction which compares the variable costs we have because we run the Cloud product with the costs that are directly correlated with customers' usage \(both paid and freemium\).
* **Formula**: CPBM = Customer Specific Costs/Variable Platform Costs

## Secondary KPIs

### Workspaces Balance Metric

* **Description**: The fraction which compares the paid workspaces with the total number of workspaces within a given month of the Cloud Infrastructure service.
* **Formula**: WB = Paid Workspaces/Total Workspaces

### Secondary Average Production Workspace Cost

* **Description**: The fraction which compares the amount of Production Environment and Core Environment costs with the number of workspaces within a given month of the Cloud Infrastructure service.
* **Formula**: SAPWC = \(Production Environment Costs + Core Environment Costs\)/Workspaces

### Secondary Average Subscription Workspace Cost

* **Description**: The fraction which compares the amount of Production Environment and Core Environment costs with the number of workspaces that have 11 or more users within a given month of the Cloud Infrastructure service.
* **Formula**: SASWC = \(Production Environment Costs + Core Environment Costs\)/Paid Workspaces

### Active Average Production Workspace Cost

* **Description**: The fraction which compares the amount of Production Environment costs with the number of active workspaces within a given month of the Cloud Infrastructure service.
* **Formula**: AAPWC = Production Environment Costs/Active Workspaces

### Secondary Active Average Subscription Workspace Cost

* **Description**: The fraction which compares the amount of Production Environment and Core Environment costs with the number of active workspaces within a given month of the Cloud Infrastructure service.
* **Formula**: SAASWC = \(Production Environment Costs + Core Environment Costs\)/Active Workspaces

### Average Total Production Freemium Cost

* **Description**: Roughly how much free workspaces cost us. The fraction which compares the amount of Production Environment costs with the number of all free workspaces \(active and inactive\).
* **Formula**: ATPFC = Production Environment Costs/Freemium Workspaces \(Active and Inactive\)

### Non Production Environment Cost
* **Description**: The fraction which compares the amount we spend on all non production environments. 
* **Formula**: NPEC = \(Test Environment Costs + Dev Environment Costs + Core Environment Costs + Staging Environment Costs\)/Total AWS Cloud Costs

### Active Hibernated Workspaces Ratio
* **Description**: The ratio between Active to Hibernated workspaces at any given month
* **Formula**: AHR = Active Workpaces/Hibernated Workspaces

**Note:** Until February 2021 we measured all workspaces as active. Hibernation functionality was introduced in the last three days of February 2021.

