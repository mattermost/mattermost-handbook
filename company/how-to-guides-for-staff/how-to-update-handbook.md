# How to Update the Handbook

## Guidelines

* **Be concise:** Say what is essential, not more. 
* **Get feedback:** Have someone from your target audience read your draft to share feedback so you can [savor surprises](../about-mattermost/mindsets.md#savor-surprises).

## Steps

### Getting Started

The quickest way to begin is navigating to the page you want to edit in [Mattermost Handbook](https://handbook.mattermost.com/), then clicking the **Edit on GitHub** icon in the top right navigation. This opens the page in GitHub that you can edit.

If this is your first time contributing to Mattermost, first read the [Mattermost Contributor Agreement](https://www.mattermost.org/mattermost-contributor-agreement/) and sign it \(at the bottom of the page\), so you can be added to the Mattermost [Approved Contributor List](https://docs.google.com/spreadsheets/d/1NTCeG-iL_VS9bFqtmHSfwETo5f-8MQ7oMDE5IUYJi_Y/pubhtml?gid=0&single=true).

### Editing an Existing Page

After you have opened the page you want to edit in GitHub, click the **Edit** pencil icon in the top right corner.

This opens a Markdown formatted document of the page. To learn more about Markdown formatting, see the [Mattermost guide for formatting text](https://docs.mattermost.com/help/messaging/formatting-text.html), or [the guide from GitBook](https://docs.gitbook.com/editing-content/markdown).

### Creating a Pull Request

When you're ready to submit your changes, scroll to the bottom of the page to commit your changes.

Add a descriptive title and comments to summarize the changes made, then select **Create a new branch for this commit and start a pull request**.

After this, click the **Propose file change** button.

![](../../.gitbook/assets/how-to-update-handbook-commit-changes.png)

Scroll down to compare changes with the original document, request **Reviewers** on the top right navigation, select relevant labels for the pull request, then select **Create pull request**. 

![](../../.gitbook/assets/how-to-update-handbook-create-new-pull-request.png)

### Commenting on a Pull Request

Once a pull request is submitted, multiple committers may comment on it and provide edits or suggestions which you can commit directly. You can also add line comments. Take a look at [Commenting on pull requests](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/commenting-on-a-pull-request) for more details.

### Reviewing a Pull Request

Once a pull request has been submitted and the correct labels assigned, the review process begins. This includes aligning the content with the Style Guide, validating processes, and tagging any other relevant committers.

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
