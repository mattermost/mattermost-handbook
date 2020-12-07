# Integrations Documentation

**1% draft**

This guide outlines the processes and workflows for requesting, updating, managing, and maintaining documentation for Mattermost-managed integrations. This includes the branching strategy for the Gitbook repos, how to set up a new Gitbook for an integration, and the process for aligning documentation with releases.

## Processes

Integrations comprise Mattermost-managed intergrations and community-managed integrations.

- Mattermost-managed integrations are maintained by Mattermost staff and the documentation is written and maintained by the Mattermost Technical Writer.
- Community-managed integrations are maintained by their creator, which includes documentation maintenance.

Mattermost integrations documentation spans three areas:

- docs.mattermost.com: Outline of how integrations work with Mattermost and a list of integrations available.
- Apps Marketplace/Gitbook: Configuration and User documentation, as well as developer content.
- developers.mattermost.com: Introduction to the contribution process, contribution workflow, testing and validation information.

### Cloud apps documentation

### Self-managed apps documentation

### Workflow and timelines

#### Updating plugin documentation

When there are changes to Mattermost-managed plugins which require documentation updates, create a new docs issue and assign it to @justinegeffen. Please include a link to the code change PR and raw content for the documentation update.

#### New plugin documentation

When new documentation needs to be written, create a Jira issue and assign it to the Technical Writing team and @Justine Geffen. Include links to any raw content as well as any PRs. Please also include a timeline for the documentation delivery.

### Branching strategy for documentation

The master branch is the source of truth of the docs for the "current release" of a plugin, and archive "previous release" as a (version)-docs branch when docs need to change.

Every time we release a new minor or major versionplugin we cut a new branch with docs and keep the branch forever so customers can still refer back to it. 

### Aligning development and documentation

### Creating new documentation

#### Creating a Gitbook space

### Documentation template for contributions
