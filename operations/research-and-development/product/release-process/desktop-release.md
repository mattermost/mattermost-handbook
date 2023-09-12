# Release Process

This document outlines the release process for the Mattermost desktop app.

Desktop app releases follow a fixed schedule of 4 releases per year. Releases ship quarterly by the 16th of March, June, September, and December of each year.

A dot release will be prepared sooner if [Electron](https://github.com/electron/electron/releases) releases a security update, or if other urgent bugs are found.

Please refer to [the desktop app release playbook](https://community.mattermost.com/playbooks/playbooks/h3a39biacpnuim7ufmwiuuoxfo/outline) for the release checklist.

For the desktop app release build process, please refer to [this document](https://developers.mattermost.com/internal/desktop-release-process/).

## Release timeline

Note: T-minus counts are measured in "working days" (weekdays other than major holidays concurrent in US and Canada) prior to release day.

The Desktop app release schedule follows the cloud/self-hosted release schedule to align all release testing cycles.

**Schedule for Desktop App releases**:
 - Feature Complete deadline is approximately 1 month prior to the release day.
 - Cut release branch based off `master` and cut RC-1 (around T-24).
 - Code Freeze at T-10.
 - Cut Final build at T-8.
    - [QA approval](https://community.mattermost.com/playbooks/playbooks/h798dt39mpbymb8z5uoiuf4hdo/outline) should be ready by T-8.
 - Release Day at T-0.
