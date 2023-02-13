# Feature documentation process: Product Manager and Developers

## Submitting feature documentation

Feature documentation is a joint effort between Product Managers, Developers, and Technical Writers. In the same way that we want to empower everyone to contribute to our documentation, Product Managers are encouraged to write MVP documentation for their product/feature.

Feature changes and new features first exist as code PRs. These PRs form the basis of whatever changes are being documented. If a code PR is for a new feature, major update to an existing feature, or a fix that impacts the current documentation, it's recommended that a documentation update is made. The Technical Writers work closely with their development teams to ensure that these types of changes are documented accordingly. 

One way we do this is by using the `Docs/Needed` label. When a code PR is submitted, that may have documentation impact, the `Docs/Needed` label is added. The assigned writer then reviews the PR and, if there are documentation changes needed, opens a PR in the docs repo with reference to the code PR.

As a developer you are also welcome to update the documentation yourself in one of the following ways:

* Update the relevant page on [docs.mattermost.com](https://docs.mattermost.com), and submit a PR for that. This PR is submitted to the docs repo, reviewed by the relevant team members, and merged from there.
* Submit your documentation as a new file, including the context and changes, any code samples, and processes. You can submit this as part of your code PR, or you can open a new PR in the docs repo and include a link to your open code PR.

We don't expect a huge body of documentation or that it's perfectly-written - but rather a clear, concise outline of the change which can be added to our documentation. The content can be provided as a list, rough notes, or you can use the example below for content and structural guidance if your documentation is quite detailed.

**Note:** Due to the cadence of the release cycle, feature documentation needs to be complete and submitted as [per the release process](https://handbook.mattermost.com/operations/research-and-development/product/release-process/feature-release#e-t-minus-15-working-days-judgment-day) to allow sufficient time for review and to ensure it's included in the release documentation update.

The supplied content can be provided informally, in bullet points, or rough notes in a Google Doc/on the PR itself. Refinements are made collaboratively.

### Feature documentation MVP \(Product Managers\)

A [Mattermost PM feature template](https://docs.google.com/document/d/16SRPKFWEtwPILQ0zNGbApbp9atICTfzgdTFuvYqSZAg/edit) is available to help Product Managers and Techical Writers capture details about new features and functionality that need product documentation.

This is a guideline of what MVP feature documentation can include. Requirements vary based on the scope of the change, so not everything will always be needed:

* A link to the feature/product's tech spec.
* Links to any relevant Jira/GitHub issues.
* A description of the product/feature/update which forms the basis of the documentation.
* Steps for any processes or procedures \(configuration of a feature, troubleshooting, etc\).
* Any FAQs or troubleshooting questions if relevant.
* Any limitations, issues, or known problems.
* Configuration settings and examples for the `config.json` file if relevant.
* \(If possible\) Suggestions of where in the docs the content should go.

When the content has been refined and approved in draft format:

* The Product Manager/Technical Writer creates a branch off the relevant documentation release branch.
* The documentation is updated with the approved content in that branch.
  * If there are multiple pages to update for a specific feature/change please keep them all in the same branch for ease of management.
* The PR is submitted and relevant reviewers added, including an editor \(not the Technical Writer who wrote the docs\), for final review.
  * Include the link to the server/webapp repo issue in your PR for reference purposes.
* Once all reviews are complete, the PR is marked as **Reviews Complete** and merged into the documentation release branch by @amyblais.

You can read more about the review process [here](https://developers.mattermost.com/contribute/getting-started/code-review).

You can find additional guidance around formatting [here](https://handbook.mattermost.com/operations/operations/company-processes/publishing/publishing-guidelines/voice-tone-and-writing-style-guidelines/documentation-style-guide#using-restructuredtext-markup-rst).

Once your PR is submitted, there's a review process that includes an editorial review, a PM review, and sometimes a dev review. During the editorial review, editors may make punctuation and/or terminology changes and commit them to save time on the review process. This only applies to punctuation/terminology - content suggestions and questions will follow the usual review and discussion process.

Once the review is complete, we'll move your contribution to the appropriate part of [docs.mattermost.com](https://docs.mattermost.com) \(if it's not there already\) and then merge it. We'll share the URL and you can edit it at any time if you need to.

## Add reviewers to PRs

Mattermost documentation covers a number of different topics. For documentation, the following reviewers are recommended:

**Editor Review**

* Carrie Warner \(@cwarnermm\)
* Justine Geffen \(@justinegeffen\)

**Product Manager Review**

* Product: Ian Tao \(@tao\); Winson Wu (\@wuwinson\)
* Integrations: Sandy Atkinson \(@asatkinson\)
* Security: Daniel Schalla \(@dschalla\)
* Server/calls: Neil Barnett \(nab-77)\
* Self-serve: John Lugtu \(@johndavidlugtu)\
* Growth: Eric Sethna \(@esethna\)

* Handbook and Process; Community: Jason Blais \(@jasonblais\)

**Dev Review**

If your change requires dev review add the developer/s you've been working with as the reviewer/s. If you're unsure who to add as a dev reviewer you can select one of the team leads below:

* Product: Scott Bishel \(@sbishel\)
* Integrations: Catalin Tomei \(@catalintomai\)
* Growth: Maria Nuñez \(@marianunez\)
* SRE: Stylianos Rigas \(@stylianos\)
* Cloud Platform: Spiros Economakis \(@spiros\)
* Mobile: Elias Nahum \(@enahum\)
* Web/desktop app: Pantelis Vratsalis \(@pantelis\)
* Security: Daniel Schalla \(@dschalla\)
* QA: Saturn Abril \(@saturninoabril\)

The full list of R&D teams is available [here](https://docs.google.com/spreadsheets/d/1lH8QIjQGEoGospDUdVs_LQ_i2b82I1ce6W7z18vhPTQ/edit#gid=1730823498).

## Providing editorial feedback

If you're asked to provide editorial feedback on a PR, and it's your first editorial feedback request, first read up on the review process [here](https://developers.mattermost.com/contribute/getting-started/code-review) to get an idea of what's expected in terms of turnaround time, type of feedback, and so on.

Editorial feedback is based on the guidelines laid out in the [Documentation Style Guide](https://handbook.mattermost.com/operations/operations/company-processes/publishing/publishing-guidelines/voice-tone-and-writing-style-guidelines/documentation-style-guide) as well as the [Voice, Tone, and Writing Style Guide](https://handbook.mattermost.com/operations/operations/publishing/publishing-guidelines/voice-tone-and-writing-style-guidelines).
