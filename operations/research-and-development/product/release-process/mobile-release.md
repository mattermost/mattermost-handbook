# Mobile App Release Process

The Mattermost team works on a monthly mobile app release process, with a new version submitted to the iOS App Store and Google Play Store on the 16th of each month.

Please refer to [the Mobile Release Playbook](https://community.mattermost.com/playbooks/playbooks/yxb6yyckgbrebe8eiuzmb6w8co/outline) for the release checklist.

**Note: iOS App Store approval may take a few days after the 16th.**

## Release Timeline

Note: T-minus counts are measured in "working days" \(weekdays, Monday through Friday, excluding [the listed statutory holidays](https://handbook.mattermost.com/operations/workplace/people/working-at-mattermost/paid-time-off#holidays)\) prior to release day.

The Mobile app release schedule follows the cloud/self-hosted release schedule to align all release testing cycles.

**Schedule for Mobile App releases**:
 - Feature Complete at T-24
    - This is the Feature Complete deadline for the release.
    - Cut the release branch based off the `main` branch.
 - RC-1 cut at T-19
    - Cut RC builds based off the release branch for QA release testing. Release testing begins.
    - Note: More frequent RC builds may be requested by the QA team and the Release Manager as we get closer to the release date and as more regression fixes get merged.
 - Code Freeze at T-10
    - Release testing is completed.
    - [QA approval](https://community.mattermost.com/playbooks/playbooks/9znffdsm9p8ixpanycpnb1mwkh/outline) should be ready by T-10.
 - Release Day at T-0
