# Deployment Engineering: MME Sev 1 Outage Status Update Template

Below is a template for sharing status updates for MME Sev 1 Outages:

```
### <customer> SEV1 outage - <time> update

#### Status: <status>

#### Incident Time: <number of hours since incident began>

<summary of incident>

#### Customer Impact

<summary of customer impact>

#### Technical Notes

<summary of technical notes>
```

## Sample status update

### Enterprise ABC SEV1 outage - 7:20pmET update

#### Status: Identified

#### Incident time: 9 hours

We've identified the likely root cause. PR is in progress, with the goal to merge tonight, followed by a 7.8.6 dot release for ABC by tomorrow morning.

WebEx bridge with ABC has concluded. We will reconvene at 8am ET.

Huge thanks to @neill.collie for being on the bridge call for 9 hours. Additionally big thank you's go to Ben Cooke for identifying the root cause, plus Doug, Joram, Agniva, Chris Speller, Claudio, Ben Schumacher who all pitched in thus far, and Amy + Delivery team for being on standby for a patch release.

Next update will be shared at 8amET.

#### Customer impact

While the outage is ongoing, mood with ABC team felt much lighter after the root cause was identified. The call ended in a good note.

ABC is preparing comms for an emergency upgrade patch. Last time in September approvals were bypassed with Alice Evan's signoff (SVP - Senior Technical Manager at ABC). Alice was on call and was ready to sign off on the approvals.

#### Technical notes

The cause appears to be a recent change that results in a long-running bot query hitting the database directly more often instead of a cache. Delivery team has been notified for a patch release in v7.8.6, which ABC would first test in dev/uat, then roll to prod if it's deemed to solve the root cause.

On the API call to get the config for the  client, we're adding back a cache around a query to count the total users. This API is called on every page load. The query was used in this case to determine if there are any existing users on the system, which is needed for some client logic. The cache was originally removed due to a bug that mis-reported the existence of users. We're adding it back in a different way that fixes the bug and reduces the query to happen only once. 

PR is in progress, with the aim to merge the change tonight, followed by a 7.8.6 dot release.

The dot release will be shared by Neill over intralink, which ABC will push to dev/uat. ABC will smoke test, plus check the Grafana query `sum(rate(mattermost_db_store_time_count{instance=~"$server",method="UserStore.Count"}[5m]))` to see if there's a noticeable difference.

Afterwards, the patch will be pushed to prod.

Latest thread with full details: https://community.mattermost.com/private-core/pl/fp1ptysz5tbz5bogre8fzbr7za
