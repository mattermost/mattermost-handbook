# Apps and Integrations Documentation Processes

**1% draft**

This guide outlines the processes and workflows for requesting, updating, managing, and maintaining documentation for Mattermost-managed and community-managed apps and integrations. This includes the branching strategy for the Gitbook repos, how to set up a new Gitbook for an integration, and the process for aligning documentation with releases.

Integrations comprise Mattermost-managed intergrations and community-managed integrations.

- Mattermost-managed integrations are maintained by Mattermost staff and the documentation is written and maintained by the Mattermost Technical Writer.
- Community-managed integrations are maintained by their creator, which includes documentation maintenance.

Mattermost integrations documentation spans three areas:

- docs.mattermost.com: Outline of how integrations work with Mattermost and a list of integrations available.
- Apps Marketplace/Gitbook: Configuration and User documentation, as well as developer content.
- developers.mattermost.com: Introduction to the contribution process, contribution workflow, testing and validation information.

## 

### Cloud apps documentation

TBC

### Self-managed apps documentation

TBC

## New documentation

When a new app or integration is created, it follows this process: (link to the steps). Part of this process includes writing documentation.

If your app or integration is a Mattermost-managed one, please follow this process: reate a Jira issue and assign it to the Technical Writing team and @justinegeffen. Include links to any raw content as well as any PRs. Please also include a timeline for the documentation delivery.

Community-managed apps or integrations are managed by their maintainers, which includes documentation updates.

## Updating documentation

When apps or integrations are updated, please follow this process: (link to process). If the update has documentation requirements, please follow this process: When there are changes to Mattermost-managed plugins which require documentation updates, create a new docs issue and assign it to @justinegeffen. Please include a link to the code change PR and raw content for the documentation update.


### Branching strategy for documentation

Different plugins have different branching strategies, depending on the versioning pattern they use.

#### Plugins with multiple versions

The master branch is the source of truth of the docs for the "current release" of a plugin, and archive "previous release" as a (version)-docs branch when docs need to change.

Every time we release a new minor or major versionplugin we cut a new branch with docs and keep the branch forever so customers can still refer back to it.

## Working in Gitbook

We use Gitbook to render our documentation.

## Apps Documentation Framework

## Bounty process

## Documentation template for contributions



