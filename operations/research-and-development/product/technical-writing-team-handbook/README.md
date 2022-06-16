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

## Set up a local development environment

Members of the writing team have two ways to contribute to Mattermost product documentation:

- Using GitHub web tools. See the GitHub training section below for details.
- Working within a local development environment. See the mattermost/docs repository [README](https://github.com/mattermost/docs#building-and-validating) documentation for details on setting up a local environment.

### Clone a documentation fork locally

Mattermost product documentation contributions can be created in one of two ways:

- as a branch (applies only Mattermost staff with appropriate GitHub repository permissions)
- as a fork (applies to all other documentation contributions)

In a GitHub documentation PR, branched contributions display using the branch name, and forked contributions display as `username/reponame:branchname` instead. While branched contributions are automatically pulled down to a local environment when you run the command `git pull` or `git fetch origin` from the command line, forked contributions must be pulled down manually.

To work with a forked contribution locally:

1. In the GitHub PR, identify the contributor's username.
2. In your local file system, create a new directory for the fork.
3. Navigate to the new directory, then clone the fork by running the command `git clone https://github.com/username/reponame`. Note that you don't need to specify the branch name.
4. Switch to the branch you want to explore by running the command `git checkout branchname`.
5. (macOS users only) Sync your virtual environment for the new directory by running the command `pipenv sync`.

## Extend Sphinx functionality

Extending product documentation functionality typically involves extending the Sphinx static generation tool with extensions that introduce new display, page, build, navigation, or output capabilities. For example, all code blocks on all pages of the product documentation feature a copy/paste option to make trying out code samples easy for documentation visitors. The copy/paste option was added by installing a Sphinx extension created by an open source contributor.

To get started with Sphinx extensions, you'll want to set up a local development environment, then identify an open source Sphinx extension you want to test based on an outcome or goal you're looking to achieve that improves the learning experience for Mattermost documentation visitors.

1. In a local documentation development environment, from the command line terminal, install the Sphinx extension using the installation instructions provided by the extension author.
2. Regenerate the `pipenv.lock` file by running the following command: `pipenv install sphinx-extension==version` where `version` is replaced with the extension's release version you want to use.
3. Update the `conf.py` file to add the extension in the `extension` section. 
4. Incorporate the new Sphinx extension on a documentation page using appropriate syntax.
5. Build the documentation locally to test how the extension works. Be sure to test as many edge cases and real world situations as you can to ensure that the new extended functionality won't break existing pages or content.

## Upgrade Sphinx

Mattermost product documentation is generated using Sphinx v4.4. As new Sphinx functionality becomes available, it can be desirable or necessary to upgrade Sphinx to a later release.

To get started with a Sphinx upgrade, you'll want to set up a local development environment, then review the [Sphinx release history](https://pypi.org/project/Sphinx/#history) to identify the upgrade version you want. It's important to understand and test upgrades locally to identify any risks an upgrade may introduce to the Mattermost documentation.

Once you have a Sphinx upgrade version in mind:

1. In a local documentation development environment, from the command line terminal, install the Sphinx upgrade by running the following command: `pipenv install sphinx==version`. This command updates both the `pipfile` with the latest Sphinx version and regenerates the `pipfile.lock`.
2. Sync your virtual environment for the new Sphinx version by running the command: `pipenv sync`.
3. Create a documentation PR containing the two file changes to `pipfile` and `pipfile.lock`.
4. Once the PR merged into production, writers can update their local development environments to use the Sphinx upgrade by running the following command: `pipenv sync`.

Following a successful Sphinx upgrade, complete the following checklist tasks to ensure that the new version of Sphinx doesn't impact existing functionality, content, or output.

### Sitemap generation

1. Open the latest sitemap via `docs.mattermost.com/sitemap.xml` in a browser tab.
2. Generate the product documentation, then use a text compare tool such as [text-compare](https://text-compare.com/) to review the differences between the newly generated sitemap against what's available in production.

You shouldn't see any glaring differences and the sitemap should NOT have any Mattermost version information in any of the URLs. You may see content move around on the page. Confirm that page URLs in production continue to exist in the latest generated sitemap XML file.

### Page redirects

Spot check a handful of redirects specified via the `conf.py` file to ensure they continue to redirect visitors correctly.

### Parallel processing and pickling

When you build the documentation locally, is the build fast? Do you see a message in the terminal indicating that pickling was successful?

If the build takes more than a few minutes to complete, or you don't see the pickling success message, this could indicate an issue with the Sphinx version, and you may want to reconsider an upgrade to this version.

### HTML output

After successfully building the product documentation:

- Navigate around the site to ensure that nothing looks or feels broken.
- Review pages with tables and tabbed content to ensure the content displays as intended.
- Review the landing page as well as subsequent page headers/footers to ensure links take users to expected destinations.
- Review the Changelog pages (which are managed in Markdown source files) to ensure that the changelogs are converted to HTML correctly.
- Perform a few docs searches to confirm that searches continue to work as expected.

### Build warnings and errors

Review and fix issues reported via the `/build/warnings.log` file including broken links, pages missing from the LHS, and syntax and formatting problems. 

### Review documentation repository setup instructions

- In GitHub, review the [mattermost/docs](https://github.com/mattermost/docs) repository [README file](https://github.com/mattermost/docs#mattermost-documentation) and this Handbook process documentation to ensure content accuracy.

## GitHub training

GitHub training videos coming soon!

### Add PRs to monthly documentation release branches

If you encounter a documentation PR that should be included in a monthly documentation release cycle, instead of tracking the PR individually, the PR can be merged into a documentation release branch. 

1. In the PR, identify the branch name you want to include in a documentation release branch. 
2. Ensure your local development environment is up-to-date and contains the same code as the `master` branch.
3. Navigate into the branch where you want to merge in the PR to ensure all code is available locally.
4. From a terminal, run the command `git merge branchname` where `branchname` is the name of the branch you want to commit to a monthly documentation release.
5. If there are no conflicts, you'll see the vi editor. Review the commit message, then type `:x` to save and exit. If there are conflicts, you need to resolve them on the CLI and commit them first before you can move to the next step to push remotely.
6. Push your changes remotely by running the command `git push`.

