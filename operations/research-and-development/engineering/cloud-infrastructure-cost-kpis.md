# Cloud Infrastructure Cost KPIs

The Cloud SRE team uses certain KPIs to monitor cloud infrastructure costs from the engineering standpoint. These KPIs are used to help the business and the Cloud SRE team to set goals for cost optimization.

As of July 2021, the goals for the SRE team are to:

 - Decrease the Average Cost Per Workspace (APWC)
 - Keep development and test environments costs (DM) below 20% of total costs
 - Increase the WB fraction (ratio of paid workspaces relative to total workspaces)

Below are the primary and seconday KPIs used to measure each:

## Primary KPIs

### Average Production Workspace Cost

 - **Description**: The fraction which compares the amount of Production Environment costs with the number of workspaces which at a given month of the Cloud Infrastructure service. Production Environment will be defined as the environment where we host all our customers, including paid and free workspaces.
 - **Formula**: APWC = Production Environment Costs/Number of Workspaces  

### Average Production Freemium Cost

 - **Description**: Roughly is how much free workspaces cost to us. The fraction which compares the amount of Production Environment costs with the number of active free workspaces.
 - **Formula**: APFC = Production Environment Costs/Freemium Active Workspaces
Note: Until February 2021 we measure all workspaces as active since we introduced hibernation functionality the last 3 days of February

### Average Subscription Workspace Cost

 - **Description**: The fraction which compares the amount of Production Environment costs with the number of workspaces that have 11 or more users which at a given month the Cloud Infrastructure service. A paid workspace is defined as successful receipt of payment for the time period (e.g. payment for the previous month completed, when measuring ASWC for the previous month).
 - **Formula**: ASWC = Production Environment Costs/ Paid Workspaces

### Development Metric

 - **Description**: The fraction which compares the amount we spend on environments related to our features testing with the total cloud infrastructure costs.
 - **Formula**: DM = (Test Environment Costs + Dev Environment Costs)/Total AWS Cloud Costs

### Customers Platform Balance Metric

 - **Description**: The fraction which compares the variable costs we have because we run the cloud Product with the costs that are directly correlated with customers usage (both paid and freemium)
 - **Formula**: CPBM = Customer Specific Costs/Variable Platform Costs

## Secondary KPIs

### Workspaces Balance Metric

 - **Description**: The fraction which compares the paid workspaces  with the total  number of workspaces which at a given month the Cloud Infrastructure service.
 - **Formula**: WB = Paid Workspaces/Total Workspaces

### Secondary Average Production Workspace Cost 

 - **Description**: The fraction which compares the amount of Production Environment and Core Environment costs with the number of workspaces which at a given month of the Cloud Infrastructure service.
 - **Formula**: SAPWC  = (Production Environment Costs +Core Environment Costs)/Workspaces

### Secondary Average Subscription Workspace Cost

 - **Description**: The fraction which compares the amount of Production Environment and Core Environment costs with the number of workspaces that have 11 or more users which at a given month the Cloud Infrastructure service.
 - **Formula**: SASWC = (Production Environment Costs + Core Environment Costs)/Paid Workspaces

### Active Average Production Workspace Cost 

 - **Description**: The fraction which compares the amount of Production Environment costs with the number of active workspaces which at a given month of the Cloud Infrastructure service.
 - **Formula**: AAPWC = Production Environment Costs/Active Workspaces

### Secondary Active Average Subscription Workspace Cost 

 - **Description**: The fraction which compares the amount of Production Environment and Core Environment costs with the number of active workspaces which at a given month the Cloud Infrastructure service.
 - **Formula**: SAASWC = (Production Environment Costs + Core Environment Costs)/Active Workspaces

### Average Total Production Freemium Cost

 - **Description**: Roughly is how much free workspaces cost to us. The fraction which compares the amount of Production Environment costs with the number of all free workspaces. (active and inactive)
 - **Formula**: ATPFC = Production Environment Costs/Freemium Workspaces (Active and Inactive)

Note: Until February 2021 we measure all workspaces as active since we introduced hibernation functionality the last 3 days of February.



