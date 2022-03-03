# Cloud Release Process

This document outlines the Cloud release process for the Mattermost core team. Our release process draws from many best practice Agile, Scrum, and Software Development Lifecycle methodologies.

Please refer to [the Cloud Release Playbook](https://community.mattermost.com/playbooks/playbooks/53b8oj79ofb6dmanmuchj1cdbo/preview) for a most up-to-date checklist.

## Release Timeline

Notes:

* All cut-off dates are based on 10am in San Francisco [\(Pacific Time](http://everytimezone.com/)\) on the day stated.
* T-minus counts are measured in "working days" \(weekdays other than major holidays concurrent in US and Canada\) prior to release day.

### A. \(T-minus 9 working days\) Merge master to the Cloud branch

1. Release Manager:
   * Ask Cloud SRE team to update the community-release server to the same version as the Mattermost Cloud test installations.
   * Confirm all Jira tickets are resolved for QA testing.
   * Notify QA that the test servers are ready for QA testing. Normally QA testing starts on the next day \(at T-8\).
     * Post a list of new feature flags and major features for QA and PMs, and confirm with PMs that all features are behind a feature flag.
   * Ask Tech Writer to work on docs.
   * Keep track of any regressions on master for fixing.
   * Add Cloud release dates to the Release Google Calendar.
   * Start working on the changelog \(both internal and external\).
   * Check whether any translation PRs, pre-packaged plugins, and `NOTICE.txt` PRs are needed.
2. Dev:
   * Merge latest `master` into the Cloud branch after Server team's review.

### B. \(T-minus 0 working days\) Release day

1. Release Manager:
   * Post in Announcements channel with a link to the changelog.
   * Confirm that the Cloud SRE team updated the community-release server to the new version.
   * Schedule a retrospective.
   * Confirm PMs are aware of upcoming Cloud release dates and feature complete dates.
   * Merge docs and the changelog PR.
   * Close the release in Jira.

