# QA Workflow

Note: Specific teams may develop their own variations on this workflow. This is generally how QA works at Mattermost.

### Daily

1. PR reviews \(see below\)
2. Jira tickets \(see below\)
3. Investigate and reproduce potential issues from reports in channels
4. Submit bug tickets as issues arise
5. Help engage with contributor questions in channels

### Weekly

1. Participate in team triage/planning meetings
2. Participate in [QA Guild meeting](https://community.mattermost.com/core/channels/qa-weekly-meetings)
3. Consider giving a demo in QA meeting and/or R&D meeting
4. \(QA Platform\) Rainforest release testing and maintenance
5. \(QA Platform\) Cypress webapp release testing and maintenance
6. \(QA Platform\) Manual release testing and maintenance

### Monthly

1. SDET \(Software Development Engineer in Test, the test engineers in QA\) rotation to monitor nightly automated tests and investigate and update as needed \(see below\)
2. Oversee your team's release testing and QA-approve releases \(cadence may vary by team/product\)
3. \(QA Platform\) Detox mobile release testing and maintenance

### As needed

1. Develop test plans for new features, add test cases to Zephyr test management
2. Approve new features after manual testing passes
3. \(QA Platform\) Oversee testing infrastructure and server needs
4. Help tend to community campaigns such as test automation Hackathons and QA community feature testing
5. Add or update documentation as you find need or opportunity

## PR reviews

1. PR author adds `3: QA Review` label to every PR
2. PR author adds a specific QA person as a reviewer _after_ PM/UX and dev reviews are done
   * Exceptions can be made for general smoke testing or other agreed-upon scenarios when it makes sense for QA review to be done in parallel with other reviewers
   * QA review assignee defaults to the QA person on that team
3. Read through the PR and its associated Jira ticket to establish context
4. Create a test build if needed
   * Labels can be added to trigger test builds for webapp/server, mobile apps
   * Test server info auto-posts in a comment on the PR
   * Mobile test builds auto-post in [QA: Builds](https://community.mattermost.com/core/channels/qa-builds) channel; uninstall existing Mattermost app from your device, and install the test build from APK file or pList link
   * Desktop: Ask for a test build or new RC on the PR or request in the [Developers: Desktop App](https://community.mattermost.com/core/channels/desktop-app) channel 
5. Establish or verify test plan and scope if not already spelled out
   * Can use [Test Plan Template](https://docs.google.com/document/d/16w9jMWXRRjuBbkF923Qka02UQyjF5_QI9skNEBb4fQQ) as appropriate, especially for major features
   * Ensure test cases are added or updated in Zephyr test management
   * For most PRs/bug fixes, note test details in the PR and related JIRA ticket \(no separate document needed\)
6. Ask questions and report issues in comments on the PR, mentioning the PR author \(and the PM/another dev as needed\)
7. Request changes as part of the Review Changes flow in GitHub, which can make it easier to manage in your PR to-do list
8. Verify unit and E2E tests are present and provide adequate coverage
   * If needed, add comment mentioning the author to ask about adding tests
   * Important: Ensure that E2E tests contain the proper mapping key to connect with Zephyr test management
9. Note that some pre-approved scenarios such as many Server team PRs that don't require QA testing may use the label `QA Deferred` 
10. When complete, select **Review Changes**, add comment, and approve
11. Remove label `3: QA Review`
12. If other reviews are still open, add label `QA Review Done`
13. If yours was the last review \(commonly the case\), add label `4: Reviews Done`
    * You may be the one to merge the PR if you're the last reviewer; this varies by team
14. On the related Jira ticket, assign yourself as QA Assignee

## Verifying and closing resolved Jira tickets

1. [QA-Assigned to you, not-closed](https://mattermost.atlassian.net/issues/?filter=15192)
2. Handling various ticket resolutions
   * `Won't Fix`, `Won't Do`, `Invalid`: Leave in Resolved \(PMs go through these periodically\)
   * `Duplicate`: Ensure the duplicate ticket is linked in a comment and close as duplicate
   * `Done`: Test according to test steps / test plan as appropriate
3. May not need to re-test for self-managed release if already satisfactorily tested for previous Cloud release
4. Be sure to test across Web App, Mobile apps, and Desktop App
5. Ensure it is noted in the ticket and test case if any of the expected behavior or the bug itself was environment-specific \(e.g. Android-only, Safari-only, etc.\)
6. Ensure related Zephyr test cases are linked to the ticket for traceability \(can link to the test case from the ticket in the Zephyr section of the ticket\)
7. Update test cases in Zephyr as needed
8. Always leave a comment on the Zephyr test case explaining your changes
9. Add a link to the related ticket in the test step field, as it allows testers an easy way to see if it’s a known issue or perhaps a “Won’t Fix” situation.

   And triple-check that the test case shows the related ticket in Traceability

10. Issues found? Communicate with the dev Assignee and either reopen or file a new ticket as desired. Can at-mention the Assignee in a comment and/or in a channel to discuss what's best
11. Tested and all passed? Note testing results in a comment and close the ticket
12. Leaving open to re-test on other fix versions
    * If you test on Cloud and want to re-test when the next self-managed RC is cut, add label `done-cloud` and leave in `Resolved`
    * If a hotfix is being backported to additional versions, add `done-5.38` for example, as the fix is tested on each version
    * Also always leave a comment explaining what testing has been completed and what is left to test 

## UI test automation

1. [Help drive and write E2E tests for your team](https://developers.mattermost.com/contribute/webapp/end-to-end-tests/)
2. Happy path for new features and bug fixes should be written or updated by the dev writing the feature or fix
3. Help to review E2E submissions and to add tests for more in-depth test cases
4. Ensure test case keys from Zephyr test cases are included in E2E tests
5. Help maintain nightly automated tests
   * Monitored by SDET on weekly rotation
   * See [QA: UI Test Automation](https://community.mattermost.com/core/channels/ui-test-automation) channel and [QA: Test Automation Reports](https://community.mattermost.com/core/channels/qa-test-automation-reports) channel
   * Test failures can be routed to the appropriate team, but SDET rotation can help monitor and answer questions
   * Demote and promote nightly tests from and to production as needed
6. Help review and shepherd community contributions
   * [E2E help-wanted issues available for contributors](https://github.com/mattermost/mattermost-server/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+label%3A%22Up+For+Grabs%22+label%3A%22Area%2FE2E+Tests%22+)
7. [E2E overview](https://developers.mattermost.com/contribute/webapp/end-to-end-tests/)
