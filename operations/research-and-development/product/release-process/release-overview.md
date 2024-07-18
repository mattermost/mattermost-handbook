# Release Overview

Mattermost ships with a new version once a month for both cloud and self-hosted customers.

## Release numbering

Mattermost numbers stable releases in the following format: **\[Major Build Number\].\[Minor Build Number\].\[Patch Build Number\]**

**Major build number:**

* Purpose: Major system releases introduce significantly new functionality or change existing product behavior
* Release frequency: Once a year. Major system releases are infrequent
* Example: v1.x.x, v2.x.x

**Minor build number:**

* Purpose: Introduce new features, bug fixes and performance improvements
* Release frequency: Monthly cadence
* Example: v1.2.x, v1.4.x

**Patch build number:**

* Purpose: Patch existing releases when severe bug fixes or security patches are required
* Release frequency: As required
* Example: v1.2.5, v1.2.6

## Objectives

The goal is to deliver value to users quickly by a\) shipping fast to get features to customers quickly for experimentation/feedback, and b\) iteratively behind feature flags as a protection if any issues arise. This document outlines the principles and guidelines for how we release a new update of each product line on a monthly basis.

## Release Principles

1. **Focus on High Impact by shipping every new feature and any riskier code changes behind a feature flag**
   * Each development team is individually responsible for quality and deciding if a feature should be included in a release or not \(with the release team giving guidelines\). This may mean shipping more patch releases, but we can manage some of this by using feature flags. This also requires good test automation coverage.
2. **Automate**
   * Automate release processes and tasks.
   * Automate release tests and have E2E tests for features.
3. **Earn Trust by communicating to external and internal stakeholders clearly**
   * Enables us to make expectations for releases clear for all stakeholders.
   * Make expectations for each release clear \(release dates, etc.\). Communicate. Ensure that everyone on the team is familiar with the release processes.
   * Release notes, minimum version requirements, and any important upgrade notes need to be available for customers and communicated via docs, blog, emails, and channels.
4. **Earn Trust by including all stakeholders \(Tech Writers, Marketing, QA, etc.\) early in the release process**
   * Enables us to avoid missing key tasks and to avoid last minute work.
   * E.g. When opening a PR, add a “Docs/Needed” label for any PRs that need docs and communicate to Tech Writers. This ensures that we have time to complete docs on time.
   * Make tracking bugs and testing requirements easy. E.g:
     * Resolve Jira tickets for QA when PRs are merged (and cherry-picked).
     * Add QA test steps to Jira tickets and/or PRs.
     * Add Fix Versions and Milestones in Jira/PRs for bugs/tickets for easy tracking.
     * Add clear Release Notes on PRs.
5. **Achieve Customer Obsession by doing retrospectives on release issues and monitoring customer/community release bug reports after releases**
   * This allows us to learn from issues so that they don’t happen again and to fix critical bugs asap.
   * Retrospectives for issues and dot releases are important.
   * Monitor community and customer reports in GitHub, Forum, and channels like Ask R&D, in partnership with the Support team.

## Release Cycles

We follow [the Agile Release Train method](https://www.scaledagileframework.com/agile-release-train/). If releases are not approved by a certain date, then we miss the release train.

 - Cloud/self-hosted [release process is outlined here](https://handbook.mattermost.com/operations/research-and-development/product/release-process/feature-release).
 - [Mobile app](https://handbook.mattermost.com/operations/research-and-development/product/release-process/mobile-release) releases follow the same release cadence as cloud/self-hosted.
 - [Desktop app release process](https://handbook.mattermost.com/operations/research-and-development/product/release-process/desktop-release).
 - When issues are found that warrant a patch release, we follow the [dot release process outlined here](https://handbook.mattermost.com/operations/research-and-development/product/release-process/dot-release).

## Release dates communication

Release dates are currently communicated in the following ways.

1. Channels
   * The [Release Announcements channel](https://community.mattermost.com/core/channels/release-announcements) functions as the main location for important announces about Cloud test server updates, and for release dates and feature complete deadlines. Specific teams or people may be at-mentioned if the announce is targeted at someone.
   * The [Announcements channel](https://community.mattermost.com/private-core/channels/announcements) functions as the central place to find the most important announcements for new releases with links to changelogs and/or blog posts that can be easily shared with external stakeholders including MLT and customers.
2. Mattermost Release Dates Calendar
   * Lists key release dates and deadlines.
3. PM and R&D meetings
   * Updates are provided on upcoming key dates and/or features as needed.
4. Productboard
   * [Productboard](https://mattermost.productboard.com/data/releases) - A milestone overview of what releases + features are coming up.
5. Spreadsheet
   * [Overview of release deadlines and cherry-picking guidelines](https://docs.google.com/spreadsheets/d/1jGEnuaZxosmC-JSUXFeZOR7I34ORFtNjPVw8hvzCIC4/edit#gid=0).

## Plugin Release Processes
 - The sample [Plugin Release Playbook](https://community.mattermost.com/playbooks/playbooks/f4oh16ardfbyfgkas1cb6intmw/outline) helps give an overview of needed steps for plugin releases.

## Tracking feature flags

Details on feature flags: [https://developers.mattermost.com/contribute/server/feature-flags/](https://developers.mattermost.com/contribute/server/feature-flags/).

## Adding milestones on PRs and Jira tickets

* If the PR is scheduled for a specific Mattermost release, please add the `Cherry-pick Approved` label and self-managed milestone on the PR. The Release Manager keeps track of PRs with the `Cherry-pick Approved` label and self-managed milestone on a daily basis.
* The Release Manager also tracks regression bugs and aims to ensure that they get fixed for the next release.
* A fix version is added in Jira to track regression bug fixes for Mattermost releases.

## Triaging Mattermost customer issues

When triaging a bug report, consider the following:

* Impact of the bug on customers.
* Severity of the issue.
* Risk and effort of reverting to the last version or fixing a bug.

**Criteria**

1. "We need to revert to the last version" process:
   * Crash or all services are down due to a bug; affects some to all Mattermost Cloud customers.
2. "We need to release this ASAP" process:
   * A severe regression or loss of functionality; affects some to all Cloud customers.
3. "It's OK to wait until next release" process:
   * Loss of function, but little impact on Cloud customers.

**Responders**

* Who is making the decision on which process above we need to follow?
  * In some cases it's the customer support teams or Cloud teams, and in some cases it's other people such as the Release Manager or developers who notice or get notified about the report.
* Bugs will be fixed by either the CRE team or by respective development teams, depending on availability and expertise.

## Frequently Asked Questions

**Q: What is the release cycle for the React Native mobile apps?**

* A: The mobile apps follow the same monthly release cycle as Mattermost Server/Webapp, releasing on the 16th of each month.

**Q: What is the release cycle for the Mattermost Desktop app?**

* A: Desktop releases are shipped every 3 months starting in March, 2023. For more details, see https://handbook.mattermost.com/operations/research-and-development/product/release-process/desktop-release.

**Q: When do I need to have a feature PR to be included into the next release?**

* A: Aim to have the PR merged before the Feature Complete deadline. The earlier in the monthly cycle the PR is merged, the higher the chances are for it to be included in that month's release. The quality of our releases is important and feature PRs are not normally cherry-picked to a release branch.

**Q: How can I determine if my merge request will make it into the next release?**

* A: The Release Manager adds PR milestones and Jira fix versions for tracking. You can also check the release branches (e.g. in the mattermost repo) to see what's included.

**Q: Do we use Playbooks for releases?**

* A: Yes, playbooks are used for cloud & self-hosted, mobile and desktop releases, and for dot releases and plugin releases.

**Q: How are PRs merged for release?**

* A: PRs are first merged to master. As needed, the dev who submitted the fix is also responsible for cherry-picking it to the release branch after a release branch has been cut.

**Q: How is cherry-picking done?**

* A: See the [cherry pick process documentation](https://developers.mattermost.com/contribute/getting-started/branching/#cherry-pick-process-developer/) for details.

**Q: What version is community.mattermost.com kept on?**

* A: Normally on `master` branch and it updates daily.

**Q: How to remove a feature/bug from a release?**

* A: The feature flag is turned off. Another option is reverting the feature from the `master` and `release` branches.

**Q: How are NOTICE.txt PRs submitted?**

* A: PRs are first merged to `master`. The dev reviewer is responsible for helping cherry-picking it to the `release` branch as needed.

**Q: Is an improvement a feature or a bug?**

* A: Usually features/story tickets.

**Q: How does release team monitor what changes went into a release?**

* A: Monitor the commit history of the respective `release` branch, e.g., [https://github.com/mattermost/mattermost-server/commits/release-7.5](https://github.com/mattermost/mattermost-server/commits/release-7.5) contains commits that shipped with `mattermost-server v7.5`. Jira ticket is resolved after cherry picking is done.

**Q: How does translations branching work?**

* A: The translation PR will be submitted against the master branch.

**Q: What is the process for community PRs?**

* A: Review, merge, and cherry-pick as needed.

**Q: What information does the Customer Support team need for Cloud releases?**

* The Announcements channel in the Staff team is used for release updates and for posting the changelog.
