---
description: 'Owner: Alex Dovenmuehle'
---

# Data Engineering

Business Operations, Data Engineering, and Analytics functions were started in December and are ever evolving. Because of how new we are, eveything on this page is currently WIP.

We are currently focused on:
* Data collection
* Mapping data to business logic
* Data modeling
* Looker (data visualization tool replacing Chartio)
* Automating Metrics

## Data Engineering Infrastructure

### GitHub
* Link: https://github.com/mattermost/mattermost-data-warehouse
  * To access the repository, you must be a member of the Core Developers team

### Amazon EKS
* https://aws.amazon.com/eks/
* EKS is a managed Kubernetes service that allows us to deploy, orchestrate, and run our code. The main benefits of Kubernetes are being able to declaratively specify the resources you need and how much CPU and memory they require, and Kubernetes will figure out how to make it work. It will also attempt to restart VMs that have failed. We make use of Dockerfiles for our images. We also use Bitnami’s Airflow helm chart.
* To keep our data and configuration confidential, we make use of Kubernetes Secrets which are only shared with team members who need access in LastPass.

### Airflow
* To access Airlow, you must be on VPN go to this link. The Airflow Creds are stored in the Shared-BizOps LastPass Folder.
* Apache Airflow is a workflow orchestration tool built in Python that allows you to build and schedule DAGs. With these DAGs we can schedule jobs to run using crontab style scheduling and also declare dependencies between jobs so that we can ensure that data that we’re processing doesn’t get overwritten. Airflow also has great utilities for retrying failed jobs and alerting for job and DAG failures.
* We take advantage of Mattermost Incoming Webhooks to send DAG failures to a special internal Mattermost channel called BizOps Ops where team members can triage the failure. We ensure that these get sent to Mattermost with our failed task callback which is specified in each DAGs configuration
* We also utilize Bitnami’s Get DAG files from a git repository so that it will automatically pull from the master branch of https://github.com/mattermost/mattermost-data-warehouse every 60 seconds so our DAGs are always up to date.
* We use Airflow’s new KubernetesPodOperator that allows each of our jobs to run in it’s own Kubernetes Pod. The real flexibility with this is that because it’s simply a Kubernetes Pod running a process, we can actually run any job in any language. It also isolates the compute and memory for all the jobs, and we can even customize how much compute and memory power we give to each job so if a job requires more power we can grant it that.
* This is a screenshot of our actual Airflow installation and gives an example of how the UI looks.

### Kubernetes Secrets
* To keep our connection strings and other configuration items confidential, we utilize Kubernetes Secrets and inject those as environment variables into our Kubernetes Pods. To inject a secret into the environment of a job run through an Airflow DAG, you must specify it in the kube_secrets.py then you can import it in the DAG file and then finally injecting into the Operator object itself

### Snowflake
* Snowflake is a cloud- and SQL- based data warehouse platform that allows you to separate query compute power from data storage. It uses a proprietary data format for storing data and strives to provide a service that means you don’t need a DBA to constantly monitor and tweak to keep the warehouse performant.

#### Virtual Warehouse
* Virtual Warehouses are Snowflake’s concept for a cluster of compute resources that can execute queries. You are billed based on how the size of the Virtual Warehouse and how long it is running for.
### Stage and COPY
* Stages in Snowflake allow you to specify an external data source that you want to load data from. Once specified, you can run a simple “COPY INTO” command with a pattern, and in our case, will allow us to import data from S3 buckets. You can see how we utilize this in https://github.com/mattermost/mattermost-data-warehouse/blob/master/extract/s3_extract/stage_import.py

### dbt (Data Build Tool)
* Dbt is a tool, written in Python, that allows you to execute the Transform step of your ELT or ETL process. https://docs.getdbt.com/docs/introduction
* We use it to transform raw data in our Snowflake warehouse into more easily usable tables and views.
* Our dbt implementation is at https://github.com/mattermost/mattermost-data-warehouse/tree/master/transform/snowflake-dbt
* We are still building out our transformations, but a good example to look at is https://github.com/mattermost/mattermost-data-warehouse/tree/master/transform/snowflake-dbt/models/finance where we take raw data from our Salesforce instance, and use it to calculate Annual Run Rate of our customers.

* Dbt has a concept of sources and models. 
  *An example sources file is at https://github.com/mattermost/mattermost-data-warehouse/blob/master/transform/snowflake-dbt/models/orgm/sources.yml and this specifies already existing raw data that dbt can pull from to build models.
Then, you can define models that reference the sources. https://github.com/mattermost/mattermost-data-warehouse/blob/master/transform/snowflake-dbt/models/finance/account_daily_arr.sql for example. The filename of the model file determines the object name in the database (in this case a table). 

### Meltano Permissions
* Meltano is an overall framework that includes a lot more than what we’re using it for.
We’re actually just using a small piece that allows us to control our Snowflake user and role permissions in a fine-grained way.
* The specific piece we use is at https://meltano.com/docs/command-line-interface.html#permissions
* We use this in the snowflake_permissions DAG. The interesting piece is the container_cmd lines. Essentially we create an entire Meltano project, but then just use a roles.yml file that we define to control the permissions.

## Data Sources

### Telemetry
* Telemetry data is data that is sent from Mattermost servers and makes its way to our data warehouse. This data is detailed at https://docs.mattermost.com/administration/telemetry.html
* Currently, we use Segment to push this data to Snowflake. The data is available in its raw form in the Raw database, in the mattermost2 and mattermost_nps schemas.
* We currently have a dbt model at https://github.com/mattermost/mattermost-data-warehouse/blob/master/transform/snowflake-dbt/models/mattermost/server_daily_details.sql that uses this raw data, but will continue to add more.
* Active User Counts
  * Mattermost servers ping a Cloudfront endpoint with some basic telemetry. It uses the log format specified here. The import job uses code here

### Push Notifications
* Mattermost runs a proxy service that allows notifications to be sent through Apple and Google’s respective notification services for mobile notifications. The log data is put into an S3 bucket and then ingested using the aforementioned Snowflake Stage and COPY. See here for more details

### Server Release
* To help us track how many Mattermost servers are being deployed, there is a pingback which gets logged to an S3 bucket that we import. Details here
### License Data
* Mattermost’s enterprise license metadata is exported nightly to an S3 bucket and then we import it daily. Code here

### Stitch Data
* Google Analytics
  * Overview
    * Google Analytics - Stitch Integration has a lot of caveats and limitations.
    * Known Limitations:
      * Each set of dimensions and measures from Google Analytics needs to have it’s own Stitch integration.
      * Each integration creates a schema in Snowflake that matches the name of the integration and adds a table called report
`Name: GA ChannelGrouping Source Users Org
Schema: analytics.ga_channelgrouping_source_users_org
Table: analytics.ga_channelgrouping_source_users_org.report`
      * Once an integration is created, it cannot be edited. If you need to make changes, you need to delete the integration and start over.
      * Data is only pulled at a daily level
      * This is an issue because “Unique Monthly Users” is not the same as “Aggregated Unique Daily Users”
  * Mattermost.org
    * Google Analytics Link
    * Owner: Jason Blais
    * Stitch Integrations:
      * GA ChannelGrouping Source Users Org
        * Frequency: 6 hours
        * Dimensions: ChannelGrouping, Source
        * Measures: Users
  * Mattermost.com
    * Google Analytics Link
    * Owner: Kendall Reicherter
    * Stitch Integrations:
      * GA ChannelGrouping Source Users Com
        * Frequency: 6 hours
        * Dimensions: ChannelGrouping, Source
        * Measures: Users
  * Salesforce / Heroku Connect
    * OrgM
    * Frequency: 1 hour (as of 2020-01-07)
    * Tables Syncing
    * Sync Type:  Key-Based Incremental Replication (Recommended)
      * When you define a Replication Key, Stitch will store the greatest value of that column of that key during each update and only sync rows with greater or equal values on subsequent updates.
      * Note: Hard deletes are not supported by this Replication Method.
      * Note: Because we use this incremental replications, when adding a new column to a table, you must reload the table to ensure all data has been backfilled in Snowflake.
    * Replication Key: sysmodstamp
    * Table Specific Info
`app.stitchdata.com/client/153136/pipeline/connections/206623/data/db/d6ghpflham816n/schema/orgm/properties/6715619/[TABLE_NAME]/`
Account Example: `app.stitchdata.com/client/153136/pipeline/connections/206623/data/db/d6ghpflham816n/schema/orgm/properties/6715619/account/`
    * Updating Table Settings:
      * Follow the link formatting to table specific info
      * Click Table Settings

    * Reloading a Table:
      * In Table Settings, click Reset Table and save updates

### Postgres Job
* The Postgres Job is simply a way for us to run scripts against our Heroku Postgres database (that contains our Salesforce data through Heroku Connect). 
* The DAG for this is here
  * The script looks for sql files in the https://github.com/mattermost/mattermost-data-warehouse/tree/master/transform/sql folder and the second argument to “get_container_operator” must match the filename in the folder (without the .sql)
It uses a Kubernetes Secret to store the credentials for our Postgres database.
  * Note: The first argument to “get_container_operator” must not have any underscores in the name, hyphens can be used in their place.

### Granting Access / Permissions
#### Snowflake
* Admin creates a user based on level of access
  * Admin:
`CREATE USER rachel
       PASSWORD='[generate using lastpass]'
       COMMENT='rachel@mattermost.com'
       DEFAULT_ROLE='sysadmin'
       DEFAULT_WAREHOUSE='analyst_xs';`

  * Read Only:
`CREATE USER rachel
       PASSWORD='[generate using lastpass]'
       COMMENT='rachel@mattermost.com'
       DEFAULT_ROLE='reporting'
       DEFAULT_WAREHOUSE='analyst_xs';`
#### Postgres
* Admin adds user to Heroku Account
#### Stitch
* Admin adds user to Stitch Account
#### Airflow
* Admin shares login information with user via LastPass
  * Airflow Creds in Shared-BizOps Folder
