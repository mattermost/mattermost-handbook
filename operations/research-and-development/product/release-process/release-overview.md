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

## Frequently Asked Questions

**Q: What is the release cycle for the React Native mobile apps?**

  - A: The mobile apps follow the same monthly release cycle as Mattermost Server/Webapp, releasing on the 16th of each month.

**Q: What is the release cycle for the Mattermost Desktop app?**

  - A: Desktop releases are currently released as required.

**Q: When is release branch cut for a release?**

  - A: One week prior to the release day.

**Q: How are PRs merged for release?**

  - A: PRs are first merged to master. The dev who submitted the fix is also responsible for cherry-picking it to the release branch after a release branch has been cut.

**Q: How is cherry-picking done?**

  - A: See the [cherry pick process documentation](https://developers.mattermost.com/contribute/getting-started/branching/#cherry-pick-process-developer/) for details.

**Q: What is community.mattermost kept on?**

  - A: community.mattermost is kept on the latest released release.

**Q: What is community-release.mattermost kept on?**

  - A: community-release.mattermost is kept on the currently in progress release. Once the release branch is cut for a release, then community-release.mattermost is updated to that release branch.

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

**Q: How does updating dependencies work?**

  - A: Dependency updates will only occur in feature releases, unless they contain security fixes.

**Q: What is the process for community PRs?**

  - A: Review, merge, and cherry-pick.
