# Focalboard Release Process

This document outlines the Focalboard release process for the Mattermost core team. Our release process draws from many best practice Agile, Scrum, and Software Development Lifecycle methodologies.

## Release Timeline

Focalboard release schedule for July and August is outlined here: https://docs.google.com/spreadsheets/d/1nMrpSyR8PSEkHuQl_oJ-bAz1_qpEiGhgF4HdDX1Uf4Q/edit#gid=0.

The release that will be included in the next self-managed release pre-packaged version will generally be the latest Focalboard Personal Edition release from the prior month. The deadline to get the pre-packaged version to the self-managed release is by self-managed Code Freeze day. The pre-packaged version is tested a few days prior to self-managed Code Freeze day.

## Notes

 - **TBD:** Critical bugs are flagged and fixed before releasing, with quick dot releases completed as needed.
 - **TBD:** Incident Collaboration Playbook is used to run releases.
 - Documentation on publishing a release: https://docs.google.com/document/d/11uLGhYYNnsulL1oUAlfFyNcT3wgAiDJmCSvnNkuAbpA/edit#heading=h.6kw7puo0cpnm 
 - Documentation on publicity process: https://docs.google.com/document/d/1C1ke76Y-KV9k0buJsv57kqq5HFdR2BwnpkmVHmBCxuA/edit# 
 - Goal is to use feature flags for features. Focalboard itself is currently behind a feature flag and tagged as experimental in June 16th self-managed release.
 - Goal is to automate as many tests as possible and to integrate with the QA dashboard.

## Basic release tasks

 - Track and triage bugs via GitHub; Focalboard for work items
 - Add PR milestones for QA tracking
 - **TBD:** Triage meetings and process to identify high priority bugs
 - Update changelog with changes, upgrade notes, contributors, and known issues
 - Update NOTICE.txt
 - Update dependencies
 - Translations monitoring
 - List software requirements (e.g. OS, browser) and minimum server version requirements
 - Testing + automated tests
 - Marketing - Release announcements, tweets
    - **TBD:** In-product notice, Wikipedia, download page**
 - Feature documentation
 - Release
    - App store release
    - GitHub release
    - Check minimum required server version (if applicable)
 - Contributors
    - Swag
 - **TBD:** Release dates - Communicate in google calendar and channel header
 - **TBD:** Retrospectives
 - **TBD:** Metrics - Quality metrics, e.g. number of bugs fixed, number of dot releases, etc.
 - **TBD:** Security updates communication
