# Incident Collaboration Release Process

This document outlines the Incident Collaboration release process for the Mattermost core team. Our release process draws from many best practice Agile, Scrum, and Software Development Lifecycle methodologies.

Every two weeks, the team runs through a playbook to cut a new release of the plugin, smoke test it, and add it to the marketplace. That gets pushed to cloud immediately \(via split.io\), and any self-managed customers who desire the upgrade may do so from the plugin marketplace.

## Release Timeline

Schedule for Incident Collaboration releases:

* Features and bug fixes are merged
* \(T-3\): Cut a Release Candidate
* \(T-2\): Smoketesting
* \(T-0\): Release Day

On the first Monday of each month, or the next business day, the Incident Collaboration team's Product Manager and Dev Lead choose what version of the plugin they will pre-package into that month's self-managed release. The deadline to merge the selected version into the self-managed release is the Code Freeze day. An additional round of testing is required to qualify before merging.

## Notes

* Critical bugs are flagged and fixed before releasing, with quick dot releases completed as needed.
* The team uses Incident Collaboration Playbook checklists for releases and for pre-packaging with self-managed.
  * Playbooks Team: [Plugin Release playbook](https://community.mattermost.com/core/com.mattermost.plugin-incident-management/playbooks/hzgiqpzsbinpujdnue9xa1kj4y) \(has limited access\)
  * Playbooks Team: [Feature Swimlane playbook](https://community.mattermost.com/core/com.mattermost.plugin-incident-management/playbooks/1gtdk5q57irzib67w6ocaatimy) \(has limited access\)

## Basic release tasks

* Track and triage bugs via Jira
* Add PR milestones for QA tracking
* Auto-generated release notes with changes, upgrade notes, minimum server version requirement, contributors, and known issues
* Update NOTICE.txt
* Update dependencies
* Testing and automated tests
* Marketing - Release announcements, tweets
* Feature documentation
* Release
  * GitHub release
  * Check minimum required server version \(if applicable\)
* Contributors
  * Swag
* Release dates communicated in Incident Response google calendar
* Release retrospective
* **TBD: Security updates communication**

