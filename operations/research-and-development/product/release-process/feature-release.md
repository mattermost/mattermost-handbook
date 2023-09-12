# Cloud and Self-Hosted Release Process

Mattermost core team works on a monthly release process, with a new version of Cloud and Self-Hosted shipping each month in [binary form](https://docs.mattermost.com/upgrade/upgrading-mattermost-server.html).

This document outlines the development process for the Mattermost core team, which draws from what we find works best for us from Agile, Scrum, and Software Development Lifecycle approaches. Please refer to [the Release Playbook](https://community.mattermost.com/playbooks/playbooks/t7s6wkmsfpf99xe6sxgricgd9e/outline) for a most up-to-date checklist.

## Release Timeline

Note: T-minus counts are measured in "working days" \(weekdays, Monday through Friday, excluding [the listed statutory holidays](https://handbook.mattermost.com/operations/workplace/people/working-at-mattermost/paid-time-off#holidays)\) prior to release day.

**Schedule for Cloud and Self-hosted releases**:

 - Feature Complete and release branch cut at T-24
    - All major features must be complete and ready to merge approximately five weeks prior to the self-managed release date. Prior to this day, the release manager makes sure everyone is aware of the impending deadline by posting reminders in the Release Discussion channel and messaging team leads. If any pull requests are not merged by this date, then the release manager changes release milestones in Jira after checking with team leads that those features can be pushed to a future release. Updates to prepackaged plugins should also be complete and merged by this date, with room to address bugs before code freeze. This is also the date when the release-X.Y is cut from master. Any additional changes to the release must first be merged to master before being cherry-picked to release-X.Y. All test servers should be configured to update daily from this branch.

 - Judgment Day at T-19
    - Approximately one week after feature complete, the release manager reviews the status of all features and issues. If anything needs to be cut, the Release Manager informs internal stakeholders in the Release Discussion channel and asks the feature owners to revert the code. There should be no known major issues included with the release.

 - Release Qualification starts at T-18
    - Immediately after judgment day and any reverts are completed, the release team officially begins release qualification. This includes verifying and closing tickets resolved for the release; running Rainforest release test run groups, Cypress automated tests, and release smoke tests; executing manual tests; and triaging new issues and re-testing as fixing becomes available.
Qualifying any individual issue occurs in both self-managed and Cloud test servers simultaneously, as the same artifacts will ship unchanged into each environment.

 - Code Freeze at T-10.
    - Ten business days prior to the release date, and near to the end of release qualification, code freeze prohibits all further changes to the release branch. No further code changes will be accepted, preventing last minute regressions, fixes, and additional testing. A final release build is cut and pushed to https://github.com/mattermost/mattermost, but marked as pre-release. The delivery team continues to triage and push minor bugs to the next release. If a showstopper issue is found, a patch release is required that may risk the remaining milestone dates.

 - Release Approval at T-8
    - Approximately two weeks after starting release qualification, the delivery team formally signs off on the complete release qualification. The pre-release bit on the corresponding GitHub release is manually removed. Note that this may be vX.Y.1 or a later patch release if fixes were required after code freeze.

 - Cloud Beta Release at T-7
   - The qualified release is smoke tested on the Cloud Beta production servers.

 - Cloud Professional Release at T-5
   - Two business days after soaking in cloud beta, the release is rolled out to customers in the professional ring.

 - Cloud Enterprise Release T-3
   - Once stabilized in cloud professional, the release is rolled out to customers in the enterprise ring. The actual date may be two or three business days later to avoid releasing to enterprise customers on a Friday.

 - Cloud Dedicated Release at T-2
    - Once stabilized in cloud enterprise, the release is rolled out to enterprise customers with dedicated clusters. As with T-3, the actual date may be one or two business days later to avoid releasing to dedicated customers on a Friday.

 - Self-Managed Release at T-0
    - On the first business day on or before the 16th of the month, the same build already qualified in Cloud is released for Self-managed customers. No rebuild is required. Marketing communications begin to roll out, and the release is communicated on the blog and other marketing channels.
