# Release Process

This document outlines the release process for the Mattermost desktop app.

Desktop App releases follow a fixed schedule of 4 releases per year. Releases ship quarterly by the 16th of March, June, September, and December of each year.

A dot release will be prepared sooner if [Electron](https://github.com/electron/electron/releases) releases a security update, or if other urgent bugs are found.

Please refer to [the desktop app release playbook](https://community.mattermost.com/playbooks/playbooks/h3a39biacpnuim7ufmwiuuoxfo/outline) for a most up-to-date checklist.

## Release timeline

Note: T-minus counts are measured in "working days" (weekdays other than major holidays concurrent in US and Canada) prior to release day.

**Schedule for Desktop App releases**:
 - Feature Complete deadline is approximately 1 month prior to the release day.
 - Cut release branch based off `master` and cut RC-1 (around T-14).
 - Code Freeze at T-5.
 - Cut Final build at T-2.
    - QA approval should be ready by T-2.
 - Release Day at T-0.
