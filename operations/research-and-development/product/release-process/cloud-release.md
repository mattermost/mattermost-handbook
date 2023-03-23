# Cloud Release Process

This document outlines the Cloud release process for the Mattermost core team. Our release process draws from many best practice Agile, Scrum, and Software Development Lifecycle methodologies.

Please refer to [the Cloud Release Playbook](https://community.mattermost.com/playbooks/playbooks/53b8oj79ofb6dmanmuchj1cdbo/outline) for a most up-to-date checklist.

## Release Timeline

Note: T-minus counts are measured in "working days" \(weekdays other than major holidays concurrent in US and Canada\) prior to release day.

 - T-14 (Thursday): 
    - Merge master into the cloud branch and update cloud test servers for the next release, including Rainforest RFQA-Cloud servers.
 - T-14 to T-3: 
    - Run Rainforest release test run groups, Cypress automated tests and product high level release smoke tests (i.e. Boards, Calls, Channels, Integration Frameworks, Playbooks and Suite Users). Close or label tickets for the release. Test failure reviews and bug fixing.
 - T-3 (Monday)
    - Each QA signs off as appropriate, using the [QA Approval playbook](https://community.mattermost.com/playbooks/playbooks/qeay15ou6frsmnu6tpmup9mxbc) run for that release.
    - QA approval should be given by 5pm Eastern on Monday so that the release rollout can be started early Tuesday morning. 
    - If QA approval is not ready by EOD Monday due to a testing delay or due to a last minute high priority bug fix, then we miss the release train.
    - If the release train was missed, we need to do a retrospective on why it happened - e.g. are adjustments needed to the QA release testing process, or was there a reason why the last minute bug fix happened.
 - T-2 (Tuesday)
    - A new release image is created and the QA team completes quick smoke testing on the Cloud Beta production servers.
 - T-0 (Thursday)
    - The release is rolled out to the remaining rings.
