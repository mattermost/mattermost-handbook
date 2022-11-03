# Release Tips

**Bug bashes**

* Run a bug bash at least for major releases.
* Bug bashes can either be run asynchronously/individually or as a group.
* Use a playbook to run bug bashes - [example bug bash playbook](https://community.mattermost.com/playbooks/playbooks/raxoo6hua3gpdpthaqmpmdzptw/outline).
  * PMs can assign test assignments and testers under the "Testing areas" checklist item.
* Decide environments to test on - normally community-daily or rc.test.mattermost.com + include Mobile and Desktop app environments.
* Decide date(s) for the bug bash.
* Announce bug bash on the day when the bug bash starts.
* Invite community members to participate in the bug bash.
* Triage owner (normally Release Manager) - review reported issues to identify what to fix for the upcoming release and open/assign tickets to teams.

**Changelog checklist**

* Features
  * State benefits first.
  * Order features based on benefit for end users.
  * Include links to docs where appropriate.
* Bugs
  * Check/test if the issue was in previous server version.
* All sections
  * Check that all sections are written and formatted the same way as in previous changelogs.
* API/Websocket/Database
  * Work with Devs on this section.
* Next version
  * If the changelog mentions items regarding upcoming versions, move them to the bottom of the changelog.

**Ways to meet deadlines**

* Post a list of dates for next release at or soon after T-0 and ping all of the teams.
* For features and bugs, start pinging early enough before due dates and make public posts.
* When pinging people, provide a clear due date and give a reason for the due date \(e.g., Code Complete on Monday\).
* Ask if people need any help or have any questions.

**Translations**

* Monitor progress of translations at [https://translate.mattermost.com/](https://translate.mattermost.com/) and ping language maintainers a few days before due date if they're not getting to 100%.
* Ask DevOps to submit a new translations PR if a translation deadline extension is requested.
* Target date for final translations PR is T-5, but T-3 is acceptable.

**Ways that** [**features/bugs guidelines**](https://docs.google.com/document/d/1QxB_A1qkEJBKAvQpRa7JiSQLZhwg6HAEajNRNa7ldGg/edit) **are currently enforced**

* Features guidelines:
  * Start to ping people already at T-15 or earlier for feature PRs that are still open.
* Bugs guidelines:
  * Need to focus on fixing only S1 and S2 bugs after T-5 to avoid missing T-2 deadline for cutting the final.

**Ways to ensure features are tested for HA/Mobile/Scale**

* HA: Test server available.
* Scale: Via loadtests.

**Release marketing**

* Blog post:
  * Follow [guidelines](https://handbook.mattermost.com/operations/messaging-and-math/how-to-guides-for-m-and-m/how-to-create-release-announcements).
