# Boards Release Process

This document outlines the Boards release process for the Mattermost core team. Our release process draws from many best practice Agile, Scrum, and Software Development Lifecycle methodologies.

## Release Timeline

Boards release schedule is outlined here: https://docs.google.com/spreadsheets/d/1nMrpSyR8PSEkHuQl_oJ-bAz1_qpEiGhgF4HdDX1Uf4Q/edit#gid=1279713913

The release that will be included in the next self-managed release pre-packaged version will generally be the latest Focalboard Personal Edition release from the prior month. The deadline to get the pre-packaged version to the self-managed release is by self-managed Code Freeze day. The pre-packaged version is tested a few days prior to self-managed Code Freeze day.

## Notes

* Critical bugs are flagged and fixed before releasing, with quick dot releases completed as needed.
* Documentation on filing a bug: https://handbook.mattermost.com/contributors/contributors/ways-to-contribute#report-a-boards-bug
* A playbook is used to run releases: https://community.mattermost.com/playbooks/playbooks/xycc3rjwd3n95n1e1yqxp9iira/preview
* Documentation on publishing a release: [https://docs.google.com/document/d/11uLGhYYNnsulL1oUAlfFyNcT3wgAiDJmCSvnNkuAbpA/edit\#heading=h.6kw7puo0cpnm](https://docs.google.com/document/d/11uLGhYYNnsulL1oUAlfFyNcT3wgAiDJmCSvnNkuAbpA/edit#heading=h.6kw7puo0cpnm) 
* Documentation on publicity process: [https://docs.google.com/document/d/1C1ke76Y-KV9k0buJsv57kqq5HFdR2BwnpkmVHmBCxuA/edit\#](https://docs.google.com/document/d/1C1ke76Y-KV9k0buJsv57kqq5HFdR2BwnpkmVHmBCxuA/edit#) 
* Feature flags are used to test features.
* Goal is to automate as many tests as possible and to integrate with the QA dashboard.

## Basic release tasks

* Track and triage bugs via GitHub; Boards for work items
* Add PR milestones for QA tracking
* Triage meetings to identify high priority bugs
* Update changelog with changes, upgrade notes, contributors, and known issues
* Update NOTICE.txt
* Update dependencies
* Translations monitoring
* List software requirements \(e.g. OS, browser\) and minimum server version requirements
* Testing + automated tests
* Marketing - Release announcements, tweets
* Feature documentation
* Release
  * App store release
  * GitHub release
  * Check minimum required server version \(if applicable\)
* Contributors
  * Swag
* **TBD:** Release dates - Communicate in google calendar and channel header
* Retrospectives
* **TBD:** Metrics - Quality metrics, e.g. number of bugs fixed, number of dot releases, etc.
* **TBD:** Security updates communication
