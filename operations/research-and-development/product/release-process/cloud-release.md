# Cloud Release Process

## Release Timeline

Notes:
- All cut-off dates are based on 10am ([San Francisco Time](http://everytimezone.com/)) on the day stated.
- T-minus counts are measured in "working days" (weekdays other than major holidays concurrent in US and Canada) prior to release day.

### A. (T-minus 7 working days) Fast-forward master to cloud branch

1. Release Manager:
 - Ask Cloud SRE team to update the community-release server to the same version as the cloud test installations.
 - Ask QA to do high priority testing.
 - Ask Tech Writer to work on docs.
 - Tickets with a cloud fix version (regression bug fixes cherry-picked to “cloud” branch) also should be tracked for testing.
 - Keep track of any regressions on master for fixing.
 - Add cloud release dates to the google calendar.
 - Start working on changelog.
 - Check if any translation PRs, pre-packaged plugins, and notice.txt PRs needed.
2. Dev:
 - Fast-forward “cloud” branch to latest master.
 
### B. (T-minus 0 working days) Release day

1. Release Manager:
 - Post changelog.
 - Update community servers to latest version.
 - Post in Announcements.
 - Retrospectives
 - Confirm PMs are aware of dates
