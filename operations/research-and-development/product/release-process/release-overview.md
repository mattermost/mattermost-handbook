# Release Overview

Mattermost ships with a new version on the 16th of each month in [binary form](http://docs.mattermost.com/administration/upgrade.html#mattermost-team-edition).

For the past few years, Mattermost used a monthly “tick-tock” alternating release cycle. A tick-tock cycle refers to even-numbered releases (e.g., 5.26) containing new features, and odd-numbered releases (e.g., 5.27) containing only bug fixes and performance improvements. As our product and team continue to evolve, we're moving away from this alternating release cycle in favor of a general monthly release.

When security issues are found that warrant a patch release, we follow the [security release process outlined here](https://handbook.mattermost.com/operations/research-and-development/product/release-process/security-release).

## Release Numbering

Mattermost numbers stable releases in the following format:
**[Version Number].[Major Build Number].[Minor Build Number]**

**Version Number:**

- Purpose: Major system releases introduce significantly new functionality or change existing product behaviour
- Release frequency: Unscheduled. Major system releases are infrequent
- Example: v1.x.x, v2.x.x

**Major Build Number:**

- Purpose: Introduce new features, bug fixes and performance improvements
- Release frequency: Monthly on the 16th of each month
- Example:
  - Even numbers (e.g. v1.2.x, v1.4.x): New features and bug fixes
  - Odd numbers (e.g. v1.3.x, v1.5.x): Quality release including performance improvements and bug fixes

**Minor Build Number:**

- Purpose: Patch existing releases when severe bug fixes or security patches are required
- Release frequency: As required
- Example: v1.2.5, v1.2.6

## Releasing Together with Cloud

The goal is to release more quickly to Cloud, but to do that it is essential that we get on track with automated testing. Feature flags work is also in the progress, which will be vital for this new release process. PRs don’t need to be cherry-picked to releases, except any last bug fixes that get merged after the release branch is cut as well as any hotfixes.

Cloud release cycle = every 2 weeks:
1 week prior, fast-forward master to cloud branch.

Schedule for “cloud-validated” release:
(T-30) - Feature Review / Judgment Day / Cut release branch and cut RC1
(T-8 to T-7) - RC testing and final QA testing
(T-5) - Code Freeze
(T-2) - Cut Final
(T-0) - Release Day

1. The feature is tested on a PR and E2E test automation is added.
2. Large features are added behind a feature flag.
3. The feature flag is initially “off” in the cloud and will be rolled out slowly.
4. Feature flag rollout plan:
5. [T-8] Prior to the cut to on-premise, the Release manager reviews new feature flags and provides a report to the PM/QA team for their review. Essentially a feature will be included in an on-prem release once the feature flag has been removed.
6. [T-7] On-premise release branch and release candidate are cut based on cloud release.
7. On-premise release candidate is smoke tested.
8. On-premise release final is cut and released publicly.

## Tracking feature flags

Release manager is able to look at the version we have deployed to cloud. Also, when we are hooked up to split.io there will be a dashboard where you can see active and historic feature flags. Any feature that has its flag removed would be included on any on-prem releases past the point where that removal was merged. Feature flags proposal.

## Adding milestones for tickets and PRs

Releases will now be focused on "ship features/improvements when they're ready for cloud, and then they'll get to an on-prem release once they've been on cloud for 2+ weeks".

 - A new “cloud” branch (based off from master) is used and any regression bug fixes for the next cloud release will be cherry-picked there.
 - This applies to webapp / server / redux / enterprise repos.
 - A fix version such as “Cloud (November 24)” is added in Jira to track regression bug fixes for cloud releases.
 - The on-prem releases will be based on a cloud release. This is decided by the Release Manager / Cloud team based on the timeline between cloud releases and the release day of on-prem releases.
 - PRs currently being merged into master don’t need an on-prem milestone added to them. Release Manager will track merged PRs and help ensure that correct milestones are added as needed. Any concerns can be brought up for discussion on a case-by-case basis. There may be a clearer process for this in the future.

## Process for triaging cloud customer issues

Here's a great example of a bug report <jump to convo> we should have a process to triage.
No plugins were available in Mattermost Cloud.

When triaging a report, consider the following:
Impact of the bug on customers
Severity of the issue
Risk and effort of reverting to the last version or fixing a bug

Criteria
1. "We need to revert to the last version" process
 - Crash or all services are down due to a bug; affects some to all cloud customers.
2. "We need to release this ASAP" process
 - A severe regression or loss of function; affects some to all customers.
3. "It's ok to wait until next release" process
 - Loss of function, but little effect on customers.

Responders
 - Who is making the decision on which process above we need to follow?
In some cases it is the SET on-call commander, in some cases other people such as the release manager or devs who notice / get notified about the report.
Bugs will be fixed by either SET team or respective dev teams, depending on availability and expertise.

Reports
 - The Cloud team has created a central channel for escalations from support (Cloud Support channel in the Staff team).
Additionally when a report is posted, should make sure to notify SET lead, release manager, and dev lead of the team that owns the feature.

## Frequently Asked Questions

**Q: What is the release cycle for the React Native mobile apps?**

  - A: The mobile apps follow the same monthly release cycle as Mattermost Server/Webapp, releasing on the 16th of each month.

**Q: What is the release cycle for the Mattermost Desktop app?**

  - A: Desktop releases are currently released as required.

**Q: When is release branch cut for a release?**

  - A: Once the cloud release that the next on-prem release is releasing with has been shipped.

**Q: How are PRs merged for release?**

  - A: PRs are first merged to master. The dev who submitted the fix is also responsible for cherry-picking it to the release branch after a release branch has been cut.

**Q: How is cherry-picking done?**

  - A: See the [cherry pick process documentation](https://developers.mattermost.com/contribute/getting-started/branching/#cherry-pick-process-developer/) for details.

**Q: What is community.mattermost kept on?**

  - A: community.mattermost is kept on the most recent cloud release.

**Q: What is community-release.mattermost kept on?**

  - A: community-release.mattermost is kept on the currently in progress cloud release.

**Q: What is community-daily.mattermost kept on?**

  - A: Normally on `master` branch.

**Q: How to remove a feature/bug from a release?**

  - A: Revert from release branch. Optionally revert from master.

**Q: How are NOTICE.txt PRs submitted?**

  - A: PRs are first merged to master. The dev who submitted the fix is then responsible for cherry-picking it to the release branch.

**Q: Is an improvement a feature or a bug?**

  - A: Usually features/story tickets.

**Q: How does release team monitor what changes went into a release?**

  - A: Monitor the commit history of the respective release branch, e.g., https://github.com/mattermost/mattermost-server/commits/release-5.4 contains commits that shipped with mattermost-server v5.4. Jira ticket is resolved after cherry picking is done.

**Q: How does translations branching work?**

  - A: Lock the translation server to the release branch. The translation PR will be submitted against the release branch and it can just be merged directly to the release branch without cherry-picking. When the translation server is locked back to master, the next PR against master will include those translations that went in for the release branch.

**Q: How does cutting mobile builds work?**

  - A: See instructions here: https://developers.mattermost.com/internal/mobile-build-process/.

**Q: What is the process for community PRs?**

  - A: Review, merge, and cherry-pick.

**Q: Will RC testing remain, or will RC testing process change?**

  - There will be some manual RC testing until all release tests are automated.

**Q: Are mobile and desktop included in the cloud first strategy?**
  - Mobile and desktop apps are not affected at this point.

**Q: Creating tickets for features that were cut from on-prem - Is this also how it continues to be tracked to see whether it's ready for the next release?**
  - Any feature that's promoted out of the feature flag process would be turned on for the on-prem releases. That way on-prem only gets fully ready or tested features and not ones still being tested. There will be some cases where we need to make a change to fix or change something for the on-prem release (e.g. a bug that only happens if you use a certain on-prem setting or a certain database we don't use in cloud). In those cases the on-prem release might have some changes that are not a direct copy of the cloud build.

**Q: What will the customer support team need for cloud releases?**
  - We’ll use the Cloud Releases channel for updates and post the changelog there (with tagging the support team). We’ll also post a more official changelog on launch day. This may be automated in the future. We should also have a dashboard or other that shows the current version deployed to cloud, and which commits are in. We can put it in the header of the Cloud Releases channel.

**Q: How will versioning work?**
  - Version numbers will be less meaningful for cloud. Proposing the name of this to be capabilities following the naming used by OpenGL. It's not whether or not a feature is enabled, but it's whether or not the server is capable of supporting the feature.
