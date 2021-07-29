# The Sustained Engineering Team (SET)
The Sustained Engineering Team (SET) is responsible for improving and maintaining quality of the Mattermost products. Its role is ever evolving, but currently primarily focuses on:

1. Responding to customer incidents and questions escalated by support (either via OpsGenie or the [~Sustained Engineering](https://community.mattermost.com/core/channels/sustained-engineering) channel)
2. Responding to any incidents on company Mattermost environments like community and community-daily

Often, people in SET primarily play the role first responders, then handing off to whichever engineering team best equipped to resolve the issue. 

## Team Members
SET is a rotating team that is comprised of engineers from the different engineering teams. The rotation is on a weekly cycle for engineers, and two-week cycle for leads. Who is currently on SET can be seen in the header of the [~Sustained Engineering](https://community.mattermost.com/core/channels/sustained-engineering) channel.

Engineering teams will commit a total of 4 engineers plus a lead to SET for each rotation. While on SET, that engineer should attend their feature team's sprint planning, but it should be taken into account that any urgent SET-related issue may take them out of the regular day-to-day planned work. Plan appropriately.

## Roles
The **SET Lead** is usually one of the engineering team's Engineering Leads. The SET lead, leads the SET team during its rotation. In practice this means the SET lead:

1. Ensures that raised issues are being addressed
2. Communicates the status of ongoing issues appropriately to stake holders
3. Is a point of escalation in case stake holders do not else who else to escalate to

The SET Lead is also on call (via OpsGenie), and is escalated to whenever neither the SET primary nor SET backup acknowledge an issue in the appropriate time. 

The **SET Primary** is usually an engineer from one of the engineering teams. The SET Primary is the first person to respond to any issues escalated. There are two ways to respond to an issue:

1. Handle the issue themselves, e.g. by implementing a fix
2. Hand off the issue to the appropriate team or person

The **SET Backup** is usually an engineer from one of the engineering teams. In case thet SET Primary is not available or unresponsive, the back-up temporarily takes over. 


## Workflow Process

SET works in a continuous style using this [Kanban JIRA board](https://mattermost.atlassian.net/secure/RapidBoard.jspa?rapidView=33). Tickets in the TO DO column should be organized from highest priority to lowest priority, based on the [Priority of Work](#priority-of-work) section. The SET lead should make sure that the tickets are priority ordered but team members can move tickets around to meet the correct priorities as necessary.

Team members on SET should pull tickets off the top of TO DO queue, work on them to completion and then pull another one off the TO DO queue.

Discussion related to SET should occur in the [~Sustained Engineering](https://community.mattermost.com/core/channels/sustained-engineering) channel on https://community.mattermost.com.


## Triage

SET triages SET tickets asynchronously and also helps Release Manager to

* Help route new unassigned tickets to the appropriate engineering team
* Assign bugs to SET when there is no clear engineering team owner
* Make sure reported bugs are in fact bugs and recommend turning non-bugs into stories or feature requests

## Priority of Work

Below is how SET prioritizes what is worked on.

1. Quality issues affecting community.mattermost.com or community-daily.mattermost.com
  * When a high impact issue affects the community server, SET responds and is responsible to coordinate fixing
  * Primary goal is to restore stability, whether this is fixing or reverting code
2. Handles customer support escalation
  * Primary goal is to help with issues that require code change
  * Be helpful with training/knowledge sharing for the support team
  * Identify customer support requests that are features and route to PM as necessary
3. General bug fixes
  * Pick up any bugs in triage without an obvious owning feature team
  * Work on bugs in this order: hotfix, release, customer reported, other

## Customer and Pre-Sales Support Escalation Process

Part of SET's responsibility is to interface with the customer support team. SET's primary goal in respect to support is to triage escalated support issues, work on any high priority customer bugs requiring code change, as well as provide training and knowledge share with the customer support team. 

For details on the Customer/Pre-Sales Support Escalation Process, please refer to [this document](https://docs.google.com/document/d/1eEnG0YA6G8_1futRlvBs2Vm88xkc0nTnZCynYXZNTBE/edit?usp=sharing). 

