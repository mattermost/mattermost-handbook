---
description: 1% DRAFT
---

# Integrations Team Processes

## Weekly Team Meeting

- Schedule meeting items by running `/agenda queue Tuesday [item]` in [`~extensibility-meeting`](https://community.mattermost.com/core/channels/extensibility-meeting).

### Workflow

1. Metrics updates: 2 min presentation on interesting metrics on https://mattermost.looker.com.
2. [Plugin Release Updates](https://github.com/orgs/mattermost/projects/1): Was did we ship in the last sprint? What do we want to ship in the next 4 weeks? What are blockers for that?
3. Thursday R&D Demo: Decide what to demo.
4. Guilds Updates: Short update from every guild meeting. If there isn't anything relevant, skip to the guild.
5. Triage Jira Toolkit, Jira Integrations, and GitHub.
6. Go through queued meeting items.
7. (Optional) Quick stand up using [the GitHub board](https://github.com/orgs/mattermost/projects/1) and Jira.
8. Remove all `Done` items from both GitHub boards.

## QA testing

- QA testing is require for all changes for not Beta plugin in the Marketplace.
- QA testing may be shipped for Beta plugins.
- QA testing is not required to changes that don't touch the production code of a plugin e.g. tooling changes.

### Peer Testing Process

1. Dylan will @-mention reviewers and request peer testing posting a link to the process.
2. Using session-based testing example format provided developers will perform functional testing on the PR and take lightweight session notes. See example attached here: https://mattermost.atlassian.net/wiki/download/attachments/619937892/SampleSessionNotes.txt.
3. Once testing is done, developers will at mention Dylan in a comment and attach their session notes.
4. Dylan will review session notes.
5. As appropriate, Dylan will make updates to release testing based on functional changes or previously untested cases.
6. Dylan will approve the PR for merge.
7. Any functional changes will be included in the next end to end test on the version bump PR as usual.

#### Things to be mindful of (WIP):

- For visual changes, ensure that themes are properly applied.
- When front end changes are made you should often test in desktop as well as browser as the JS is different.
- Icons generated with system font can be different on from Mac to Windows.

#### Testing notes example

```
Scope
---------

<!-- Your understanding of what functional impact the PR will have on the product -->

- Display username that created zoom meeting #62.
- Test that username of meeting creator is always shown.

Testing notes
----------------

<!-- Testing you've done that you feel validate the change and cover any needed regression -->

- User name is displayed in with Zoom meeting post as expected.
- Tested switching mapped users to ensure display remains accurate.
- Tested updating username to ensure display.
- Trigger 30 second meeting collision post to ensure the functionality is also affected by the enhancement.

Follow-up concerns
-------------------

Seeing an intermittent connection issue with Zoom on http://dkh-local.ngrok.io. Seems to occur on desktop.
```

## Ticket Workflow

### Jira

- Jira ticket must be filled for:
    - Planed changes in the core product (Server, Webapp, Mobile, Redux).
    - Bugs in the core product (Server, Webapp, Mobile, Redux).
- Jira ticket may be filled for larger multi-plugin projects.

### GitHub

- For all confirmed bugs a GitHub issue on the corresponding repository must be filled.
- For all enhancements a GitHub issue on the corresponding repository should be filled.
- Add a `Type/X` label to make clear what type the ticket is.
- You may add a `Difficulty/X` label to set a mana estimate.
    - `Easy` means 2 Mana
    - `Medium` means 4 Mana
    - `Hard` mean 8 mana
- Staff members add the issues there are working on for the current sprint to https://github.com/orgs/mattermost/projects/1.
    - Putting an issue is always preferred over putting a PR on the board.
