# Data Engineering

## Data Engineering Infrastructure

![](../../../.gitbook/assets/data-diagram.png)

### GitHub

* Link: [Mattermost Data Warehouse](https://github.com/mattermost/mattermost-data-warehouse)
  * To access the repository, you must be a member of the Core Developers team.

### Amazon EKS

* [https://aws.amazon.com/eks/](https://aws.amazon.com/eks/)
* EKS is a managed Kubernetes service that allows us to deploy, orchestrate, and run our code. The main benefit of Kubernetes is being able to declaratively specify the resources you need and how much CPU and memory they require, and Kubernetes will figure out how to make it work. It will also attempt to restart VMs that have failed. We make use of [Dockerfiles](https://hub.docker.com/repository/docker/adovenmm/data-warehouse-psql/general) for our images. We also use [Bitnami’s Airflow helm chart](https://github.com/bitnami/charts/tree/master/bitnami/airflow).
* To keep our data and configuration confidential, we make use of [Kubernetes Secrets](https://kubernetes.io/docs/concepts/configuration/secret/) which are only shared with team members who need access in LastPass.

### Airflow

* To access Airflow, you must be on VPN go to this [link](http://airflow.internal.mattermost.com). The Airflow Creds are stored in the Shared-BizOps LastPass folder.
* [Apache Airflow](https://airflow.apache.org/) is a workflow orchestration tool built in Python that allows you to build and schedule [DAGs](https://airflow.apache.org/docs/stable/concepts.html#dags). With these DAGs we can schedule jobs to run using [crontab style scheduling](https://crontab.guru/) and also declare dependencies between jobs so that we can ensure that data that we’re processing doesn’t get overwritten. Airflow also has great utilities for retrying failed jobs and alerting for job and DAG failures.
* We take advantage of [Mattermost incoming webhooks](https://docs.mattermost.com/developer/webhooks-incoming.html) to send DAG failures to a special internal Mattermost channel called BizOps where team members can triage the failure. We ensure that these get sent to Mattermost with our [failed task callback](https://github.com/mattermost/mattermost-data-warehouse/blob/master/dags/airflow_utils.py#L17) which is specified in each [DAGs configuration](https://github.com/mattermost/mattermost-data-warehouse/blob/master/dags/extract/diagnostics.py#L24).
* We also utilize [Bitnami’s Get DAG files from a git repository](https://github.com/bitnami/charts/tree/master/bitnami/airflow#option-3-get-your-dag-files-from-a-git-repository) to automatically pull from the master branch of our [GitHub repository](https://github.com/mattermost/mattermost-data-warehouse) every 60 seconds so our DAGs are always up to date.
* We use Airflow’s new [KubernetesPodOperator](https://airflow.apache.org/docs/stable/kubernetes.html) that allows each of our jobs to run in its own Kubernetes Pod. The real flexibility with this is that because it’s simply a Kubernetes Pod running a process, we can actually run any job in any language. It also isolates the compute and memory for all the jobs, and we can even customize how much compute and memory power we give to each job so if a job requires more power we can grant it that.
* This is a screenshot of our actual Airflow installation and gives an example of the UI.

![](../../../.gitbook/assets/airflow.png)

### Kubernetes Secrets

* To keep our connection strings and other configuration items confidential, we utilize [Kubernetes Secrets](https://kubernetes.io/docs/concepts/configuration/secret/) and inject those as environment variables into our Kubernetes Pods. To inject a secret into the environment of a job run through an Airflow DAG, you must specify it in the [kube\_secrets.py](https://github.com/mattermost/mattermost-data-warehouse/blob/master/dags/kube_secrets.py) then you can import it in the [DAG file](https://github.com/mattermost/mattermost-data-warehouse/blob/master/dags/extract/diagnostics.py#L8) and then finally inject it into the [Operator object](https://github.com/mattermost/mattermost-data-warehouse/blob/master/dags/extract/diagnostics.py#L49) itself.

### Snowflake

* [Snowflake](https://www.snowflake.com/) is a cloud- and SQL- based data warehouse platform that allows you to separate query compute power from data storage. It uses a proprietary data format for storing data and strives to provide a service that means you don’t need a DBA to constantly monitor and tweak to keep the warehouse performant.

#### Virtual warehouse

* [Virtual warehouses](https://docs.snowflake.net/manuals/user-guide/warehouses.html) are Snowflake’s concept for a cluster of compute resources that can execute queries. You are billed based on how the size of the Virtual Warehouse and how long it is running for.

**Stage and `COPY`**

* [Stages](https://docs.snowflake.net/manuals/sql-reference/sql/create-stage.html) in Snowflake allow you to specify an external data source that you want to load data from. Once specified, you can run a simple `COPY INTO` command with a pattern, and in our case, will allow us to import data from S3 buckets. You can see how we utilize this [here](https://github.com/mattermost/mattermost-data-warehouse/blob/master/extract/s3_extract/stage_import.py).

### dbt \(data build tool\)

* [dbt](https://docs.getdbt.com/docs/introduction) is a tool, written in Python, that allows you to execute the `transform` step of your ELT or ETL process. 
* We use it to transform raw data in our Snowflake warehouse into more easily usable tables and views.
* Our dbt implementation is [here](https://github.com/mattermost/mattermost-data-warehouse/tree/master/transform/snowflake-dbt).
* Dbt has a concept of [sources](https://docs.getdbt.com/docs/using-sources) and [models](https://docs.getdbt.com/docs/building-models).
  * An example sources file is [here](https://github.com/mattermost/mattermost-data-warehouse/blob/master/transform/snowflake-dbt/models/orgm/sources.yml) and this specifies already existing raw data that dbt can pull from to build models.
  * Then, you can define models that reference the sources.
  * Example:
    * [https://github.com/mattermost/mattermost-data-warehouse/blob/master/transform/snowflake-dbt/models/finance/\*\*account\_daily\_arr\*\*.sql](https://github.com/mattermost/mattermost-data-warehouse/blob/master/transform/snowflake-dbt/models/finance/**account_daily_arr**.sql).
    * The filename \(account\_daily\_arr\) of the model file determines the object name in the database \(in this case a table\).

### Meltano permissions

* [Meltano](https://meltano.com/) is an overall framework that includes a lot more than what we’re using it for.

  We’re actually just using a small piece that allows us to control our Snowflake user and role permissions in a fine-grained way.

* The specific piece we use is [here](https://meltano.com/docs/command-line-interface.html#permissions).
* We use this in the [snowflake\_permissions DAG](https://github.com/mattermost/mattermost-data-warehouse/blob/master/dags/general/snowflake_permissions.py#L32). The interesting piece is the container\_cmd lines. Essentially we create an entire Meltano project, but then just use a [roles.yml](https://github.com/mattermost/mattermost-data-warehouse/blob/master/load/snowflake/roles.yaml) file that we define to control the permissions.

## Data sources

### Telemetry

* Telemetry data is data that's sent from Mattermost servers and makes its way to our data warehouse.
  * This data is detailed [here](https://docs.mattermost.com/administration/telemetry.html).
* Currently, we use [Segment](https://segment.com/) to push this data to Snowflake.
  * The data is available in its raw form in the Raw database, in the mattermost2 and mattermost\_nps schemas.
* We currently have a dbt model [here](https://github.com/mattermost/mattermost-data-warehouse/blob/master/transform/snowflake-dbt/models/mattermost/server_daily_details.sql) that uses this raw data, but will continue to add more.
* Active User Counts
  * Mattermost servers ping a Cloudfront endpoint with some basic telemetry. It uses the log format specified [here](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/AccessLogs.html#LogFileFormat).
  * The import job uses code [here](https://github.com/mattermost/mattermost-data-warehouse/blob/master/extract/s3_extract/stage_import.py#L52).

### Push notifications

* Mattermost runs a proxy service that allows notifications to be sent through Apple and Google’s respective notification services for mobile notifications. The log data is put into an S3 bucket and then ingested using Snowflake Stage and `COPY`. See [here](https://github.com/mattermost/mattermost-data-warehouse/blob/master/extract/s3_extract/stage_import.py#L58) for more details.

### Server release

* To help us track how many Mattermost servers are being deployed, there's a pingback which gets logged to an S3 bucket that we import. Details [here](https://github.com/mattermost/mattermost-data-warehouse/blob/master/extract/s3_extract/stage_import.py#L46).

**License data**

* Mattermost’s enterprise license metadata is exported nightly to an S3 bucket and then we import it daily. Code [here](https://github.com/mattermost/mattermost-data-warehouse/blob/master/extract/s3_extract/stage_import.py#L42).

### Stitch data

* **Google Analytics**
  * Overview
    * Google Analytics - Stitch integration has a lot of caveats and limitations.
    * Known limitations:
      * Each set of dimensions and measures from Google Analytics needs to have its own Stitch integration.
      * Each integration creates a schema in Snowflake that matches the name of the integration and adds a table called `report`.
        * `Name: GA ChannelGrouping Source Users Org Schema: analytics.ga_channelgrouping_source_users_org Table: analytics.ga_channelgrouping_source_users_org.report`
      * Once an integration is created, it can't be edited. If you need to make changes, you need to delete the integration and start over.
      * Data is only pulled at a daily level.
        * This is an issue because `Unique Monthly Users` is not the same as `Aggregated Unique Daily Users`.
  * Mattermost.com
    * [Google Analytics Link](https://analytics.google.com/analytics/web/?authuser=0#/report-home/a120238482w177779216p176410444)
    * Owner: Kevin Fayle
    * Stitch integrations:
      * [GA Mattermost Com Pages Visits](https://app.stitchdata.com/client/153136/pipeline/connections/226666/summary)
        * Frequency: 6 hours
        * Dimensions: **Page Path**, **Page Title**
        * Measures: **Page Visits**, **Unique Page Visits**, **Avg Time on Page**
  * Developers.Mattermost.com
    * [Google Analytics Link](https://analytics.google.com/analytics/web/#/dashboard/uh0tcPOLS1ir9osCAZvBiQ/a64458817w179061281p177463446/)
    * Owner: Kevin Fayle
    * Stitch integrations:
      * [GA Developers Pages Visits](https://app.stitchdata.com/client/153136/pipeline/connections/226635/summary)
        * Frequency: 6 hours
        * Dimensions: **Page Path**, **Page Title**
        * Measures: **Page Visits**, **Unique Page Visits**, **Avg Time on Page**

