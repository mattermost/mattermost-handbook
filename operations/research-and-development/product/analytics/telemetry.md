# Telemetry

## Summary

Telemetry data is optionally shared from your Mattermost servers and is used to identify security and reliability issues, to analyze and fix software problems, to help improve the quality of Mattermost software and related services, and to make design decisions for future releases.

Telemetry is essential for tracking product usage, quickly identifying problems, and operating our business. Our goal is to have working telemetry, in the form of Looker reports, for every feature before it is released.

To collect telemetry, we are using [RudderStack](https://rudderstack.com/) which is then pushed to [Snowflake](https://www.snowflake.com/). You can read more about our Data Engineering infrastructure at [Data Engineering](https://handbook.mattermost.com/operations/research-and-development/engineering/data-engineering).

## [The Telemetry Handbook](https://mattermost.atlassian.net/wiki/spaces/DATAENG/pages/2729639944/Telemetry+Handbook)

We have created this handbook to ensure we collect useful telemetry from all sources. This handbook is the guideline for how to implement telemetry, both from the perspective of Product Managers and the engineers doing the actual implementation.
