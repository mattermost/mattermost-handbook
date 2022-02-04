# Technical Writing Team Handbook

## Technical Writing Handbook

Mattermost Technical Writers focus primarily on writing, editing, structuring, and maintaining Mattermost technical and product documentation, end user documentation for Mattermost Channels, Boards, and Playbooks, as well as developer documentation and the company Handbook. Technical Writers also manage in-product microcopy, provide editorial reviews for all documentation across the organization, and work closely with the community to improve documentation.

### Areas of responsibility \(AORs\)

Documentation and technical writing at Mattermost covers \(but isn't limited to\) the following verticals:

* Channels
  * Mattermost Cloud
  * Self-managed deployments
  * Messaging features and functionality
* Playbooks
* Boards
* Growth
  * Customer Portal
  * Telemetry
* Apps Framework and Marketplace

Other areas of documentation include:

* Mattermost Handbook
* Integrations \(developer documentation, plugin documentation, and developer journey\)
* Documentation metrics:
  * Docs page ratings via Google Analytics
  * Google Analytics metrics for page visits, read times, and bounce rates
  * Customer feedback analysis
  * Metrics dashboards using RudderStack
* In-product messaging and interface
* GitLab documentation for:
  * [GitLab Mattermost docs](https://docs.gitlab.com/omnibus/gitlab-mattermost/%20)
  * GitLab helm chart docs
* Developer documentation for:
  * [developers.mattermost.com](https://developers.mattermost.com), including Contribute, Integrate, and Extend sections
  * [api.mattermost.com](https://api.mattermost.com)
  * General developer experience docs, e.g. code samples, best practices, and tutorials
* Community and doc review process
  * Process for Doc Up plugin
  * Docs review and release coordination
  * Community Help Wanted doc issues
* Content and processes
  * PR reviews across the organization
  * Documentation processes for release PRs

Please reach out to the [Documentation Working Group](https://community.mattermost.com/private-core/channels/dwg-documentation-working-group) for any questions.

## How to contribute to the documentation

Our documentation is open to contributions from anyone. The basic outline for getting started with contributions is provided in the [README](https://github.com/mattermost/docs/blob/master/README.md) of the docs repo. If you have write access to the repo, you can create a branch off master and work on that.

Once complete, submit your Pull Request \(PR\). Ensure that you assign appropriate approvers and labels - if you've forked the repo or don't have the correct repo permissions you may not be able to do this, so you can skip this step. Read more about the review process [here](https://developers.mattermost.com/contribute/getting-started/code-review) - it applies to various types of contributions including documentation.

### PR tips and best practices

* Try to submit files in batches rather than single PRs for each file update. This reduces the PR load and also groups your changes more effectively.
* When there are lots of changes requested, especially on a docs PR that doesn't require QA testing, you can use the "Add suggestion to batch" feature in GitHub to commit all of the suggestions at once. You need to be on the **Files changed** tab to use this feature, though it's also shown on the **Conversation** tab. By batching your suggestions, you can use one commit message such as "Added batch suggestions from @Carrie Warner". This just makes the commit history of the PR a lot more readable and useful for everyone reviewing it.
* Descriptive PR titles and commit messages go a long way, especially when the PR is referenced in the future. The default PR titles that GitHub gives us like "Updated README.md" are not very helpful because there's no way to know the purpose of the PR by reading the title. For example, if the whole file was translated to Japanese because we realize that's our main audience, that information isn't obvious unless you open the PR and read it - or if it's in the PR title.

## Style Guide and UI writing guides

Our [Documentation Style Guide] is a guide to writing Mattermost product documentation and includes guidelines around punctuation, casing, and how to format files. We also have [a guide for writing UI copy](https://handbook.mattermost.com/operations/research-and-development/product/development-process/user-interface-text-guidelines) which includes tip, best practices, and examples.

## i18n contributions

**Note: This process is in flight.***

Our product documentation is available for translation contributions. Join the [i18n channel](https://community.mattermost.com/core/channels/localization) on our Community server and connect with our translation community members. The documentation translation process is still being defined, and @cwarnermm is the DRI along with members of the Localization team.

Currently, submitting a translation PR follows the same writing and editing process as other PRs. However, there are additional considerations to bear in mind when submitting your PR as these assist with the approval and merge process:

1. Do you have an active test instance running with the integrations guide translated so we can validate the rendering and formatting?
2. If the content you're translating includes screenshots should we keep the original English versions of the screenshots, or consider translated versions of them too?
3. If the intention is to translate the screenshots, is there a proposed process for keeping them up to date?
4. Have at least one member of UX team and one member of Apps PM team review the user experience in choosing different languages.
5. To maintain high standards for translated documentation, set up a process to notify translators when something is changed in the English-version of the docs, and expectation on correcting translations for new releases.
6. Decide if we want to indicate translations level - e.g. “Alpha” or “Beta” for translations that are in progress.
7. Test you can successfully rate a translated docs page by selecting a rating emoji. Ping @justine.geffen for validation of this.

## GitHub training

GitHub training videos coming soon!
