# How to update handbook

## Guidelines

* **Be concise:** Say what is essential, not more. 
* **Get feedback:** Have someone from your target audience read your draft to share feedback so you can [savor surprises](../about-mattermost/mindsets.md#savor-surprises).

## Steps

If this is your first time contributing to Mattermost, first read the [Mattermost Contributor Agreement](https://www.mattermost.org/mattermost-contributor-agreement/) and sign it \(at the bottom of the page\), so you can be added to the Mattermost [Approved Contributor List](https://docs.google.com/spreadsheets/d/1NTCeG-iL_VS9bFqtmHSfwETo5f-8MQ7oMDE5IUYJi_Y/pubhtml?gid=0&single=true). Please ensure the **GitHub username** field matches your username exactly on GitHub, including capitalization.

### Editing an Existing Page

1. The quickest way to begin is navigating to the page you want to edit in [Mattermost Handbook](https://handbook.mattermost.com/), then clicking the **Edit on GitHub** icon in the top right navigation. This opens the page in GitHub that you can edit.
2. In GitHub click the pencil icon in the navigation bar \(above the page header\) called **Edit the file in your fork of this project** to open the editable Markdown format page. 
3. To learn more about Markdown formatting, see the [Mattermost guide for formatting text](https://docs.mattermost.com/help/messaging/formatting-text.html), or [the guide from GitBook](https://docs.gitbook.com/editing-content/markdown).
4. Make your edits. When you're ready to submit your changes, scroll to the bottom of the page to commit your changes and start a pull request.
5. Add a descriptive title if the default title isn't sufficient. Add an extended description to summarize the changes you've made.
6. Click the **Propose file change** button.

![](../../.gitbook/assets/how-to-update-handbook-commit-changes.png)

1. On the next page, scroll down to compare changes with the original document and then select **Create pull request**.
2. Confirm that the title and description are correct. Then select **Create pull request**.

![](../../.gitbook/assets/how-to-update-handbook-create-new-pull-request.png)

Once a pull request has been submitted, a core committer with write-access assigns relevant reviewers and labels to kick off the review process. The review process includes aligning the content with the Style Guide, validating the changes, and tagging any other relevant committers.

Multiple committers may comment on your pull request and provide edits or suggestions which you can commit directly. You can also add line comments. Take a look at [Commenting on pull requests](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/commenting-on-a-pull-request) for more details.

Once the review process is complete, the change is merged and pushed live. We recommend that you review your changes at [https://handbook.mattermost.com](https://handbook.mattermost.com) for potential formatting errors.

## Frequently Asked Questions

### How do I format a page?

All Handbook pages are written in Markdown, which is also the language used to post messages in Mattermost. To learn more about Markdown formatting, see the [Mattermost guide for formatting text](https://docs.mattermost.com/help/messaging/formatting-text.html), or [the guide from GitBook](https://docs.gitbook.com/editing-content/markdown).

### How do I create a new page?

Creating a new page follows the same process as above, with two exceptions:

* Navigate to that section of the handbook where you'd like to add the new page and select **Create new file**.
* Add your new page to the [Handbook table of contents](https://github.com/mattermost/mattermost-handbook/blob/0.2.1/SUMMARY.md).

![](../../.gitbook/assets/how-to-update-handbook-create-new-file.png)

### How do I update the left-hand navigation?

You can update the left-hand navigation in the [SUMMARY.md](https://github.com/mattermost/mattermost-handbook/blob/0.2.1/SUMMARY.md) file.

### How do I add an image to the documentation?

Follow these two steps:

* Go to the [/assets](https://github.com/mattermost/mattermost-handbook/tree/0.2.1/.gitbook/assets) folder, click **Upload files**, then upload the image files you want to add to your documentation. Make sure to have a clear name for each file you upload.
* Next, go to the section you want to add an image to and include the following Markdown formatting:

  ```text
  ![](../../../.gitbook/assets/release-timeline-jan2020.png)
  ```

## Training Video

[Watch a training video on how to update the handbook in GitHub](https://drive.google.com/file/d/1AOI8H-oe2u1JW6oOA4nPPTSbGnK3Xuq1/view?usp=sharing).

## Approved Reviewers and Permissions

Below is a list of approved reviewers.

1. @jasonblais: Reviews major changes to handbook.mattermost.com, such as updates to the table of contents.
2. @justinegeffen, @amyblais: Editor reviews of all submitted PRs for correct grammar and consistent style.
3. @rbradleyhaas, @michaelschiffmm: Signs off on changes to [business operations](https://handbook.mattermost.com/operations/business-operations).
4. TBD: Signs off on changes to [messaging and math](https://handbook.mattermost.com/operations/messaging-and-math).
5. TBD: Signs off on changes to [finance](https://handbook.mattermost.com/operations/finance).
6. @natalie-hub, @HilaryClarke: Signs off on changes to [workplace](https://handbook.mattermost.com/operations/workplace).
7. @it33: Signs off on changes to signing authority \([example](https://github.com/mattermost/mattermost-handbook/pull/60)\).

Each PR should be reviewed by at least one approved reviewer. A build check requiring at least one approved review prior to a merge is planned, similar to other Mattermost repositories.

Below is a list of permissions handbook contributors have access to:

1. @jasonblais, @justinegeffen, @amyblais: Write permissions to the repository.
2. @rbradleyhaas, @michaelschiffmm: Write permissions to the repository, but are not expected to make changes without reviews outside of [business operations](https://handbook.mattermost.com/operations/business-operations), nor make changes to table of contents without reviews. 
3. Staff contributors: Submits changes to handbook.mattermost.com via PRs. Have access to request reviews, add labels, submit PR reviews, and be requested as reviewers.
4. Non-staff contributors: Submits changes to handbook.mattermost.com via PRs. Have access to request reviews, add labels, and submit PR reviews.

