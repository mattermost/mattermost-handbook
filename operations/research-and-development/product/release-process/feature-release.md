# Cloud and Self-Hosted Release Process

Mattermost core team works on a monthly release process, with a new version of cloud and self-hosted shipping successively once a month.

This document outlines the development process for the Mattermost core team, which draws from what we find works best for us from Agile, Scrum, and Software Development Lifecycle approaches. Please refer to [the cloud & self-hosted release playbook](https://community.mattermost.com/playbooks/playbooks/7ya8gsijg3f1dkx84txzek6t1r/outline) for the release checklist.

A single release is qualified for both cloud and self-hosted at the same time, with both versions labelled as ``vX.Y.Z``. Outside of patch releases, no changes are released to self-hosted customers before they are first released to cloud customers.

## Release Timeline

Note: T-minus counts are measured in "working days" \(weekdays, Monday through Friday, excluding [the listed statutory holidays](https://handbook.mattermost.com/operations/workplace/people/working-at-mattermost/paid-time-off#holidays)\) prior to release day.

 - Feature Complete and Release Branch Cut at T-24
    - All major features must be complete and merged approximately five weeks prior to the self-managed release date. Prior to this day, the release manager makes sure everyone is aware of the impending deadline by posting reminders in the Release Discussion channel and messaging team leads. If any pull requests are not merged by this date, then the release manager changes release milestones in Jira after checking with team leads that those features can be pushed to a future release. Updates to prepackaged plugins should also be complete and merged by this date, with room to address bugs before code freeze. This is also the date when the ``release-X.Y`` is cut from master. Any additional changes to the release must first be merged to master before being cherry-picked to ``release-X.Y``. All test servers should be configured to update daily from this branch.

 - Judgment Day at T-19
    - Approximately one week after feature complete, the release manager reviews the status of all features and issues. Regression bugs are identified naturally in Community as well as on the release branch by the QA team. If anything needs to be cut, the Release Manager informs internal stakeholders in the Release Discussion channel and asks the feature owners to revert the code. There should be no known major issues included with the release. RC-1 is cut by the end of this day.

 - Release Qualification Starts at T-18
    - Immediately after judgment day and any reverts are completed, the release team officially begins release qualification. This includes verifying and closing tickets resolved for the release; running Rainforest release test run groups, Cypress automated tests, and release smoke tests; executing manual tests; and triaging new issues and re-testing as fixes become available. Progress is tracked in the [QA Approval playbook](https://community.mattermost.com/playbooks/playbooks/rpsa3y78t3gsun9ba8185s5gto/outline). Qualifying any individual issue occurs in both self-hosted and cloud test servers simultaneously, as the same artifacts will ship unchanged into each environment.

 - Code Freeze at T-10
    - Ten business days prior to the release date, and near to the end of release qualification, code freeze prohibits all further changes to the release branch. No further code changes will be accepted, preventing last-minute regressions, fixes, and additional testing. A final release build is cut and pushed to https://github.com/mattermost/mattermost, but marked as pre-release. The delivery team continues to triage and push minor bugs to the next release. If a showstopper issue is found, a patch release is required that may risk the remaining milestone dates.
    - Minor bugs or issues found after code freeze should generally be deferred to the next release, but it is occasionally necessary to patch the monthly release to address show stopper bugs or security issues. Introducing a patch increments the patch version (``vX.Y.Z+1``) and may delay the cloud or self-hosted release dates. We bump the patch version here to preserve the integrity of the code freeze deadline. We also schedule a retrospective to better understand how the issue was introduced and discovered so late in the release cycle.

 - Release Approval at T-8
    - Approximately two weeks after starting release qualification, the delivery team formally signs off on the complete release qualification. The pre-release bit on the corresponding GitHub release is manually removed. Note that this may be ``vX.Y.1`` or a later patch release if fixes were required after code freeze.

 - Cloud Beta Release at T-7
   - The qualified release is smoke tested on the cloud beta production servers.

 - Cloud Professional Release at T-5
   - Two business days after soaking in cloud beta, the release is rolled out to customers in the professional ring. Release documentation, including the changelog, is merged on this day.

 - Cloud Enterprise Release T-3
   - Once stabilized in cloud professional, the release is rolled out to customers in the enterprise ring. The actual date may be two or three business days later to avoid releasing to enterprise customers on a Friday.

 - Cloud Dedicated Release at T-2
    - Once stabilized in cloud enterprise, the release is rolled out to enterprise customers with dedicated clusters. As with T-3, the actual date may be one or two business days later to avoid releasing to dedicated customers on a Friday.

 - Self-Managed Release at T-0
    - On the first business day on or before the 16th of the month, the same build already qualified in cloud is released for self-hosted customers. No rebuild is required. Marketing communications begin to roll out, and the release is communicated on the blog and other marketing channels.
