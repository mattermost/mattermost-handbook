# Sustained Engineering

The Sustained Engineering Team \(SET\) is responsible for improving and maintaining quality of  Mattermost products, as well as helping support with any issues they require engineering support with. Often, people in SET primarily play the role of first responders, then handing off to whichever engineering team best equipped to resolve an issue.

## Team members

SET is a rotating team that is comprised of engineers from the different engineering teams. The rotation is on a two-week cycle. For engineers one of those weeks is as back-up, another is as primary.

Who is currently on SET can be seen in the header of the [~Sustained Engineering](https://community.mattermost.com/core/channels/sustained-engineering) channel.

Engineering teams will commit a total of 4 engineers (a primary and a backup for each of the two shifts) plus a lead to SET for each rotation. While on SET, an engineer still attends their team's meetings, but it should be taken into account that any SET-related issue may take them out of the regular day-to-day planned work. How this is managed is up to the engineering lead from the engineer's team, e.g.: some work on regular sprint work and accept the interruptions, others focus on fixing bugs to reduce the cost of context switching.

## Roles

The **SET Lead** is one of the engineering team's Engineering Leads. The SET lead, leads the SET team during its rotation. In practice this means the SET Lead:

1. Ensures that raised issues are being addressed.
2. Communicates the status of ongoing issues appropriately to stakeholders.
3. Is a point of escalation in case stakeholders do not know who else to escalate to.

The SET Lead is also on call (via OpsGenie), and is escalated to whenever neither the SET primary nor SET backup acknowledge an issue in the appropriate time.

The **SET Primary** is an engineer from one of the engineering teams. The SET Primary is the first person to respond to any issues escalated. Escalation primarily happens through the [~Sustained Engineering](https://community.mattermost.com/core/channels/sustained-engineering) channel or OpsGenie in cases of time urgency (refer to [Sources of escalations](#Sources-of-escalations) section for more details).

The **SET Backup** is an engineer from one of the engineering teams. In the case that the SET Primary is not available or unresponsive, the SET backup temporarily takes over. In certain situations it may also be required for the primary to ask for help to the backup.

## Priority of work

Below is how SET prioritizes what is worked on.

1. Quality issues affecting community.mattermost.com or community-daily.mattermost.com
   * When a high impact issue affects the community server, SET responds and is responsible to coordinate fixing.
   * The primary goal is to restore stability, whether this is achieved by fixing the issue or reverting code.
2. Handles customer support escalation
   * The primary goal is to help with issues that require code changes or in-depth knowledge of the code internals.
   * Be helpful with training/knowledge sharing for the support team.
   * Identify customer support requests that are features and route to PM as necessary.
3. General bug fixes
   * Pick up any bugs in triage.
   * Work on bugs in this order: hotfix, release, customer reported, other.
4. [~Ask R&D](https://community.mattermost.com/core/channels/ask-r-and-d) channel — this channel should be monitored, but checking it once or twice per day is sufficient.

## Sources of escalations

Work for SET comes from various sources:

1. OpsGenie: Support has an e-mail address they will send urgent escalations to. These result in pages in OpsGenie, first sent to the SET Primary, then to SET Back-up and ultimately to the SET Lead when not timely acknowledged. **Note:** using this channel of escalation is exceedingly rare, and only happens in extremely time sensitive cases.
2. The [~Sustained Engineering](https://community.mattermost.com/core/channels/sustained-engineering) channel. Support may use this channel to ask questions or raise urgent issues.
3. The SET [Kanban Jira board](https://mattermost.atlassian.net/secure/RapidBoard.jspa?rapidView=33). Tickets in the TO DO column should be organized from highest priority to lowest priority, based on the [Priority of Work](./#priority-of-work) section. The SET lead should make sure that the tickets are priority ordered but team members can move tickets around to meet the correct priorities as necessary. If tickets get stuck in a certain state, it's also the SET responsibility to push them to completion, either by nudging people or taking them over.
4. The [~Ask R&D](https://community.mattermost.com/core/channels/ask-r-and-d) channel. This is the place where support and community can ask any type of R&D related questions.

## SET weekly cycle

We use a Mattermost playbook to run the SET cycle. For this, the SET Lead creates a new run of the [SET Cycle](https://community.mattermost.com/playbooks/playbooks/w36ro78cgj8qtjq5mf6say7bxe/preview) playbook and follows the steps as codified by the playbook. Overall a SET cycles consists of three phases:

1. Start: Review all ongoing issues and make sure they have appropriate owners in the current SET team.
2. Monitor: Monitor the sources of SET escalations (previous section) and act accordingly (see next section).
3. Hand-over: By Friday end of day, the SET leads ensures that the next week's SET team (especially the SET Lead) is aware of ongoing issues and have sufficient context to continue the work. Specifically:
   * Ensure that the incoming SET team is in the right incident channels (if anybody).
   * SET Jira tickets find new assignees in the incoming SET team.
   * Any additional knowledge (beside what's in the Jira tickets and channels) that the incoming SET team will need to continue the work is transferred.

## Workflow

Support may ask questions in the [~Sustained Engineering](https://community-daily.mattermost.com/core/channels/sustained-engineering) channel. If these can be answered without significant time investment (up to about an hour), just answer them. If they require deeper analysis, investigation, or potential hand-off to other people or teams, follow the following steps:

1. **Create a Jira ticket** for the issue, initially connected to the "Sustained Engineering" team, and assigned to the SET Primary and moved to _In Progress_. Ensure the ticket describes the problem clearly and is as specific as possible. For example, if Mattermost is slow specify what is slow: the server, the client, a particular request.
2. **Understand the customer impact and priority of the issue together with support.** Determine the priority of the issue following [the levels specified here](https://support.mattermost.com/hc/en-us/articles/4413076086548-Mattermost-Support-service-levels-and-their-severity), clearly mark this priority in the ticket. If the issue is really a feature request or low-urgency bug, change the ticket type and reassign it to the appropriate team. In that case, the SET responsibilities end. 
4. If the issue is of **L1 (critical) or L2 (major)** support [will have a run of the Mattermost Support Incident](https://community.mattermost.com/playbooks/playbooks/bx9xnkb8upribm3wsbye1cdwtw) playbook running that SET will be invited to. Make sure that updates (using the Playbooks "Post update" feature) are posted **at least daily**.
3. **Investigate the source of the issue,** update the Jira ticket accordingly. Ensure the following things are clearly listed in the ticket (where appropriate):
   * Mattermost version
   * Database type and version
   * Configuration used
   * Relevant logs
   * A CPU profile (in case of high-CPU usage issue)
   * A heap profile (in case of memory use)
   * Stack trace (in case  a service gets stuck)
4. Hand-over (optional): once the issue is sufficiently narrowed down _and_ there is a more appropriate owner than SET, hand the issue over as follows:
   * If a _Mattermost Support Incident_ playbook was run, invite the new owning team to the incident channel.
   * Reassign the Jira ticket to the new owning team.

**Important:** Even if an issue has been handed over, it remains SET responsibility to ensure good communication between engineering and other stakeholders.
