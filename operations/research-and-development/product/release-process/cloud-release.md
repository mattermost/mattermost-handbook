# Cloud Release Process

This document outlines the Cloud release process for the Mattermost core team, which draws from what we find works best for us from Agile, Scrum, and Software Development Lifecycle approaches.

## Release Timeline

Notes:
- All cut-off dates are based on 10am ([San Francisco Time](http://everytimezone.com/)) on the day stated.
- T-minus counts are measured in "working days" (weekdays other than major holidays concurrent in US and Canada) prior to release day.

### A. (T-minus 7 working days) Fast-forward master to cloud branch

1. Release Manager:
    - Ask Cloud SRE team to update the community-release server to the same version as the cloud test installations.
    - Confirm all Jira tickets are resolved for QA testing.
    - Ask QA to do high priority testing.
    - Ask Tech Writer to work on docs.
    - Keep track of any regressions on master for fixing.
    - Add cloud release dates to the Release Google Calendar.
    - Start working on the changelog (both internal and external).
    - Check if any translation PRs, pre-packaged plugins, and notice.txt PRs needed.
2. Dev:
    - Fast-forward “cloud” branch to latest master.
 
### B. (T-minus 0 working days) Release day

1. Release Manager:
    - Post in Announcements channel with a link to the changelog.
    - Update community servers to the latest version.
    - Schedule a retrospective.
    - Confirm PMs are aware of upcoming cloud release dates and feature complete dates.
