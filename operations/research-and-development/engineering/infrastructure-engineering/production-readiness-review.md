# Production Readiness Review

The production readiness review (PRR) is a process that identifies the reliability needs of a service, feature (mid to large only) or a significant change to infrastructure. The Mattermost PRR has been inspired from the [production readiness review](https://sre.google/sre-book/evolving-sre-engagement-model/) from the SRE book. A PRR is considered a prerequisite for the Infrastructure team to accept responsibility for managing the production aspects of a service, feature or infrastructure change.

The goals of the readiness review is to improve the followings:
- System architecture and interservice dependencies
- Observability (metrics, monitoring, logging)
- Incident Response
- Capacity planning
- Change management
- Performance, availability, latency and efficiency
- Increase awareness and boost collaboration with a goal to built a cloud-native product

This will help to increase the collaboration between Product, Security and Infrastructure teams in order to bridge any gaps about a new service, feature or infrastructure change. The review document is not intended to be constantly updated and it reflects a snapshot of the reality of what is being deployed and the discussions around it. 

## Process

The PRR process is initiated by the DRI of the related work with the following steps:
1. Run the Mattermost PRR Playbook here
2. The title of the Playbook run should be self-descriptive for the change.
3. Include the relevant reviewers in the PRR Mattermost channel
4. Use the checklist in Playbook which will guide you through to complete the review

## Completion
Once all comments have been addressed and the reviewers are satisfied they could check off the task item in which they are owners. When all the set approvals are there, the playbook run needs to be closed.

Pro-tips approvals
The PRR playbook uses [Playbooks task actions](https://docs.mattermost.com/playbooks/work-with-tasks.html#task-actions), so when you are done with your review and you are ready to approve you can just write in the channel the following:
- SRE review is completed
- Platform review is completed
- etc.

This will automatically mark the task item list as done based on the current members of the engineering teams.
