# Feature Release Process

Mattermost core team works on a monthly release process, with a new version shipping on the 16th of each month in [binary form](https://docs.mattermost.com/upgrade/upgrading-mattermost-server.html).

This document outlines the development process for the Mattermost core team, which draws from what we find works best for us from Agile, Scrum, and Software Development Lifecycle approaches. Please refer to [the Self-Managed Release Playbook](https://community.mattermost.com/playbooks/playbooks/t7s6wkmsfpf99xe6sxgricgd9e/outline) for a most up-to-date checklist.

## Release Timeline

Notes:

* All cut-off dates are based on 10am \([San Francisco Time](http://everytimezone.com/)\) on the day stated.
* T-minus counts are measured in "working days" \(weekdays, Monday through Friday, excluding [the listed statutory holidays](https://handbook.mattermost.com/operations/workplace/people/working-at-mattermost/paid-time-off#holidays)\) prior to release day.

### A. \(Code complete date of previous release\) Beginning of Release

Pre-work for the current release begins at the code complete date of the previous release. See "Code Complete" section below for details.

### B. \(T-minus 30 working days\) Judgment Day & Release Branch Cut

Day when Leads and PMs decide which major features are included in the release, and which are postponed. **Stabilization** period begins when all features for release have been committed. During this period, only **bugs** can be committed to the release branch. Non-bug pull requests are tagged for the next version. Exceptions can be made by the Release Manager during triage. Review the [Release Features & Bugs Quality Gate Guidelines](https://docs.google.com/document/d/1QxB_A1qkEJBKAvQpRa7JiSQLZhwg6HAEajNRNa7ldGg/edit)

1. Release Manager:
   * Post this checklist in [Release Checklist](https://community.mattermost.com/core/channels/release-checklist) channel
   * Begin daily triage of tickets with the team
     * Also triage tickets in the backlog
   * Prior to the cut to Self-Managed, the Release manager reviews new feature flags and provides a report to the PM/QA team for their review. Essentially a feature will be included in a Self-Managed release once the feature flag has been removed.
   * Confirm with PMs that each Enterprise feature is in the correct [pricing SKU](https://mattermost.com/pricing/)
   * Review any features that are currently in beta and confirm with PMs if there are any to be promoted
   * Review the Jira tickets remaining in the current release fix version and push those that won't make it to the next fix version
   * After mobile release branch is cut, ask dev to cut an RN build
   * Queue a list of MVP candidates in alphabetical order to the MVP Discussion channel [See example](https://community.mattermost.com/core/pl/3its7ifbw7dh58obpasdszf1mr)
   * Draft changelog in a WIP PR with updates for highlights, feature additions, known issues, compatibility updates for deprecated features, `config.json`, [database changes](https://github.com/mattermost/mattermost-server/blob/master/store/sqlstore/upgrade.go), [API changes](https://github.com/mattermost/mattermost-server/commits/master/model/client.go), [WebSocket event changes](https://github.com/mattermost/mattermost-server/blob/master/model/websocket_message.go#L13), and Go runtime version; [see example](https://docs.mattermost.com/install/self-managed-changelog.html)
     * Specify the release type with a link to the [Release Definitions doc](https://docs.mattermost.com/upgrade/release-definitions.html)
   * Review that [software requirements](https://docs.mattermost.com/install/requirements.html#software-requirements) and [server software versions](https://docs.mattermost.com/install/requirements.html#server-software) are up-to-date based on [these step-by-step guidelines](https://handbook.mattermost.com/operations/research-and-development/product/development-process/software-requirements)
   * Ask PMs and Dev Leads if there are any notable breaking changes or deprecated features in the release
     * Update [Upgrade Guide](https://docs.mattermost.com/administration/important-upgrade-notes.html) with any special notes for upgrading to the new version
     * If there are any breaking compatibility changes in the release, open an issue in the [GitLab Omnibus](https://gitlab.com/gitlab-org/omnibus-gitlab) to make sure GitLab is aware. Post a link to the issue in the `Release: Self-Managed` channel
   * Start posting a daily list of open and submitted bugs and PRs
   * Submit `NOTICE.txt` PRs for any new libraries added from dev, and ensure they are cherry-picked to feature release branch
   * Confirm that `NOTICE.txt` PRs, Translations PRs, database upgrade, and any needed pre-packaged plugins, backports, and recent regression fixes are included in the release
   * Create meta issue for release in GitHub \(see [example](https://github.com/mattermost/mattermost-server/issues/3702)\)
   * Post a reminder in the Localization channel about the due date for translations, similar to this [example](https://community.mattermost.com/core/pl/7wqx4zehotgu7efhmbz51mxfqa)
     * Follow that translations are prioritized at [https://translate.mattermost.com/projects/mattermost/](https://translate.mattermost.com/projects/mattermost/)
   * Prepare bullet points for release announcement and share for PMs to work on. [Refer to the process here](https://handbook.mattermost.com/operations/messaging-and-math/how-to-guides-for-m-and-m/how-to-create-release-announcements)
   * Ask PMs and Tech Writer to complete release documentation by T-9 deadline. [Example request](https://community.mattermost.com/core/pl/w4oobh4zpigsfbqskx5ix5jgxo)
   * Schedule a meeting with PMs and QAs to discuss upcoming features in the next feature release
2. Dev:
   * Cut release branches for server and mobile
     * Merge database upgrade before cutting the branch
     * Update [model/version.go](https://github.com/mattermost/mattermost-server/blob/master/model/version.go#L16)
     * Point CI servers to the release branch after cutting
     * Update [https://prev.test.mattermost.com](https://prev.test.mattermost.com) to the previous release version
       * Prioritize reviewing, updating, and merging of pull requests for current release until there are no more tickets in the [pull request queue](https://github.com/mattermost/mattermost-server/pulls) marked for the current release
       * After the cut-off, any PRs that include significant code changes require approval of the Release Manager before merging
3. QA:
   * Prioritize testing PRs and resolved tickets for this release
   * Ensure that new features are also properly tested on mobile apps
   * Prioritize updating test cases as needed in test management and automated tests

### C. \(T-minus 9 working days\) RC1 Cut and RC Testing Begins

1. Release Manager:
   * Post this checklist in Release Checklist channel
   * Verify all items in the last posted release checklist are complete
   * Post in the [Release: Self-Managed](https://community.mattermost.com/core/channels/release-discussion) channel the rough timing when the release candidate will be cut
   * Cut a Release Candidate [using this process](https://github.com/mattermost/internal-docs/blob/63dcb6d0ff5d20ab9310466065dc15799b12708c/site/content/infra/release-tasks.md) and check CI servers running on release branch
   * Generate a list of contributors for changelog
   * Confirm doc submission
   * Post list of tickets to be fixed to the `Release: Self-Managed` channel \([see example](https://community.mattermost.com/core/pl/65k77x3bnigw5f9ffohfxonnfy)\)
   * Update the GitHub meta issue:
     * Include a link to the changelog on the documentation branch
     * Update download links and testing server links to the latest RCs
   * After build is cut, tweet announcement that RC1 is ready \(see [example](https://community.mattermost.com/core/pl/tefx1ijyz7bs8mabuxmpq9f7pw)\)
   * Update [Open Source Components](https://docs.mattermost.com/administration/open-source-components.html) and [Release Lifecycle](https://docs.mattermost.com/administration/release-lifecycle.html) docs
   * Confirm changelog reflects any changes since it was merged \(including known issues and contributors from all repositories\)
     * Confirm translators have been added
     * Confirm Open Source Components changes have been added
   * Find [www-gitlab-com merge request](https://gitlab.com/gitlab-com/www-gitlab-com/merge_requests?scope=all&utf8=%E2%9C%93&state=opened&label_name%5B%5D=blog%20post&label_name%5B%5D=release) for latest GitLab release blog post and make request for adding GitLab Mattermost update \(see [example request](https://gitlab.com/gitlab-com/www-gitlab-com/merge_requests/2910#note_14096885), [example update](https://about.gitlab.com/2016/07/22/gitlab-8-10-released/#gitlab-mattermost-32)\). Post to `Release: Self-Managed` channel with link to request
   * Confirm the required URLs for the blog/release announcement were prepared
2. Logistics @hanna.park:
   * Mail out contributor and security researcher mugs
     * Space out the ordering of mugs over the next three weeks to prevent mistakes being made by the supplier \(e.g., If there are 12 contributors to order mugs for, place an order every 2nd or 3rd day over the next three weeks\)
   * Update [Team](https://developers.mattermost.com/contribute/team_contributions/) page with new contributors
   * Generate an E20 5000 seat test licence and email to Lindy for release testing
3. QA:
   * Confirm up to date with testing PRs and resolved tickets
   * Confirm up to date with test updates and known issues in release test management and automated tests
   * Assign release testing areas to team members
   * After RC1 is cut: Update test server invite links in Release Testing instructions
   * After RC1 is cut: Run automated regression tests
   * Post reminder in Release Announcements channel for any unfinished RC testing, at-mentioning tester\(s\)
     * Find QA or other teammates to help finish unfinished tests if needed
     * Verify all release tests are finished, bring any concerns to Triage/Release meeting
     * Go through test cycles and verify all issues and comments have been filed or updated in Jira as needed
4. Build:
   * Review all `TODO` notes, including one for uncommenting upgrade code
   * Confirm all PRs in [`/enterprise`](https://github.com/mattermost/enterprise/pulls) repo have been merged
   * Master is tagged and branched and `Release Candidate 1` is cut \(e.g. 3.5.0-RC1\) according to the Release Candidate Checklist in `mattermost/process`
   * Update version for each [Mattermost Helm chart](https://artifacthub.io/packages/search?page=1&ts_query_web=mattermost)
   * Make PRs for bug fixes to the release branch
   * Review PRs made from release branch and merge changes into the release branch as required
   * Run daily automated upgrade tests to avoid catching upgrade bugs late
5. PM:
   * Finish draft of blog post for mattermost.com and all art work \(screenshots, GIFs, and Twitter banners\) used for the blog post
     * Add links to [Admin guide](https://docs.mattermost.com/guides/administrator.html) in the release blog post where needed

### D. \(T-minus 5 working days\) Code Freeze

Day after which only **S1 regressions** should be fixed \(crashes, security vulnerabilities\) and no other code changes should be committed. Exceptions can be made by the Release Manager during triage on a case-by-case basis. Review the [Bug Severity Guidelines](https://handbook.mattermost.com/operations/research-and-development/product/development-process/new-bug-tickets/bug-severity-guidelines).

1. Release Manager:
   * Post this checklist in Release Checklist channel
   * Verify all items in the last posted release checklist are complete
   * Verify that the final translations PR for the release is submitted
   * Update **Known Issues** section with any significant issues that were found and not fixed for the final release
2. QA:
   * Verify all Jira tickets other than newly-filed bugs have been tested, verified, and closed
   * As bug fixes are merged and RCs are cut, verify fixes on new RCs, and post in Release Channel after testing
   * After all tickets are verified and closed, run smoke tests on webapp/server, desktop app, and RN apps as appropriate 
3. Docs:
   * Submit Changelog PR for team review
   * Submit any remaining documentation PRs for product updates in the release
   * Check that a redirect page has been set up in mattermost.com for any links added to the System Console
   * Submit documentation for [API changes](https://github.com/mattermost/mattermost-server/commits/master/model/client.go) and [WebSocket event changes](https://github.com/mattermost/mattermost-server/blob/master/model/websocket_message.go#L13) to API documentation
   * Confirm changes to `config.json` in compatibility section of changelog are written back to [settings documentation](http://docs.mattermost.com/administration/config-settings.html#configuration-settings)
   * Confirm all new diagnostics are documented in the telemetry docs \([https://docs.mattermost.com/administration/telemetry.html](https://docs.mattermost.com/administration/telemetry.html)\)

### E. \(T-minus 2 working days\) Release Build Cut

The final release is cut - RC cuts and bug fixes should be completed by this date. Only urgent and critical issues are considered for fixing.

1. Release Manager:
   * Post this checklist in Release Checklist channel
   * Verify all items in the last posted release checklist are complete
   * Work with a developer to submit GitLab MR [following this process](https://docs.mattermost.com/process/gitlab-process.html#merge-requests) and [test the upgrade](https://docs.google.com/document/d/1mbeu2XXwCpbz3qz7y_6yDIYBToyY2nW0NFZq9Gdei1E/edit#heading=h.ncq9ltn04isg) once the GitLab MR is merged and included in their RC
   * Close GitHub meta ticket for the release
   * Add the download links, SHA-256 hash, and GPG signature to the [version archive](https://docs.mattermost.com/administration/version-archive.html)
   * Merge changelog PR after review is complete
     * If there is a security fix, confirm the changelog recommends upgrade, with a note mentioning the security level and thanking the security researcher \(security process doc for example\)
   * Update the [Mattermost server download page](https://mattermost.com/download/) with the links to the Enterprise Edition and Team Edition sections
     * Test the download links before and after updating the page
   * Check security issues and confirm disclosure text
   * Update the [security mugs spreadsheet](https://docs.google.com/spreadsheets/d/18MVoUJ1pfvqhqEX7tfQ9pia8yVuac8UsnfKmnU_dTqk/edit#gid=0)
   * Check the security researcher was added to the [Responsible Disclosure Policy](https://mattermost.com/security-vulnerability-report/) page
   * Update [deprecated feature list](https://docs.mattermost.com/install/deprecated-features.html) in mattermost.com with new and scheduled deprecations
   * Draft [Mattermost Security Updates](https://mattermost.com/security-updates/), but do not post until 30 days after official release 
     * Add a placeholder text saying "Details on the security update will be posted here on X date, as per our Responsible Disclosure Policy"
2. QA:
   * Verify all PRs and tickets for the release have been tested/closed
   * Post QA approval in `Release: Self-Managed` channel and playbook channel for that release
3. Build:
   * Tags a new release \(e.g. 1.1.0\) and runs an official build which should be essentially identical to the last RC
   * Posts SHA key, md5 sum, and GPG signatures of the final build to `Release: Self-Managed` channel
   * Post in `Release: Self-Managed` with links to the Enterprise Edition and Team Edition sections
4. Dev:
   * Verify the hashes \(SHA-1, SHA-256, and md5\) and GPG signatures are correct for both Enterprise Edition and Team Edition
   * Test upgrade from previous version to current version, following the [Upgrade Guide](https://docs.mattermost.com/upgrade/upgrading-mattermost-server.html) with database upgrades on both MySQL and Postgres
   * Test upgrade from Team Edition to Enterprise Edition based on the [Upgrade Guide](https://docs.mattermost.com/upgrade/upgrading-mattermost-server.html)
   * Test fresh install of current version, following the [Install Guide](https://docs.mattermost.com/guides/administrator.html#installing-mattermost)
   * Review any changes made to install guides, and test if necessary
   * Ensure [Security Policies](https://handbook.mattermost.com/operations/operations/company-policies/security-policies) page has been updated
   * Update dependancies after release branch is cut in `mattermost-server`, `mattermost-webapp`, `desktop`, `mattermost-mobile`, and `mattermost-redux`
5. Logistics @hanna.park:
   * Order the release MVP winner's coaster
6. Docs:
   * Remind PMs and Tech Writer to finalize docs
   * Merge the docs release branch to master and verify all changes on docs.mattermost.com once the build is up
   * Submit a correction PR for any incorrect formatting or other errors missed during the initial review
7. Marketing:
   * Receive sign off on final version of MailChimp email blast and Twitter announcement and schedule for 08:00 PST on the date of marketing announcement
     * **Note:** If the release contains a security update, also draft a Mailchimp email blast for the [Security Bulletin mailing list](http://eepurl.com/cAl5Rv)
   * Finalize blog post for mattermost.com, test on mobile view, and set timer for 08:00 PST on the day of release

### F. \(T-minus 0 working days\) Release Day

1. Release Manager:
   * Post this checklist in Release Checklist channel
   * Verify all items in the last posted release checklist are complete
   * Update the server upgrade [in-product notice](https://github.com/mattermost/notices)
   * Schedule a release retrospective meeting, to be held within five days of the release
   * Prepare and post [release metrics](https://docs.google.com/spreadsheets/d/1Aoj4OTaWoyrKIcQNiHH1MVoRG51T20Y_0w2tg5oVw-M/edit#gid=825551144)
   * Finalize [release summary slide deck](https://docs.google.com/presentation/d/1DnfgP-yyZ8-sfhQC7rS9McbQQcmSPCQYLs62LNoIJuQ/edit#slide=id.g2f0aecc189_0_245) to prepare for posting for CSMs
   * Review and update [company roadmap](https://mattermost.com/roadmap/) with which major features made it into the release
     * Review with Head of Product prior to updating
     * Also update feature lists on [https://mattermost.com/pricing/](https://mattermost.com/pricing/) and [https://mattermost.com/product/](https://mattermost.com/product/) with relevant new features where needed
   * Update the Mattermost Wikipedia page with the latest version
   * Post the MVP winner announcement in the [Contributors channel](https://community.mattermost.com/core/channels/tickets)
     * Update [MVP page](https://developers.mattermost.com/contribute/mvp/) with the most valued professional of the release
   * Add new release fix versions in Jira for the next few releases
   * Post key dates for the next release in the `Release: Self-Managed` channel and remove links to RC candidates and testing spreadsheet from the header
     * Make sure that statutory holidays for Canada and US are accounted for in the release dates
   * Check for any [UserVoice](https://docs.google.com/spreadsheets/d/1nljd4cFh-9MXF4DxlUnC8b6bdqijkvi8KHquOmK8M6E/edit#gid=0) feature suggestions that were completed in the current release
     * Find the [release tweet](https://twitter.com/mattermosthq/status/854781715914555393) and insert a link to the tweet next to the feature that shipped with the release
   * Close the release in Jira both for webapp and mobile \([releases page](https://mattermost.atlassian.net/projects/MM?selectedItem=com.atlassian.jira.jira-projects-plugin%3Arelease-page)\)
   * Confirm that daily triage / release update meetings are scheduled.
   * Prepare tickets for the next release, with a corresponding vX.X prefix, and put the tickets in the appropriate sprints as follows:
     * The week RC is cut:
       * [RC Build Testing for core team](https://mattermost.atlassian.net/browse/PLT-2208)
     * The week RC is cut:
       * [Loadtest x.x release candidate compared to x.x release](https://mattermost.atlassian.net/browse/MM-12532)
     * The week RC is cut \(for GitLab dev owner\):
       * Test RC1 with the latest GitLab build during release testing cycle
     * Release week \(for dependencies owner\)
       * Upgrade dependencies for webapp, server, and Redux
     * Week after release \(for GitLab dev owner\)
       * [Submit GitLab Omnibus RC install of Mattermost](https://mattermost.atlassian.net/browse/MM-9872)
     * The week before code complete \(one for Apps and for Mobile\):
       * If an existing ESR is going out of support next month, update the in-app prompts \(mobile and desktop\) to start detecting for the new minimum supported ESR version
       * If a new ESR is released next month, update the prompts to recommend upgrading to that version instead of the older ESR
   * Confirm that [mattermost-docker](https://github.com/mattermost/mattermost-docker/releases) has been updated to the latest version \(contact the maintainer via direct message on community server if necessary\)
   * Contact owner of Yunohost community installer to update install version number. See [example](https://github.com/YunoHost-Apps/mattermost_ynh/pull/103)
   * Turn on CrazyEgg for blog post page
   * Confirm marketing has been posted \(mail announcement, tweets, blog posts\)
     * Post in the Announcements channel
   * Update @mattermost Twitter profile with the next release date
   * Prepare retweet of GitLab release tweet \([see example here](https://community.mattermost.com/core/pl/k7wchwj5mtrhucj6don96yx3sc)\)
2. Docs:
   * Create a new branch on docs for the next release - `vX.X-documentation`
     * Submit a PR for changelog against the `vX.X-documentation` branch and add a `Work in Progress` label for it
     * Submit a PR to change version number in `docs/source/conf.py` against the `vX.X-documentation` branch
3. Build:
   * Ensure [https://community.mattermost.com](https://community.mattermost.com) is on the most recently released version and that [https://prev.test.mattermost.com](https://prev.test.mattermost.com) is on the previous release version
   * Verify that the release tags were added to GitHub
4. QA:
   * Merge any updates made to Selenium tests during release testing
   * Update RN server URLs to Rainforest

### G. \(T-plus 30 days\) Update Mattermost Security Page

1. Release Manager:
   * Post [Mattermost Security Updates](https://mattermost.com/security-updates/) after reviewing with security lead
     * If a dot release is shipping with security fixes, do not post new details until T-plus 10 working days from the dot release ship date
