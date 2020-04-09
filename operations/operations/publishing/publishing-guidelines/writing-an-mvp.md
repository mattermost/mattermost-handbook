# Writing and submitting documentation with your PR

Our user, admin, and technical documentation lives at [docs.mattermost.com](https://docs.mattermost.com), primarily written using ReStructured Text, using Sphinx and Write The Docs as our build and theme tools. 

If your PR is for a new feature, major update to an existing feature, or a fix that impacts the current documentation, it's recommended that you include documentation around the change. This is helpful in providing context for reviewers, and also ensures the content can be added to the documentation quickly. 

You can contribute documentation in one of the following ways: 

* Update the relevant page on [docs.mattermost.com](https://docs.mattermost.com), and submit a PR for that. This PR is submitted to the docs repo, is reviewed by the relevant team members, and merged from there. 

* Submit your documentation as a new file, including the context and changes, any code samples, and processes. You can submit this as part of your PR, or you can open a new PR in the docs repo and include a link to your open code PR. 

We don't expect a huge body of documentation or that it's perfectly-written - but rather a clear, concise outline of the change which can be added to our documentation. The content can be provided as a list, or you can use the example below for content and structural guidance if your documentation is quite detailed:

```
## Introduction and context
*Details of the current feature/function and what the contribution fixes or adds. This can be presented as bullet points. For example:*
"This adds a new property to be used by the desktop app in the same way other properties are being used for the user profile view. This change is part of the configuration settings in System Console and is also included in the CLI."

## Configuration or Installation (if applicable)
*Provide configuration and set up steps in the context of the change/feature. For example:*
"The steps needed to configure this are as follows: 
1. Navigate to **System Console > MenuItem > MenuItem**.
2. Set the setting to ``true``. 
3, Click **Save**.

For the CLI, the following parameters needs to be added: 
(include parameter/s)

## Code samples (if applicable)
*Include any code samples that should be included in the user-facing documentation.*

## Troubleshooting/Known Issues (if applicable)
*Include any known issues or limitations that may affect how the feature/process works. For example:*
"This only works in 5.19, and is not compatible with macOS."
```

Once your PR is submitted, there's a review process that includes an editorial review, a PM review, and sometimes a dev review. During the editorial review, editors may make punctuation and/or terminology changes and commit them to save time on the review process. This only applies to punctuation/terminology - content suggestions and questions will follow the usual review and discussion process.

Once the review is complete, we'll move your contribution to the appropriate part of [docs.mattermost.com](https://docs.mattermost.com) (if it's not there already) and then merge it. We'll share the URL and you can edit it at any time if you need to.
