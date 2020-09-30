---
description: 1% DRAFT
---

# Integrations Team Processes

## Weekly Team Meeting

- Schedule meeting items by running `/agenda queue Tuesday [item]` in [`~extensibility-meeting`](https://community.mattermost.com/core/channels/extensibility-meeting).

### Workflow

1. Metrics updates: 2 min presentation on interesting metrics on https://mattermost.looker.com.
2. [Plugin Release Updates](https://github.com/orgs/mattermost/projects/1): Was did we ship in the last sprint? What do we want to ship in the next 4 weeks? What are blockers for that?
3. Thursday R&D Demo: Decide what to demo.
4. Guilds Updates: Short update from every guild meeting. If there isn't anything relevant, skip to the guild.
5. Triage Jira Toolkit, Jira Integrations, and GitHub.
6. Go through queued meeting items.
7. (Optional) Quick stand up using [the GitHub board](https://github.com/orgs/mattermost/projects/1) and Jira.
8. Remove all `Done` items from both GitHub boards.

## QA testing

- QA testing is require for all changes for not Beta plugin in the Marketplace.
- QA testing may be shipped for Beta plugins.
- QA testing is not required to changes that don't touch the production code of a plugin e.g. tooling changes.

### Peer Testing Process

1. Dylan will @-mention reviewers and request peer testing posting a link to the process.
2. Using session-based testing example format provided developers will perform functional testing on the PR and take lightweight session notes. See example attached here: https://mattermost.atlassian.net/wiki/download/attachments/619937892/SampleSessionNotes.txt.
3. Once testing is done, developers will at mention Dylan in a comment and attach their session notes.
4. Dylan will review session notes.
5. As appropriate, Dylan will make updates to release testing based on functional changes or previously untested cases.
6. Dylan will approve the PR for merge.
7. Any functional changes will be included in the next end to end test on the version bump PR as usual.

#### Things to be mindful of (WIP):

- For visual changes, ensure that themes are properly applied.
- When front end changes are made you should often test in desktop as well as browser as the JS is different.
- Icons generated with system font can be different on from Mac to Windows.

#### Testing notes example

```
Scope
------

<!-- Your understanding of what functional impact the PR will have on the product -->

- Display username that created zoom meeting #62.
- Test that username of meeting creator is always shown.

Testing notes
----------------

<!-- Testing you've done that you feel validate the change and cover any needed regression -->

- User name is displayed in with Zoom meeting post as expected.
- Tested switching mapped users to ensure display remains accurate.
- Tested updating username to ensure display.
- Trigger 30 second meeting collision post to ensure the functionality is also affected by the enhancement.

Follow-up concerns
-------------------

Seeing an intermittent connection issue with Zoom on http://dkh-local.ngrok.io. Seems to occur on desktop.
```

## Ticket Workflow

### Jira

- Jira ticket must be filled for:
    - Planed changes in the core product (Server, Webapp, Mobile, Redux).
    - Bugs in the core product (Server, Webapp, Mobile, Redux).
- Jira ticket may be filled for larger multi-plugin projects.

### GitHub

- For all confirmed bugs a GitHub issue on the corresponding repository must be filed.
- For all enhancements a GitHub issue on the corresponding repository should be filed.
- Add a `Type/X` label to make clear what type the ticket is.
- You may add a `Difficulty/X` label to set a mana estimate.
    - `Easy` means 2 mana
    - `Medium` means 4 mana
    - `Hard` mean 8 mana
- Staff members add the issues there are working on for the current sprint to https://github.com/orgs/mattermost/projects/1.
    - Putting an issue is always preferred over putting a PR on the board.

# Plugin Release Process

WIP: Migrating links and content from: https://github.com/jfrerich/plugin-release-process/blob/master/README.md.

[GitBook Entry](https://app.gitbook.com/@jason-frerich/s/plugin-release-process)  
[GitHub Page](https://github.com/jfrerich/plugin-release-process)

![horizontal line](.gitbook/assets/0.png)

## Overview

The release process for modifying plugin versions and plugin version dependencies currently requires a developer to perform several non-automated tasks. Bumping, tagging, releasing, publishing, and bundling \(preloading\) versions are not necessarily complicated, but a formal set of steps is required and should be followed. This document describes those processes in detail and will be used to help standardize and automate these flows in the future.

## Goals

1. Define the steps required to bump, tag, release, publish, and bundle plugin versions.
2. Through defining specific tasks during the process we will be able to define protocols and identify areas for automation improvements.

## Scope

This document covers the current steps required to perform the following tasks:

1. Bump the current version of an existing plugin.
2. Tag a version of a plugin for release.
3. Bundle a plugin version to a Mattermost server release.
4. Publish a bumped plugin version to the Plugin Marketplace.
5. Publish a new plugin to the Plugin Marketplace.
6. Release to `community.mattermost.com`.

The Future Enhancements section of this document describes additional suggestions for automating some of these tasks.

## Plugin Release Flows

### Considerations when bumping and releasing a plugin version

\(**`TODO:`** Need permanent place to place the spreadsheet\)

* Compare commits from last bump/tagged release.
* Documentation \(README.md\) changes aren’t necessarily vital.
  * Documentation through bundled releases aren’t viewable through the app and users will be looking at the latest master commit in the GitHub repo.
* Keep spreadsheet up to date.
* The PR for the version bump \(in the plugin repo\) does not mean that is the last commit to get tagged. This step only bumps the version. The tagging step actually determines the commit that is tagged with the release tag.

### Bump current version of an existing plugin

\(**`TODO:`** First determine the next version number\)

* Feature or patch bumping determined by commits being added from previous release tag.
* Look through existing Issues and PRs and make sure the Milestone label is added for items to be included with release.
* Update in Google Spreadsheet.

\(**`TODO:`** Use SemVer \`v.X.feature.patch\` to determine which to bump\)
\(**`TODO:`** must have admin access\)

Changing the version of a plugin is no different than any other PR and requires 2 Developers and 1 QA Reviewer. Also add a PM review to verify the plugin change.

#### Create a commit with new version

* Verify no existing security issues \(using [Updating Security Alerts Through CLI](./#updating-security-alerts-through-cli)\).
  * If security issues exist, submit PR and merge before bumping version.
* `git pull` on the master branch in your local plugin repository to prepare for creating a branch.
* `git checkout -b bump-version-vX.X.X` to create a branch to perform the necessary edits.
* Edit `plugin.json` and bump the plugin’s `version` field in the json object. This file is located in the `root` directory of the plugin.
*  Modify `release_notes_url` to match the new bumped version.
  * Example: "release\_notes\_url": "[https://github.com/mattermost/mattermost-plugin-todo/releases/tag/v0.3.0](https://github.com/mattermost/mattermost-plugin-todo/releases/tag/v0.3.0)".
* `make apply` to update the plugin manifest files. The manifest files exist for server and webapp plugin directories.
  * Possible manifest files are `server/manifest.go`, `webapp/src/manifest.ts`, and `webapp/src/manifest.js`.
* `git status` verify no untracked files will get added with following `git -A`.
* `git add -A` if the make target builds successfully to add the files for committing.
* `git commit -m “Bump version to 1.1.2”` to commit the new commit.
* `git push --set-upstream origin bump-version-1.1.2` to push the commit to origin and prepare the PR.

#### Create a PR against the master branch of the plugin repository

* **Use as automation template** 
  * [**https://github.com/mattermost/mattermost-plugin-custom-attributes/pull/21**](https://github.com/mattermost/mattermost-plugin-custom-attributes/pull/21)
* **PR Title:** `Bump version to X.X.X`
* **PR Summary:**: `Bump version to X.X.X` \(use the same text for the PR summary\)
  * Add any further reasoning or description for version bump \(if necessary\)
* Add 2 Developers, 1 PM, and 1 QA for review.
* Add `Dev Review`, `QA Review`, and `PM Review` labels.
* Add Release Notes Proposal in the PR so others can verify before moving to tag/release [https://github.com/mattermost/mattermost-plugin-custom-attributes/pull/21](https://github.com/mattermost/mattermost-plugin-custom-attributes/pull/21).

  ![](.gitbook/assets/image.png)

### Tag/cut a version of a plugin for release

After the PR for bumping the version of a plugin has been merged, you can now tag the version for release.

**Prerequesite:** In order to cut releases using matterbuild slash commands, you will need to be added to the following `config.json`:

* [https://github.com/mattermost/platform-private/blob/master/matterbuild/config.json](https://github.com/mattermost/platform-private/blob/master/matterbuild/config.json)

Cut the release using the following as an example. Note this is a slash command for use inside Mattermost:

`/mb cutplugin --tag v1.2.0 --repo mattermost-plugin-todo`

CI runs can be viewed at [circleci.com/gh/mattermost](https://circleci.com/gh/mattermost). If CI jobs complete successfully, a new release will automatically be produced and viewable under the **Releases** tab in the plugin repo.

Matterbuild will respond with message upon success. Now view the release link and update the commit messages. This is a subjective task where determine if a commit is a feature of enhancement. Edit the release messages and arrange accordingly.

The next steps are to add the plugin to the Plugin Marketplace. The instructions are included in the return message upon a successful `cutplugin` command.

* Matterbuild created the release notes with the following command:
* `git log --pretty=oneline --abbrev-commit --no-decorate --no-color $(git describe --tags --abbrev=0)..HEAD`

### Bundle a plugin release version to a Mattermost server release

\(**`TODO:`** Branch name - determine naming convention for PR branch name\)
\(**`TODO:`** PR - determine naming convention for PR Title\)
\(**`TODO:`** PR - determine naming convention for PR Summary\)
\(**`TODO:`** PR - inside summary get list of from -&gt; to versions with automation\)

Plugins that are released with Mattermost are called bundled plugins. These plugins are included with the software and need only to be configured.

* `git pull` the latest master branch on mattermost-server
* Create a new branch so you can modify the plugin versions
  * `git checkout -b bundle-plugins-v5.20`
  * Use branch naming convention `bundle-plugins-vX.XX`
* Edit Makefile
  * Locate `# Plugins Packages` comment
  * Modify plugin release versions
* Create PR against master branch with following:
  * **Title:** Update bundled plugins for vX.XX
  * **Summary:** List of updated plugins
    * Ideally includes from version -&gt; to version for each plugin

### Publish a plugin release version to the Plugin Marketplace

The steps to have a plugin version added the Plugin Marketplace are included with the success of an `/mb cutplugin` slash command.

![](.gitbook/assets/image%20%283%29.png)

If a new plugin is being added, you'll need to add the repo name to the `repositoryNames` array in `cmd/generator/main.go`.

## Plugin Intake

### Create PR for Initial Review

\(**`TODO`**: See if `hub` CLI can automate PR creation\)
\(**`TODO`**: Need to instruct new plugins to initialize a commit that can be easily compared for PR. Options are starter-plugin commit or empty branch. Git compare dirs to see if first commit was starter plugin or included changes from author\).
\(**`TODO`**: Review anti-pattern link [Do Not Issue Pull Requests From Your Master Branch - Learn, Converse, Share](https://blog.jasonmeridth.com/posts/do-not-issue-pull-requests-from-your-master-branch/).
\(**`TODO`**: Cannot assign reviewers easily in forked branch in my personal repo. Try forking to Mattermost.
\(**`TODO`**: Don’t have forking permissions to Mattermost Organization.

This is a brief overview of the steps required to create the initial PR for Plugin Intake Review.

* **Fork the repo so no possibility to mess up author's repo**
  * Use GitHub \(possibly hub cli\)
* **Insert empty root commit into master \(probably over kill\)**
  * Most plugins will start from starter-template
    * Skip this section if using first commit from author's master branch
  * `git checkout --orphan emptyroot`
  * `git rm -rf .`
  * `git commit —allow-empty -m ‘empty root commit for PR’`
  * `git rebase —onto emptyroot —root master`
  * `git branch -d emptyroot`
* **Create branch: `initial-commit-for-PluginReview-compare`**
  * _This branch is for creating PR from `PluginReview` branch to view all changes to the repo from the `intial commit`_
  * `git checkout <commit-hash>`
    * Choose commit to compare against latest master
    * Could use empty root commit \(overkill\) or initial commit in repo \(likely from plugin-starter template\)
  * `git checkout -b initial-commit-for-PluginReview-compare`
    * Create as new branch
  * `git push --set-upstream origin initial-commit-for-PluginReview-compare`
    * Push to remote
* **Create branch: `PluginReview-master-dev-copy`**
  * _This branch is for doing the review. A PR will be created against the initial branch to view all the changes from the plugin-starter-template_.
  * `git checkout master`
  * `git checkout -b PluginReview-master-dev-copy`
  * `git push --set-upstream origin PluginReview-master-dev-copy`
* **GitHub create PR**
  * Title: `Initial Plugin Review`
  * Base: `initial-commit-branch-for-PR`
  * Compare: `PluginReview-master-dev-copy`
* **Create Initial Plugin Review Issue in Repo**
  * Use the following as a template
  * Track checklist items here
  * Issue to be closed after plugin review is completed
  * [example](https://github.com/mattermost/mattermost-plugin-agenda/issues/5)
* **Review checklist items and start creating PRs against `master`**
* **Create PR `PluginReview-master-dev-copy` to `master` to view all proposed changes**

### Plugin Review Checklist

\(**`TODO`**: when automate, add checklist into description section\)  
\(**`TODO`**: How to automate `min_server_version` verification [link](https://community.mattermost.com/core/pl/1agmru9n67ffxkmz7aet51ptbw%29%29%20%20%20%28**`TODO`**:%20if%20plugin%20began%20with%20mattermost-plugin-starter-template,%20find%20way%20to%20sync%20with%20latest%20start-template%20files%20%28Makefile,%20.lintrc%20files,%20.etc%29%20\)

* README.md
  * Installation instructions provided, detailed and accurate
  * Use cases are defined and documented
* Plugin Setup Files
  * `plugin.json`
    * `id` - try to make unique \(Ex. `calendar` likely to collide as \# plugins grow\)
    * `min_server_version` - verify works using specified version
  * server/plugin.go
* Installation
  * compare Makefile to latest `mattermost-plugin-starter-template`
  * `make` executes without errors
  * no lint errors
* Security
  * `npm audit` returns with no issues
* Best Practices
  * recognize anti-patterns
  * variable/function naming \(possibly automate check with go or write AST script\)
    * vars: fooBar
    * Public Methods: FooBar\(\)
    * Private Methods: fooBar\(\)
  * idiomatic Go
    * err handling

## Plugin Intake Process

\(**`TODO`**: create as a ticket in an common area. don't use `make solar-lottery` the golder template\)

This is the process by which Mattermost takes ownership of a plugin and most the plugin under the Mattermost GitHub Organization. The intake process is a list of checks that need to be completed. The list is created as an issue in the plugin repo and updated as items are completed. Use \[this issue template\]\([https://github.com/jfrerich/plugin-release-process/issues/1](https://github.com/jfrerich/plugin-release-process/issues/1)\) for each intake.

The intake process in this document originated from this Jira ticket [https://mattermost.atlassian.net/browse/MM-21180](https://mattermost.atlassian.net/browse/MM-21180).

Plugin must first pass intake review process.

## Future enhancements

This section lists possible enhancements to the release flow. By gathering the details of the flow and breaking into specific tech areas, we can start create a design spec and start building automation for the entire plugin release flow.

There is an open ticket to automate syncing plugins with \[mattermost-plugin-starter-template\]\([https://github.com/mattermost/mattermost-plugin-starter-template](https://github.com/mattermost/mattermost-plugin-starter-template)\):

* [https://mattermost.atlassian.net/browse/MM-21722](https://mattermost.atlassian.net/browse/MM-21722)

### Automation \(WIP\)

\[mattermost-plugin-sync\]\([https://github.com/jfrerich/mattermost-plugin-sync](https://github.com/jfrerich/mattermost-plugin-sync)\)

1. Bumping Plugin version.
2. Tagging version for release.
3. Bundling plugins with Mattermost.
4. Publishing plugins to the Plugin Marketplace.
5. Filing Jira tickets to toolkit for publishing to the Plugin Marketplace.
6. MM command to show bundled releases of current MM-server version.
   1. Compare with latest tagged release of repos.
   2. Include commit PR history for viewing changes since last tagged release.

## SECURITY RELEASE / UPGRADE PROCESS

\(**`TODO`**: Automate checking all released plugins through CLI, cron, or GH webhook event\)  
\(**`TODO`**: User must be repo admin to see and resolve automated security issue\)  
\(**`TODO`**: Need method to hook to tell us when security issue is found\)  
\(**`TODO`**: PR for security updates should be discrete\)  
\(**`TODO`**: investigate `npm ls hoek`\)

Security alerts are displayed when viewing a GitHub repo and are resolved via the automated `dependabot` tool

### Updating npm Dependencies CLI

* `git checkout latest master`
* `git checkout -b bump-dependency-versions`
* `cd webapp/`
  * `npm-check -E -u` to view the changes interactively
    `npm-check -E -y` to update without interactive
* `git add package-lock.json package-lock.json`
* `git commit -m "Update dependencies"`
* `git push --set-upstream origin bump-dependency-versions`
* Create PR
  * Title: `Update Dependencies` \(Will automatically get set\)
  * Summary: Update dependencies

### Updating Security Alerts Through CLI

* `git checkout latest master`
* `git checkout -b npm-audit-fix`
* `cd webapp/`
* `npm audit` - will return list of security issues
* `npm audit fix` - updates ``package-lock.json`` dependencies
* `git add package-lock.json`
* `git commit -m "Update dependencies"`
* `git push --set-upstream origin npm-audit-fix`
* Create PR
  * Title: `Update Dependencies` \(Will automatically get set\)
  * Summary: &lt;library\_name&gt; &lt;from\_ver&gt; -&gt; &lt;to\_ver&gt;

### Updating Security Alerts Through GitHub

Github displays security alerts when viewing a GitHub repo.

![Security Notification](.gitbook/assets/security-notification.png)

View all alerts by clicking on the **View security alerts** button.

![Security Alerts](.gitbook/assets/security-view-alerts.png)

Clicking on a specific security alert will open the details alert and provide a **Create automated security update** button. Click the button to have `dependabot` begin generating an automated security update.

![Security Alert Details](.gitbook/assets/security-serialze-javascript.png)

![Generating automated security update](.gitbook/assets/security-generating-automated-security.png)
