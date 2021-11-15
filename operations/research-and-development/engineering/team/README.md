# Sustained Engineering

The Sustained Engineering Team \(SET\) is responsible for improving and maintaining quality of the Mattermost products, as well as helping support with any issues they require engineering support with. Often, people in SET primarily play the role of first responders, then handing off to whichever engineering team best equipped to resolve an issue.

## Team Members
SET is a rotating team that is comprised of engineers from the different engineering teams. The rotation is on a weekly cycle for engineers, and two-week cycle for leads.

Who is currently on SET can be seen in the header of the [~Sustained Engineering](https://community.mattermost.com/core/channels/sustained-engineering) channel.

Engineering teams will commit a total of 4 engineers (two primaries for two time zones, two backups for two timezones) plus a lead to SET for each rotation. While on SET, that engineer should attend their feature team's sprint planning, but it should be taken into account that any urgent SET-related issue may take them out of the regular day-to-day planned work. How this is managed is up to the SET team member's engineering lead, some let them work on regular sprint work and accept the interruptions, others let them focus on fixing bugs to reduce the cost of context switching.

## Roles

The **SET Lead** is usually one of the engineering team's Engineering Leads. The SET lead, leads the SET team during its rotation. In practice this means the SET lead:

1. Ensures that raised issues are being addressed.
2. Communicates the status of ongoing issues appropriately to stakeholders.
3. Is a point of escalation in case stakeholders do not know who else to escalate to.

The SET Lead is also on call \(via OpsGenie\), and is escalated to whenever neither the SET primary nor SET backup acknowledge an issue in the appropriate time.

We use a Mattermost Playbook to run the SET cycle. For this, the SET Lead creates a new run of the [SET Cycle](https://community-daily.mattermost.com/playbooks/playbooks/w36ro78cgj8qtjq5mf6say7bxe/preview) playbook and follows the steps as codified by the playbook. **Note:** Running this playbooks requires the SET Lead to have priviledges to create public channels on the "Contributors" team at community, if you do not have this, request it in the [Community Configuration](https://community-daily.mattermost.com/core/channels/community-configuration) channel.

The **SET Primary** is usually an engineer from one of the engineering teams. The SET Primary is the first person to respond to any issues escalated. Escalation primarilly happens through the "Sustained Engineering" channel or OpsGenie in cases of time urgency.

The **SET Backup** is usually an engineer from one of the engineering teams. In the case that the SET Primary is not available or unresponsive, the SET backup temporarily takes over. In certain situations it may also be required for the primary to ask for help to the backup.

## Workflow

Work for SET comes from various sources:

1. The SET [Kanban JIRA board](https://mattermost.atlassian.net/secure/RapidBoard.jspa?rapidView=33). Tickets in the TO DO column should be organized from highest priority to lowest priority, based on the [Priority of Work](./#priority-of-work) section. The SET lead should make sure that the tickets are priority ordered but team members can move tickets around to meet the correct priorities as necessary. If tickets get stuck in a certain state, it's also the SET responsibility to push them to completion, either by nudging people or taking them over.
2. OpsGenie: Support has an e-mail address they will send urgent escalations to. These result in pages in OpsDuty, first sent to the SET Primary, then to SET Back-up and ultimately to the SET Lead when not timely acknowledged.
3. The [~Sustained Engineering](https://community-daily.mattermost.com/core/channels/sustained-engineering) channel. Support may use this channel to ask questions or raise urgent issues.
4. The [~Ask R&D](https://community-daily.mattermost.com/core/channels/ask-r-and-d) channel. This is the place where support and community can ask any type of R&D related questions.

When a new issue is raised, it is the SET primary's duty to:

1. Understand the customer impact and priority of the issue (if required with the help of the SET lead, or relevant product managers). If the issue is really a feature request or low-urgency bug, a JIRA ticket is filed and assigned to the appropriate team. In that case, the SET responsibilities end here. In case of higher-impact issues, the steps continue:
2. Investigate to understand the source of the issue.
3. Prepare a "hand-off package" including (where relevant): logs, Grafana snapshots, and above all a clear description of what the issue is ready to be acted on by the responsible team.
4. Hand-off the issue to the team who owns the problematic part of the product. Of course, if the issue is in the scope of expertise of the SET engineers, they handle the issue themselves.

## Priority of Work

Below is how SET prioritizes what is worked on.

1. Quality issues affecting community.mattermost.com or community-daily.mattermost.com
   * When a high impact issue affects the community server, SET responds and is responsible to coordinate fixing.
   * The primary goal is to restore stability, whether this is achieved by fixing the issue or reverting code.
2. Handles customer support escalation
   * The primary goal is to help with issues that require code changes or in-depth knowledge of the code internals.
   * Be helpful with training/knowledge sharing for the support team.
   * Identify customer support requests that are features and route to PM as necessary.
3. General bug fixes
   * Pick up any bugs in triage without an obvious owning feature team.
   * Work on bugs in this order: hotfix, release, customer reported, other.
4. [~Ask R&D](https://community-daily.mattermost.com/core/channels/ask-r-and-d) channel — this channel should be monitored, but checking it once or twice per day is sufficient.
