# Deployment Engineering: Playbook for MME Sev 1 Outages

Below is a codified playbook used to respond to MME Sev 1 Outages.

Some aspects of this playbook is a work in progress, marked with "XXX". 

## 1 - Escalation

[ ] Create Incident Channel, run MME Sev1 Playbook

 - _Once MME Sev1 issue is escalated by CSM, TAM or CRE, create incident channel, and run MME Sev 1 Playbook_

[ ] Add CSM, TAM & DE to Incident Channel

 - _Add CSM, TAM & DE leaders (@Brent Fox @Stu Doherty @Jason Blais) to the channel to add the appropriate staff member. Also add @Ian Tien to view Playbooks in motion for L2 and L1 incidents._

[ ] Start audio & screen share with customer

 - _Include a Mattermost engineer & customer DBA on the call who can run queries to support troubleshooting_

[ ] Reply to customer (CEO if MME Sev 1 > 1 hour)

 - _MME Sev 1 outage >1 hour requires CEO looped into customer_

## 2 - Data Gathering

[ ] Share system information

 - _Includes relevant system configuration setting, database specs (with CPU, RAM) & application specs (with CPU, RAM)_

[ ] Share Grafana screenshots

 - _Include DB calls, API latency, Store latency, Top HTTP requests, Top API requests, CPU utilization, memory utilization_

[ ] Share output from support bundle

 - _Link to relevant docs_

[ ] Share output from slow query logs

 - _Link to relevant docs_

[ ] Pin data to channel

 - _Link to relevant docs_

## 3 - Data Review

[ ] Review system configuration settings that may impact performance

 - _Includes user typing timeout, user typing message, max notifications per channel & db replica lag settings_

[ ] Review Grafana screenshots to identify potential issues

 - _Includes XXX_

[ ] Review support bundle output to identify potential issues

 - _Includes XXX_

[ ] Review slow query log output to identify potential issues

 - _Includes XXX_

[ ] Summary findings from data review

 - _Includes XXX_

[ ] Reply to customer with update (CEO if MME Sev 1 > 1 hour)

 - _MME Sev 1 outage >1 hour requires CEO looped into customer. Include a timeline for anticipated resolution._

## 4 - Code Investigation

[ ] Based on findings from data review, identify areas of codebase with potential root cause

 - _Includes XXX_

[ ] Identify potential root cause based on the code

 - _Includes XXX_

[ ] Identify solution for root cause

 - _Includes XXX_

[ ] Submit PR for solution

 - _Includes XXX_

[ ] Deem whether verification of a fix is required for release candidate

 - _If yes, provide clear step-by-step instructions for QA to verify the fix, including specifications for test server such as database type (MySQL vs Postgres)_

[ ] Reply to customer with update (CEO if MME Sev 1 > 1 hour)

 - _MME Sev 1 outage >1 hour requires CEO looped into customer. Include a timeline for anticipated resolution._

## 5 - Release Preparation

[ ] Merge PR to master branch

 - _Includes XXX_

[ ] Cherry pick PR to dot release branch

 - _Includes XXX_

[ ] Cut dot release candidate

 - _Includes XXX_

[ ] Verify fix in dot release candidate

 - _Includes XXX_

[ ] Cut dot release

 - _Includes XXX_

[ ] Reply to customer with update (CEO if MME Sev 1 > 1 hour)

 - _MME Sev 1 outage >1 hour requires CEO looped into customer. Include a timeline for anticipated resolution._

## 6 - Dot release deployment

[ ] Send dot release binary to customer

 - _Includes XXX_

[ ] Upgrade customer’s dev/staging environment with dot release

 - _Includes XXX_

[ ] Verify fix in customer’s dev/staging environment 

 - _Includes XXX_

[ ] Upgrade customer’s production environment with dot release

 - _Includes XXX_

[ ] Verify fix in customer’s production environment 

 - _Includes XXX_

[ ] Reply to customer with update (CEO if MME Sev 1 > 1 hour)

 - _MME Sev 1 outage >1 hour requires CEO looped into customer. Include a timeline for anticipated resolution._

## 7 - Resolution

[ ] Monitor fix in customer environment for 24 hours

 - _Includes XXX_

[ ] Receive confirmation from customer about issue resolution

 - _Includes XXX_

[ ] Reply to customer with update (CEO if MME Sev 1 > 1 hour)

 - _MME Sev 1 outage >1 hour requires CEO looped into customer_

## 8 - Retrospective

[ ] Complete incident retrospective within 1 business day from resolution

 - _Includes XXX_

[ ] Draft incident summary analysis within 2 business days from resolution

 - _Includes XXX_

[ ] Send completed incident summary analysis with customer within 3 business days

 - _Includes XXX_

[ ] Reply to customer with update (CEO if MME Sev 1 > 1 hour)

 - _MME Sev 1 outage >1 hour requires CEO looped into customer_

