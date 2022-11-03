# Mobile App Release Process

The Mattermost Mobile Apps team works on a monthly release process, with a new version submitted to the iOS App Store and Google Play Store on the 16th of each month.

Please refer to [the Mobile Release Playbook](https://community.mattermost.com/playbooks/playbooks/yxb6yyckgbrebe8eiuzmb6w8co/outline) for a most up-to-date checklist.

**Note: iOS App Store approval may take a few days after the 16th.**

## Release Timeline

Notes:

* All cut-off dates are based on 10am \([San Francisco Time](https://everytimezone.com/)\) on the day stated.
* T-minus counts are measured in "working days" \(weekdays, Monday through Friday, excluding [the listed statutory holidays](https://handbook.mattermost.com/operations/workplace/people/working-at-mattermost/paid-time-off#holidays)\) prior to release day.

### A. \(T-minus 20 working days\) Cut-off for merging major features

No pull requests for major features should be **merged** to the current release after this date. In special cases, exceptions can be made by the Release Manager.

1. Release Manager:
   * Post this checklist in Release Checklist channel
   * Draft Changelog in a WIP PR with updates for compatibility notes, highlights, feature additions and bug fixes
   * Monitor and report any app crash reports in Testflight during the release cycle
   * Start posting a daily Zero Bug Balance query
   * Prepare a list of highlights to be included in the next Mattermost release announcement
2. PM:
   * Prioritize reviewing major features, ensuring any bugs and UX issues get fixed
3. Dev:
   * Prioritize reviewing, updating, and merging of pull requests for current release until there are no more tickets in the pull request queue marked for the current release
     * After the cut-off, any PRs that include significant code changes, require approval of the Release Manager and React Native PM before merging
4. Build:
   * Cut a beta build for QA testing

### B. \(T-minus 19 working days\) Feature Testing

1. QA:
   * Prioritize testing PRs and verifying resolved tickets for this release
   * Prioritize updating test cases as needed in test management and automated tests

### C. \(T-minus 15 working days\) Judgment Day

Day when PM decides which major features are included in the release, and which are postponed.

1. **\(Team\) Triage Meeting**:
   * Begin daily triage of tickets
2. Release Manager:
   * Post this checklist in Release Checklist channel
   * Verify all items in the last posted release checklist are complete
   * Update Changelog PR based on what's in/out of the release
   * Post a link to Release Discussion channel for query of remaining bugs in this release
3. PM:
   * Review the Jira tickets remaining in the current release fix version and push those that won't make it to the next fix version

### D. \(T-minus 9 working days\) Code Complete and Release Candidate Cut

**Stabilization** period begins when all features for release have been committed. During this period, only **bugs** can be committed to the release branch. Non-bug pull requests are tagged for next version. Exceptions can be made by the Release Manager during triage.

1. Release Manager:
   * Post this checklist in Release Checklist channel
   * Verify all items in the last posted release checklist are complete
2. Dev:
   * Prioritize reviewing, updating, and merging of pull requests for current release until there are no more tickets in the pull request queue marked for the current release
   * Check the minimum server version required and submit pull request to update in fastlane files
   * Create release branch for mattermost-mobile and mattermost-redux
   * Cut release candidate build
3. QA:
   * Confirm up to date with test case updates and known issues in test management and automated tests
   * After release candidate build is available: Run automated tests
   * Create QA manual test cycles as needed and begin manual testing
   * Bring concerns or issues found during testing to the Release Manager in-channel
4. Docs:
   * Submit any remaining documentation PRs for product updates in the release

### E. \(T-minus 8 working days\) Release Candidate Testing

1. Release Manager:
   * Post this checklist in Release Checklist channel
   * Verify all items in the last posted release checklist are complete
   * Post list of tickets to be fixed to the Release Discussion channel
   * Update Changelog for any new bug fixes
   * Check that the release candidate is available to beta testers
2. QA:
   * Create non-QA manual test cycle, assign testers, [kick off RC testing](https://docs.google.com/document/d/1kGvss1Mc9xfocvmJTYJZ0iXN09UtLKvzrAFMkUpFEtM)
   * As bug fixes are merged, verify fixes on new builds and post in relevant release channel\(s\) after testing
   * Post in the appropriate release channel\(s\) when release testing is complete, confirm list of any new items that remain to be tested
   * Go through test cycles and verify all issues and comments have been filed or updated in Jira as needed
3. Team:
   * Complete testing assignments and file any bugs found in Jira 
   * Daily triage of hotfix candidates and decide on whether and when to cut next RC or final
4. Dev:
   * Make pull requests for hotfixes to the release branch
   * Review PRs made to release branch and merge changes into the release branch
5. Build:
   * Verify with Release Manager before cutting any new RCs \(approved fixes should be merged\)
   * Push next RC to acceptance and announce in Native Mobile Apps channel
6. QA:     
   * When all testing is complete and no outstanding items remain, post approval for final cut in the relevant channel\(s\)

### F. \(T-minus 2 working days\) Release Build Cut

The final release is cut. If an urgent and important issue needs to be addressed between major releases, a bug fix release \(e.g., 1.1.1\) may be created.

1. Release Manager:
   * Post this checklist in Release Checklist channel
   * Verify all items in the last posted release checklist are complete
   * Submit Changelog PR for review
     * Merge Changelog PR after review is complete
2. Build: 
   * Tags the release and cuts the final build
   * Upload the `.ipa` and `.apk` files to GitHub
3. Marketing:
   * Finish draft of marketing images and send to marketing lead for review
4. Docs:
   * Finalize docs
     * If reviews are not complete, hold a 30-minute doc review meeting with PMs and anyone else who has changed or reviewed docs this release and wants to join
     * Submit a correction PR for any incorrect formatting or other errors missed during the initial review

### G. \(T-minus 0 working days\) Release Day and Build Submitted to App Stores

1. Release Manager:
   * Post this checklist in Release Checklist channel
   * Verify all items in the last posted release checklist are complete
   * Submit final build to Google Play Store and iTunes Connect
   * Confirm that minimum server version required is clear in update notes in the App stores and in GitHub README and Releases pages
   * Close the release in Jira
   * Schedule a release retrospective meeting, to be held within five days from the release 
   * Post key dates for the next release in the header of the Native Mobile Apps channel and remove links to RC candidates and testing spreadsheet
     * Make sure that statutory holidays for Canada and US are accounted for in the release dates
   * Check for any [UserVoice](https://docs.google.com/spreadsheets/d/1nljd4cFh-9MXF4DxlUnC8b6bdqijkvi8KHquOmK8M6E/edit#gid=0) feature suggestions that were completed in the current release
2. Build:
   * Merge the release branch back in to master
   * Review and update project dependencies as needed
   * Create release in GitHub

### H. \(T-plus X days\) Release Marketing

1. Marketing:
   * After the apps are approved and on the App Store \(number of days may vary\), send out release marketing
     * Update the app version on the [download page](https://mattermost.com/download/)
     * Send out a Twitter announcement
   * Double check that minimum server version required is clear in update notes in the App stores and in GitHub README and Releases pages

