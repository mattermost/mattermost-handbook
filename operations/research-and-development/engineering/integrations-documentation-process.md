# Integrations Documentation

**1% draft**

This guide outlines the processes and workflows for requesting, updating, managing, and maintaining documentation for Mattermost-managed integrations. This includes the branching strategy for the Gitbook repos, how to set up a new Gitbook for an integration, and the process for aligning documentation with releases.

## Vision and Goals

High quality content that’s intuitively located and accessible from web and apps marketplace.

- Standardizing all content and bringing it in line with our quality and voice.
- Updating content to provide usage cases for plugins.
- Defining the developer journey to remove friction from the contribution funnel by identifying documentation gaps and potential blockers.
  - Documentation template so contributors can submit documentation with their plugin.
  - Guidance around creating Cloud Apps.
  - Update and refine the plugins contribution documentation.
- Working with the community to get feedback, suggestions, and fix any errors in documentation.
- Define processes and workflows as well as plugin DRIs to ensure documentation is kept up to date.

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

### Branching strategy for documentation

- The default landing page is the latest minor or major release but NOT including the latest version in master. Using the branching strategy below, we can include the upcoming release documentation as an option in the LHS which can be viewed prior to release to see what’s coming. 
- Master branch is for code changes and doc changes and have branches for releases, so docs are always available for previous versions.

Every time we release a new minor or major versionplugin we cut a new branch with docs and keep the branch forever so customers can still refer back to it. 

### Aligning development and documentation

### Creating new documentation

#### Creating a Gitbook space

### Documentation template for contributions
