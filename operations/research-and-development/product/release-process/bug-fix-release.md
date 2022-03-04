# Quality Release Process

## Release Timeline

Notes:
- All cut-off dates are based on 10am ([San Francisco Time](https://everytimezone.com/)) on the day stated.
- T-minus counts are measured in "working days" (weekdays, Monday through Friday, excluding [the listed statutory holidays](https://handbook.mattermost.com/operations/workplace/people/working-at-mattermost/paid-time-off#holidays)) prior to release day.

### A. (Code complete date of previous release) Beginning of Release

Pre-work for the current release begins at the code complete date of the previous release. See "Code Complete" section below for details.

### B. (T-minus 20 working days) Bug Fixing

1. **(Team) Daily Release Update Meeting (10:00am San Francisco time)**: 
    - Begin daily triage of tickets
        - Also start to triage tickets in the backlog
2. Release Manager:
    - Post this checklist in Release Checklist channel
    - Schedule a meeting with PMs and QAs to discuss upcoming features in the next feature release
    - After release branches are cut:
        - Go through and add "Cherry-pick Approved" labels to all release PRs and ask devs to cherry-pick already merged PRs
        - Ask dev to cut an RN build for QA testing
    - Draft Changelog in a WIP PR with updates for known issues, compatibility updates for deprecated features, config.json, [database changes](https://github.com/mattermost/mattermost-server/blob/master/store/sqlstore/upgrade.go), [API changes](https://github.com/mattermost/mattermost-server/commits/master/model/client.go), [WebSocket event changes](https://github.com/mattermost/mattermost-server/blob/master/model/websocket_message.go#L13), and Go runtime version; [see example](http://docs.mattermost.com/administration/changelog.html#compatibility)
      - Note the type of release and add a link to release doc that defines the type (https://docs.mattermost.com/administration/release-definitions.html)
    - Review that [software requirements](https://docs.mattermost.com/install/requirements.html#software-requirements) are up-to-date based on [these step-by-step guidelines](https://handbook.mattermost.com/operations/research-and-development/product/development-process/software-requirements)
    - Post a reminder to devs in the Release Discussion channel of the the code complete date with a list of open bugs and PRs [see example](https://community.mattermost.com/core/pl/coggyys9atg7fqyam81q3gkmoo)
    - Post a reminder in the French Localization channel about the due date for translations, similar to this [example](https://community.mattermost.com/core/pl/7wqx4zehotgu7efhmbz51mxfqa). Follow that translations are prioritized at https://translate.mattermost.com/projects/mattermost/
3. Dev:
    - Prioritize reviewing, updating, and merging of pull requests for current release until there are no more tickets in the pull request queue marked for the current release
      - After the cut-off, any PRs that include significant code changes, require approval of the release manager before merging
    
### C. (T-minus 19 working days) Release Bug Testing

1. QA:
    - Prioritize testing PRs and resolved tickets for this release
    - Ensure that all bugs are also properly tested on mobile apps
    - Prioritize updating release tests in test management and automated tests

### D. (T-minus 15 working days) Judgment Day

1. **(Team) Judgment Day Meeting (10:00am San Francisco time)**: 
    - Continue triaging tickets
    - Discuss worst bug currently on the release branch
2. Release Manager:
    - Post this checklist in Release Checklist channel
    - Verify all items in the last posted release checklist are complete
    - Queue a list of MVP candidates in alphabetical order to the MVP Discussion channel [See example](https://community.mattermost.com/core/pl/iau7cw7wzfdxze9ea7jr4bu3ay)
    - Create meta issue for release in GitHub (see [example](https://github.com/mattermost/mattermost-server/issues/3702))
    - Confirm date of marketing announcement for the release date
      - If release day falls on a Friday, the blog post goes out on the Friday and the emailed newsletter goes out the following Tuesday
    - Post a reminder to devs in the Release Discussion channel of the the code complete date with a list of open bugs and PRs [see example](https://community.mattermost.com/core/pl/coggyys9atg7fqyam81q3gkmoo)
    - Ask PMs and dev leads if there are any notable breaking changes or deprecated features in the release
      - Update [Upgrade Guide](https://docs.mattermost.com/upgrade/important-upgrade-notes.html) with any special notes for upgrading to the new version
    - Ask PMs and Tech Writer to complete release documentation by T-9 deadline. [Example request](https://community.mattermost.com/core/pl/w4oobh4zpigsfbqskx5ix5jgxo)
    - Prepare bullet points for release announcement and share for PMs to work on. [Refer to the process here](https://handbook.mattermost.com/operations/messaging-and-math/how-to-guides-for-m-and-m/how-to-create-release-announcements)
3. PM:
    - Finalize roadmap for next release, and identify planned marketing bullet points
    
### E. (T-minus 12 working days) Code Complete

Review the [Release Features & Bug Guidelines](https://docs.google.com/document/d/1QxB_A1qkEJBKAvQpRa7JiSQLZhwg6HAEajNRNa7ldGg/edit)

1. **(Team) Code Complete Meeting (10:00am San Francisco time)**:
    - Last check of tickets that need to be merged before RC1
2. Release Manager:
    - Post this checklist in Release Checklist channel
    - Verify all items in the last posted release checklist are complete
    - Review the Jira tickets remaining in the current release fix version and push those that won't make it to the next fix version
    - Submit `NOTICE.txt` PRs for any new libraries added from dev, and ensure they are cherry-picked to quality release branch
    - If there are any breaking compatibility changes in the release, open an issue in the [GitLab Omnibus](https://gitlab.com/gitlab-org/omnibus-gitlab) to make sure GitLab is aware. Post a link to the issue in the Release Discussion channel
    - Start drafting [a release summary slide deck](https://docs.google.com/presentation/d/1HndB1oe8-JabPseP3H-4wZtP0SqOU0IKjQpMoqfnSo0/edit#slide=id.p2) for MTL and CSMs for the next release
3. Dev:
    - Prioritize reviewing, updating, and merging of pull requests for current release until there are no more tickets in the pull request queue marked for the current release
4. QA:
    - Identify any new teammates who will be joining release testing, send them an intro to the testing process and timeframe, and send them the [hardware/software survey](https://drive.google.com/open?id=1IUiNO2S5fgWVn-Y_cyouxheukqKyGQC0_2UX64Ejwk8)
    - Set up DM/GM channels in preparation for testing auto-closing after 7 days

### F. (T-minus 11 working days) Release Candidate Cut

1. Release Manager:
    - Post this checklist in Release Checklist channel
    - Verify all items in the last posted release checklist are complete
    - Generate a list of contributors for Changelog
    - Ask martin.kraft to provide a list of Database changes, API changes, WebSocket event changes, and config.json setting changes for Changelog. [See example request](https://github.com/mattermost/docs/pull/3398#issuecomment-593411501)
2. Logistics @hanna.park:
    - Mail out contributor and security researcher mugs
      - Space out the ordering of mugs over the next three weeks to prevent mistakes being made by the supplier (e.g., If there are 12 contributors to order mugs for, place an order every 2nd or 3rd day over the next three weeks)
    - Update [Team](https://developers.mattermost.com/contribute/team_contributions/) page with new contributors
3. QA:
    - Confirm up to date with testing PRs and resolved tickets
    - Confirm up to date with test updates and known issues in release test management and automated tests
    - Assign release testing areas to team members
    - After RC1 is cut: Update test server invite links in Release Testing instructions
    - After RC1 is cut: Run automated regression tests
4. Build:
    - Review all `TODO` notes, including one for uncommenting upgrade code
    - Confirm all PRs in [`/enterprise`](https://github.com/mattermost/enterprise/pulls) repo have been merged
    - Update Redux before each RC and Final build
    - Update package version in [Mattermost DockerFile](https://github.com/mattermost/mattermost-server/blob/master/build/Dockerfile#L7)
    - Master is tagged and branched and `Release Candidate 1` is cut (e.g., 3.5.0-RC1) according to the Release Candidate Checklist in ``mattermost/process``
    - After branching, the database version in `sql_upgrade.go` on master is set to the next scheduled release version (e.g., 3.6.0)
    - Update version for each [Mattermost Helm chart](https://hub.helm.sh/charts/mattermost)

### G. (T-minus 10 working days) Release Candidate Testing

1. **(Team) Daily Release Update Meeting**
    - Triage Jira tickets
    - Decide when to cut next RC
2. Release Manager:
    - Post this checklist in Release Checklist channel
    - Verify all items in the last posted release checklist are complete
    - Update the GitHub meta issue:
       - Include a link to the Changelog on the documentation branch
       - Update download links and testing server links to the latest RCs
    - After build is cut, tweet announcement that RC1 is ready (see [example](https://community.mattermost.com/core/pl/tefx1ijyz7bs8mabuxmpq9f7pw))
    - Post list of tickets to be fixed to the Release Discussion channel ([see example](https://community.mattermost.com/core/pl/65k77x3bnigw5f9ffohfxonnfy))
3. QA:
    - Update Release Discussion header with links to RC instances and testing spreadsheet ([template](https://docs.google.com/document/d/1UvTsvwZXmEL9QPjxmjoIkR2AcwGtOjql8cYRfk2N8eA/edit#bookmark=id.ghe4vz9zd1v))
    - Post release testing instructions to Release Discussion channel ([template](https://docs.google.com/document/d/1UvTsvwZXmEL9QPjxmjoIkR2AcwGtOjql8cYRfk2N8eA/edit#bookmark=id.u28aar2hx7hg))
    - Post reminders in Announcements channel ([template](https://docs.google.com/document/d/1UvTsvwZXmEL9QPjxmjoIkR2AcwGtOjql8cYRfk2N8eA/edit#bookmark=id.pirw51cwsja5)) and Customer Support channel ([template](https://docs.google.com/document/d/1UvTsvwZXmEL9QPjxmjoIkR2AcwGtOjql8cYRfk2N8eA/edit#bookmark=id.ke0fh13gidni))
    - DM reminders if needed to team members who are not QA or devs, or who are new to release testing
4. Logistics @hanna.park:
    - Generate an E20 5000 seat test licence and email to Lindy for release testing
5. Dev:
    - Make PRs for bug fixes to the release branch
    - Review PRs made from release branch and cherry-pick changes into the release branch
    - Run daily automated upgrade tests to avoid catching upgrade bugs late
6. PM:
    - Finish draft of blog post for mattermost.com and all art work (screenshots and GIFs) used for the blog post
        - Upgrade should be recommended if there are security fixes in this version, with a note thanking the security researcher

### H. (T-minus 9 working days) Release Candidate Testing Finished

1. **(Team) Daily Release Update Meeting**
    - Confirm testing assigned in the Release Testing spreadsheet is complete 
    - Continue to triage Jira tickets
2. Release Manager:
    - Post this checklist in Release Checklist channel
    - Verify all items in the last posted release checklist are complete
    - Update https://docs.mattermost.com/administration/open-source-components.html
    - Confirm Changelog reflects any changes since it was merged (including known issues and contributors from all repositories)
      - Verify that translators were added
      - Verify that Open Source Components changes were added
      - Update **Known Issues** section with any significant issues that were found and not fixed for the final release
    - Find [www-gitlab-com merge request](https://gitlab.com/gitlab-com/www-gitlab-com/merge_requests?scope=all&utf8=%E2%9C%93&state=opened&label_name%5B%5D=blog%20post&label_name%5B%5D=release) for latest GitLab release blog post and make request for adding GitLab Mattermost update (see [example request](https://gitlab.com/gitlab-com/www-gitlab-com/merge_requests/2910#note_14096885), [example update](https://about.gitlab.com/2016/07/22/gitlab-8-10-released/#gitlab-mattermost-32)). Post to Release Discussion channel with link to request.
    - Cut next Release Candidate [using this process](https://github.com/mattermost/internal-docs/blob/63dcb6d0ff5d20ab9310466065dc15799b12708c/site/content/infra/release-tasks.md) and check CI servers running on release branch
    - Confirm doc submission and confirm the required URLs for the blog/release announcement where prepared
4. QA:
    - Midday: Post reminders about testing, at-mentioning team members whose tests are not yet complete
    - Find QA or other teammates to help finish unfinished tests if needed
    - End of day or next morning: Verify all release tests are finished, bring any concerns to Triage/Release meeting
    - Go through all tabs of testing spreadsheet and verify all comments and questions have been filed in Jira as needed
    
### I. (T-minus 5 working days) Code Freeze
Day after which only **S1 regressions** should be fixed (crashes, security vulnerabilities) and no other code changes should be committed. Exceptions can be made by the Release Manager during triage on a case-by-case basis. Review the [Bug Severity Guidelines](https://handbook.mattermost.com/operations/research-and-development/product/development-process/new-bug-tickets/bug-severity-guidelines).

1. **(Team) Daily Release Update Meeting**
    - Continue to triage Jira tickets
    - If no blocking issues are found, PM, Dev, and QA sign off on the release and begin final smoke tests
2. Release Manager:
    - Post this checklist in Release Checklist channel
    - Verify all items in the last posted release checklist are complete
    - Verify that the final translations PR for the release is submitted
    - Update **Known Issues** section with any significant issues that were found and not fixed for the final release
3. QA:
    - Verify all Jira tickets other than newly-filed bugs have been tested, verified, and closed
    - As bug fixes are merged and RCs are cut, verify fixes on new RCs, and post in Release Channel after testing
    - After all tickets are verified and closed, run smoke tests on webapp/server, desktop app, and RN apps as appropriate
5. Docs:
    - Submit Changelog PR for team review
    - Submit any remaining documentation PRs for product updates in the release
    - Check that a redirect page has been set up in mattermost.com for any links added to the System Console
    - Submit documentation for [API changes](https://github.com/mattermost/mattermost-server/commits/master/model/client.go) and [WebSocket event changes](https://github.com/mattermost/mattermost-server/blob/master/model/websocket_message.go#L13) to  API documentation
    - Confirm changes to `config.json` in compatibility section of Changelog are written back to [settings documentation](https://docs.mattermost.com/configure/configuration-settings.html)
    - Confirm all new diagnostics are documented in the telemetry docs (https://docs.mattermost.com/administration/telemetry.html)

### J. (T-minus 2 working days) Release Build Cut

The final release is cut - RC cuts and bug fixes should be completed by this date. Only urgent and critical issues are considered for fixing.

1. Release Manager:
    - Post this checklist in Release Checklist channel
    - Verify all items in the last posted release checklist are complete
    - Work with a developer to submit GitLab MR [following this process](https://docs.mattermost.com/process/gitlab-process.html#merge-requests) and [test the upgrade](https://docs.google.com/document/d/1mbeu2XXwCpbz3qz7y_6yDIYBToyY2nW0NFZq9Gdei1E/edit#heading=h.ncq9ltn04isg) once the GitLab MR is merged and included in their RC.
    - Close GitHub meta ticket for the release
    - Add the download links and SHA-256 hash [upgrade guide](http://docs.mattermost.com/administration/upgrade.html#version-archive)
    - Merge Changelog PR after review is complete
      - If there is a security fix, confirm the Changelog recommends upgrade, with a note mentioning the security level and thanking the security researcher (security process doc for example)
    - Update the [Mattermost server download page](https://mattermost.com/download/) with the links to the EE and TE bits
      - Test the download links before and after updating the page
    - Check security tickets and confirm disclosure text
    - Update the [security mugs spreadsheet](https://docs.google.com/spreadsheets/d/18MVoUJ1pfvqhqEX7tfQ9pia8yVuac8UsnfKmnU_dTqk/edit#gid=0)
    - Check the security researcher was added to the [Responsible Disclosure Policy](https://mattermost.com/security-vulnerability-report/) page
    - Confirm link to security updates appears in blog post if there are security updates in this release, with a note thanking the security researcher
    - Update [deprecated feature list](https://docs.mattermost.com/install/deprecated-features/) with new and scheduled deprecations
    - Draft [Mattermost Security Updates](https://mattermost.com/security-updates/), but do not post until 30 days after official release.
      - Add a placeholder text saying "Details on the security update will be posted here on X date, as per our Responsible Disclosure Policy"
2. QA:
    - Verify all PRs and tickets for the release have been tested/closed
    - Verify smoke tests on webapp/server, desktop app, and RN apps all passed
    - Post QA approval in Release Discussion channel
3. Build:
    - Update Redux before each RC and Final build
    - Tags a new release (e.g., 1.1.0) and runs an official build which should be essentially identical to the last RC
    - Posts SHA key, md5 sum, and GPG signatures of the final build to release channel
    - Post in Release Discussion with links to the Enterprise Edition and Team Edition sections
4. Dev:
    - Verify the hashes (SHA-1, SHA-256, and md5) and GPG signatures are correct for both Enterprise Edition and Team Edition.
    - Test upgrade from previous version to current version, following the [Upgrade Guide](https://docs.mattermost.com/upgrade/upgrading-mattermost-server.html) with database upgrades on both MySQL and Postgres
    - Test upgrade from Team Edition to Enterprise edition based on the [Upgrade Guide](https://docs.mattermost.com/upgrade/upgrading-mattermost-server.html)
    - Test fresh install of current version, following the [Install Guide](https://docs.mattermost.com/guides/deployment.html)
    - Review any changes made to install guides, and test if necessary
    - Ensure [Security Policies](https://handbook.mattermost.com/operations/operations/company-policies/security-policies) page has been updated
    - Update dependancies after release branch is cut in `mattermost-server`, `mattermost-webapp`, `desktop`, `mattermost-mobile`, and `mattermost-redux`
5. Logistics @hanna.park:
    - Order the release MVP winner's coaster
6. Docs:
    - Finalize docs
      - If reviews are not complete, hold a 30 minute doc review meeting with PMs and anyone else who has changed or reviewed docs this release and wants to join
      - Merge the docs release branch to master and verify all changes on docs.mattermost.com once the build is up
      - Submit a correction PR for any incorrect formatting or other errors missed during the initial review
7. Marketing:
    - Receive sign off on final version of MailChimp email blast and Twitter announcement and schedule for 08:00 PST on the date of marketing announcement
      - **Note:** If the release contains a security update, also draft a Mailchimp email blast for the [Security Bulletin mailing list](https://eepurl.com/cAl5Rv)
    - Finalize blog post for mattermost.com, test on mobile view, and set timer for 08:00 PST on the day of release
    - Add links to [Deployment guide](https://docs.mattermost.com/guides/deployment.html) in the release blog post where needed

### K. (T-minus 0 working days) Release Day

1. Release Manager:
    - Post this checklist in Release Checklist channel
    - Verify all items in the last posted release checklist are complete
    - Update the server upgrade [in-product notice](https://github.com/mattermost/notices)
    - Schedule a release retrospective meeting, to be held within five days of the release
    - Update Integrations Directory on the [Mattermost Apps and Integrations](https://integrations.mattermost.com/) page
    - Prepare and post [release metrics](https://docs.google.com/spreadsheets/d/1Aoj4OTaWoyrKIcQNiHH1MVoRG51T20Y_0w2tg5oVw-M/edit#gid=825551144)
    - Update [company roadmap](https://mattermost.com/roadmap/)
    - Post an MVP winner announcement in the [Contributors channel](https://community.mattermost.com/core/channels/tickets)
      - Update [MVP page](https://developers.mattermost.com/contribute/mvp/) with the most valued professional of the release
    - Add new release fix versions in Jira for the next few releases
    - Post key dates for the next release in the Release Discussion channel and remove links to RC candidates and testing spreadsheet from the header
        - Make sure that statutory holidays for Canada and US are accounted for in the release dates
    - Close the release in Jira both for webapp and mobile ([releases page](https://mattermost.atlassian.net/projects/MM?selectedItem=com.atlassian.jira.jira-projects-plugin%3Arelease-page))
    - For the next release, create the following team meetings. If they conflict with existing meetings, check with meeting owner to reschedule or reschedule the release meeting
      - Bug Bash Meeting on the week after Code Complete at 10:00am San Francisco time
      - Release Triage and Update Meeting each weekday starting at T-15 and ending at T-2 at 9:30am San Francisco time for PM, QA and release dev.
    - Prepare tickets for the next release, with a corresponding vX.X prefix, and put the tickets in the appropriate sprints as follows:
        - The week RC is cut:
            - [RC Build Testing for core team](https://mattermost.atlassian.net/browse/PLT-2208)
        - The week RC is cut:
            - [Loadtest x.x release candidate compared to x.x release](https://mattermost.atlassian.net/browse/MM-12532)
        - The week RC is cut (for GitLab dev owner):
            - Test RC1 with the latest GitLab build during release testing cycle
        - Release week (for dependancies owner)
            - Upgrade dependancies for webapp, server, and Redux
        - Week after release (for GitLab dev owner)
            - [Submit GitLab Omnibus RC install of Mattermost](https://mattermost.atlassian.net/browse/MM-9872)
        - The week before code complete:
            - [Add telemetry for new configuration settings in the release](https://mattermost.atlassian.net/browse/MM-24483)
         - The week before code complete (one for Apps and for Mobile):
            - If an existing ESR is going out of support next month, update the in-app prompts (mobile and desktop) to start detecting for the new minimum supported ESR version
            - If a new ESR is released next month, update the prompts to recommend upgrading to that version instead of the older ESR
    - Confirm that [mattermost-docker](https://github.com/mattermost/mattermost-docker/releases) has been updated to the latest version (contact the maintainer via direct message on community server if necessary)
    - Contact owners of [community installers](https://www.mattermost.org/installation/) or submit PRs to update install version number
      - For Chef Cookbook, open a new issue to announce the new release. See [example](https://github.com/ist-dsi/mattermost-cookbook/issues/22).
      - For Yunohost, open a new pull request to update the version. See [example](https://github.com/YunoHost-Apps/mattermost_ynh/pull/103).
    - Turn on CrazyEgg for blog post page
    - Confirm marketing has been posted (animated GIFs, screenshots, mail announcement, tweets, blog posts)
    - Update @mattermosthq Twitter profile with the next release date
    - Prepare retweet of GitLab release tweet ([see example here](https://community.mattermost.com/core/pl/k7wchwj5mtrhucj6don96yx3sc))
2. Docs:
    - Create a new branch on docs for the next release - `vX.X-documentation`
        - Submit a PR for changelog against the `vX.X-documentation` branch and add a `Work in Progress` label for it
        - Submit a PR to change version number in `docs/source/conf.py` against the `vX.X-documentation` branch
3. Build:
    - Cut release branches for the next feature release
        - Ensure `community-release` server is on the feature release branch
    - Put CI servers and translation server back onto master, and post in Private Developers channel once done
    - Ensure https://community.mattermost.com is on the most recently released version and that https://prev.test.mattermost.com is on the most recently released bug fix release
4. QA:
    - Merge any updates made to Selenium tests during release testing
    - Update RN server URLs to Rainforest

### L. (T-plus 30 days) Update Mattermost Security Page

1. Release Manager:
    - Post [Mattermost Security Updates](https://mattermost.com/security-updates/) after reviewing with security lead
      - If a dot release is shipping with security fixes, do not post new details until T-plus 10 working days from the dot release ship date
