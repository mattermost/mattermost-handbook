# Cloud Data Export Process

This page outlines the current steps for the Mattermost team for creating a data export file for a Mattermost Cloud administrator. All exports are in JSONL format by default.

## Current Process

1. Cloud user contacts Mattermost, requesting a data export. This can be made by contacting the support team via https://customers.mattermost.com/cloud/contact-us, or through the Mattermost Help Center at https://support.mattermost.com/.
2. Zendesk ticket automatically created for the request, assigned to a Support team member.
3. Support team member confirms which of the following data exports is requested:

 - Configuration data in JSONL format, which they can apply to their Self-Hosted deployment.
 - Configuration and [bulk export](https://docs.mattermost.com/manage/bulk-export-tool.html) data with channels, messages, and more in JSONL format.
 - Configuration and [bulk export](https://docs.mattermost.com/manage/bulk-export-tool.html) data in JSONL format, plus all assets stored in s3 (e.g. files).
 - Everything in the database, with either a raw database dump, or pre-formatted CSV file.

4. Support team member opens a Jira ticket for the SRE team to process the data export request with the following information (see [MM-38454](https://mattermost.atlassian.net/browse/MM-38454) for an example):

 - Cloud URL, e.g. https://example.cloud.mattermost.com/
 - Account owner email, e.g. admin@example.com
 - Data export format, e.g. JSONL
 - Cut-off date for history export, e.g. Sep 9, 2021
 - Link to Zendesk ticket, e.g. https://mattermost.zendesk.com/agent/tickets/1234

5. SRE team performs the data export per request, with a 5-business day SLA, and stores it in S3.
6. SRE team shares the data export S3 link to the Support team.
7. Support team forwards the S3 link to the requester.

## Future Optimizations

Long-term we'd like to make this process self-serve.

In the near term, we are aiming to publish documentation about Cloud data imports/exports by October 25. 

This will make the data export process for channels, messages and other [bulk export](https://docs.mattermost.com/manage/bulk-export-tool.html) data self-serve, with some knowledge about running commands to export the data.

Providing a self-serve import/export capability via the UI is not in the near-term roadmap, but can be considered if we see an increased demand. An early draft of this proposed approach [can be found here](https://docs.google.com/document/d/1eTTdd8uM1FxVcPcCrtdPlbOcVZE2UwHLWL2Jy-MmYts/edit).

