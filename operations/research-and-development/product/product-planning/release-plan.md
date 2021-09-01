# Release Plan

A release plan outlines the features and work that we plan on putting into the release version of the product. A release plan allows us to understand our resources available to accomplish the design, development, and quality assurance work required for a successful product release.

## Release Plan vs. Roadmap

A release plan is different from a roadmap, in that a roadmap typically lays out the direction and prioritization the product is headed and includes larger objectives and larger features.

The release plan may include major bugs, smaller features and even tasks required to complete a feature set. The release plan document typically includes all the R&D teams’ proposed work so that we can get a holistic view of what features, bugs or improvements are targeted for the release. Each team may also have their own version of a release plan that they use for tracking features and resource planning. You can find our [release plan here](https://mattermost.productboard.com/feature-board/1097526-release-tracking-internal).

When we add items to a release, we are targeting their completion by that release, however, things such as underestimation of work required or quality issues found during testing may prevent it from actually being released.

* If a feature is at risk being cut from a release after it was targeted, we do our best to communicate to all those interested as soon as possible. Typically, the PM team reviews and updates the release plan weekly.
* If a feature is cut from a release, it is not necessarily put into the next release. There may be unforeseen complications that need to be solved that may take multiple release cycles to address. In some cases, other work may be deemed higher priority and the feature will be deprioritized and considered at a later stage.

PMs will do their best to communicate next steps for features that are cut.

## Release Philosophy

We follow a time-based release philosophy. This means we release a new version of our Mattermost product every month on the 16th.

### Extended Support Releases

Our releases for January and July are offered as an [Extended Support Releases \(ESR\)](https://docs.mattermost.com/administration/extended-support-release.html). This type of release allows customers to receive backports for security fixes and bug fixes without having to upgrade to a version with new functionality that would require significant testing and certification before rolling to large volume of users. We also do dot releases for major bugs and security fixes and backport these to the previous three monthly releases. For more information on our release types and processes please see this [documentation](https://handbook.mattermost.com/operations/research-and-development/product/release-process/release-overview).

## Major Versions

At times, we may do a major release version of our software. A major version provides us the opportunity to make breaking changes that allow us to re-define how product functions and to support future features, deprecate some foundational features that have been replaced, as well as package new major functionality as part of the binary. Major versions are scheduled well in advance and notices about major changes are communicated early so that customers can prepare for changes.

