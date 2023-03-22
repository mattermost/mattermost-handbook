# Self-Hosted Release Process

Mattermost core team works on a monthly release process, with a new version shipping on the 16th of each month in [binary form](https://docs.mattermost.com/upgrade/upgrading-mattermost-server.html).

This document outlines the development process for the Mattermost core team, which draws from what we find works best for us from Agile, Scrum, and Software Development Lifecycle approaches. Please refer to [the Self-Managed Release Playbook](https://community.mattermost.com/playbooks/playbooks/t7s6wkmsfpf99xe6sxgricgd9e/outline) for a most up-to-date checklist.

## Release Timeline

Note: T-minus counts are measured in "working days" \(weekdays, Monday through Friday, excluding [the listed statutory holidays](https://handbook.mattermost.com/operations/workplace/people/working-at-mattermost/paid-time-off#holidays)\) prior to release day.

**Schedule for Self-managed releases**:
 - Feature Complete deadline is approximately 1 month prior to the release day.
    - When we merge master into the cloud branch for the last Cloud release of the month, this is the cut-off for new features included in the next self-managed release.
    - If a feature misses the cut-off, it doesn’t get added to the next self-managed release.
 - Cut release branch based off the last Cloud release of the month and cut RC-1 (around T-14).
 - Code Freeze at T-5.
    - Prepackaged plugins should be ready on or before this date.
 - Cut Final build at T-2.
    - QA approval should be ready by T-2.
 - Release Day at T-0.
