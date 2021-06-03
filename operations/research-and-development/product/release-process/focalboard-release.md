# Focalboard Release Process

This document outlines the Focalboard release process for the Mattermost core team. Our release process draws from many best practice Agile, Scrum, and Software Development Lifecycle methodologies.

## Release Timeline

Schedule for Focalboard releases:
 - Features and bug fixes are merged
 - (T-3): Cut a Release Candidate
 - (T-2): Smoketesting
 - (T-0): Release Day

On the first day of each month, the Focalboard team's Product Manager and Dev Lead choose which recent release they will include in the next self-managed release pre-packaged version. The deadline to get the pre-packaged version to the self-managed release is by self-managed Code Freeze day. The pre-packaged version is tested a few days prior to self-managed Code Freeze day.

## Notes

 - Incident Collaboration Playbook is used to run releases.
 - Documentation on publishing a release: https://docs.google.com/document/d/11uLGhYYNnsulL1oUAlfFyNcT3wgAiDJmCSvnNkuAbpA/edit#heading=h.6kw7puo0cpnm 
 - Documentation on publicity process: https://docs.google.com/document/d/1C1ke76Y-KV9k0buJsv57kqq5HFdR2BwnpkmVHmBCxuA/edit# 
 - Goal is to use feature flags for features. Focalboard itself is currently behind a feature flag and tagged as experimental in June 16th self-managed release.
 - Goal is to automate as many tests as possible and to integrate with the QA dashboard.

## Basic release tasks

 - Track and triage bugs via GitHub; Focalboard for work items
 - Add PR milestones for QA tracking
 - **Triage meetings? XXXX**
 - Update changelog with changes, upgrade notes, contributors, and known issues
 - Update NOTICE.txt
 - Update dependencies
 - Translations monitoring
 - List software requirements (e.g. OS, browser) and minimum server version requirements
 - Testing + automated tests
    - **Load tests? Upgrade tests? XXXX**
 - Marketing - Release announcements, tweets
    - **In-product notice? Wikipedia? Download page XXXX**
 - Feature documentation
 - Release
    - App store release
    - Github release
    - Check minimum required server version (if applicable)
 - Contributors
    - Swag
 - **Release dates - Communicate in google calendar and channel header XXXX**
 - **Retrospectives XXXX**
 - **Metrics - Quality metrics, e.g. number of bugs fixed, number of dot releases, etc. XXXX**
 - **Security updates communication XXXX**
