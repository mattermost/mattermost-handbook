---
description: 1% DRAFT
---

# Integrations Team Processes

## Weekly team meeting

* Schedule meeting items by running `/agenda queue Tuesday [item]` in [`~extensibility-meeting`](https://community.mattermost.com/core/channels/extensibility-meeting).

### Workflow

1. Metrics updates: 2 min presentation on interesting metrics on [https://mattermost.looker.com](https://mattermost.looker.com).
2. [Plugin Release Updates](https://github.com/orgs/mattermost/projects/1): Was did we ship in the last sprint? What do we want to ship in the next 4 weeks? What are blockers for that?
3. Thursday R&D Demo: Decide what to demo.
4. Guilds Updates: Short update from every guild meeting. If there isn't anything relevant, skip to the guild.
5. Triage Jira Toolkit, Jira Integrations, and GitHub.
6. Go through queued meeting items.
7. \(Optional\) Quick stand up using [the GitHub board](https://github.com/orgs/mattermost/projects/1) and Jira.
8. Remove all `Done` items from both GitHub boards.

## QA testing

* QA testing is require for all changes for not Beta plugin in the Marketplace.
* QA testing may be shipped for Beta plugins.
* QA testing is not required to changes that don't touch the production code of a plugin e.g. tooling changes.

### Peer Testing Process

1. Dylan will @-mention reviewers and request peer testing posting a link to the process.
2. Using session-based testing example format provided developers will perform functional testing on the PR and take lightweight session notes. See example attached here: [https://mattermost.atlassian.net/wiki/download/attachments/619937892/SampleSessionNotes.txt](https://mattermost.atlassian.net/wiki/download/attachments/619937892/SampleSessionNotes.txt).
3. Once testing is done, developers will at mention Dylan in a comment and attach their session notes.
4. Dylan will review session notes.
5. As appropriate, Dylan will make updates to release testing based on functional changes or previously untested cases.
6. Dylan will approve the PR for merge.
7. Any functional changes will be included in the next end to end test on the version bump PR as usual.

#### Things to be mindful of \(WIP\):

* For visual changes, ensure that themes are properly applied.
* When front end changes are made you should often test in desktop as well as browser as the JS is different.
* Icons generated with system font can be different on from Mac to Windows.

#### Testing notes example

```text
Scope
-----

<!-- Your understanding of what functional impact the PR will have on the product -->

- Display username that created zoom meeting #62.
- Test that username of meeting creator is always shown.

Testing notes
-------------

<!-- Testing you've done that you feel validate the change and cover any needed regression -->

- User name is displayed in with Zoom meeting post as expected.
- Tested switching mapped users to ensure display remains accurate.
- Tested updating username to ensure display.
- Trigger 30 second meeting collision post to ensure the functionality is also affected by the enhancement.

Follow-up concerns
-------------------

Seeing an intermittent connection issue with Zoom on http://dkh-local.ngrok.io. Seems to occur on desktop.
```

## Ticket workflow

### Jira

* Jira tickets must be filed for:
  * Planned changes in the core product \(Server, Webapp, Mobile, Redux\).
  * Bugs in the core product \(Server, Webapp, Mobile, Redux\).
* Jira ticket may be filled for larger multi-plugin projects.

### GitHub

* For all confirmed bugs a GitHub issue on the corresponding repository must be filed.
* For all enhancements a GitHub issue on the corresponding repository should be filed.
* Add a `Type/X` label to make clear what type the ticket is.
* You may add a `Difficulty/X` label to set a mana estimate.
  * `Easy` means 2 mana
  * `Medium` means 4 mana
  * `Hard` means 8 mana
* Staff members add the issues there are working on for the current sprint to [https://github.com/orgs/mattermost/projects/1](https://github.com/orgs/mattermost/projects/1).
  * Putting an issue is always preferred over putting a PR on the board.

## Documentation process

**1% draft**

This guide outlines the processes and workflows for requesting, updating, managing, and maintaining documentation for Mattermost-managed and community-managed apps, plugins, and integrations. This includes the branching strategy for the Gitbook repos, how to set up a new Gitbook, and the process for aligning documentation with releases.

Mattermost integrations documentation currently spans:

* [docs.mattermost.com](https://docs.mattermost.com/guides/integration.html): Outline of how integrations work with Mattermost and a list of integrations available.
* Gitbook: Configuration and User documentation for plugins, as well as developer content.
* developers.mattermost.com: Apps documentation, plugin documentation, introduction to the contribution process, contribution workflow, testing, and validation information.

Mattermost-managed integrations are maintained by Mattermost staff and the documentation is written and maintained by the Integrations team. Community-managed integrations are maintained by their creator, which includes documentation maintenance.

## Apps documentation workflow

The Apps Framework and Marketplace documentation lives [here](https://developers.mattermost.com/integrate/apps/). When submitting documentation updates and new documentation for apps, there are two options available:

1. Submit the content with your PR in the [plugin-apps](https://github.com/mattermost/mattermost-plugin-apps) repo. Add the `Docs/Needed` label to the PR and ping @justinegeffen. The content will then be added to the docs, and the `Docs/Done` label added to your PR.
2. Alternatively, you're welcome \(and encouraged\) to submit the docs PR yourself, [here](https://github.com/mattermost/mattermost-developer-documentation/tree/master/site/content/integrate/apps), then add a `Docs/Needed` label and tag @justinegeffen.

For both options, please ensure that doc updates are either provided by you or requested ahead of merge so there's time to review the content. At least four days' notice is ideal. The goal is to ensure that docs and releases are always in sync.

## Plugin documentation workflow

The plugin documentation will soon be moved to developers.mattermost.com and will follow the same process as above. Until then, if you have a documentation update for your plugin, please work with @justinegeffen to ensure changes made in time and aligned with release.

This is the same process used for the webapp and server repos in terms of documentation work.

### Documentation for plugins with multiple versions

If a plugin has documentation for multiple versions the master branch is the source of truth of the docs for the current release version of a plugin. Previous releases are archived as a \(version\)-docs branch when docs need to change.

Every time we release a new minor or major version plugin we cut a new branch with docs and keep the branch forever so customers can still refer back to it.

Plugins that don't have documentation for multiple versions can have their content updated in master and don't follow this process.

### Working in Gitbook

We use Gitbook to render our documentation. A migration process from Gitbook to the Developers website is scheduled to start soon, at which point all plugin documentation will live in that repo.

Details of the PR process for updating docs once this migration is complete will follow.

## Documentation template for contributions

TODO
