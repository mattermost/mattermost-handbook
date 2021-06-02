# Incident Collaboration Release Process

This document outlines the Incident Collaboration release process for the Mattermost core team. Our release process draws from many best practice Agile, Scrum, and Software Development Lifecycle methodologies.

Every two weeks, the team runs through a playbook to cut a new release of the plugin, smoke test it, and add it to the marketplace. That gets pushed to cloud immediately (via split.io), and any self-managed customers who desire the upgrade may do so from the plugin marketplace.

Weekly releases may be a future consideration, but not a plan yet. There is no big usage in Cloud yet.

## Release Timeline

Schedule for Incident Collaboration releases:
 - Features and bug fixes are merged
 - (T-3): Cut a Release Candidate
 - (T-2): Smoketesting
 - (T-0): Release Day

On the first day of each month, the Incident Collaboration team's Product Manager and Dev Lead choose which recent release they will include in the next self-managed release pre-packaged version.
The deadline to get the pre-packaged version to the self-managed release is by self-managed Code Freeze day. The pre-packaged version is tested a few days prior to self-managed Code Freeze day.

## Notes

 - Critical bugs are flagged and fixed asap before releasing, with quick dot releases completed as needed.
 - The team uses Incident Collaboration Playbook checklists for releases and for pre-packaging with self-managed.
 - Incident Collaboration is deployed as a plugin, so the team is free to ship as often as they want, and without even being tied to the cloud release cadence.
 - TBD: The team is entertaining the idea of deploying to -daily on a near daily basis, though haven't invested in the infrastructure there yet.
