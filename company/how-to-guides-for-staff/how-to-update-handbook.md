# How to update the handbook

## Who can update update the Handbook?

Contributions from everyone, from staff members to community members, are welcome. You don't have to work at Mattermost to submit an update or fix something that's caught your eye.

## How do I know what to update?

"Update the Handbook" is a term we use regularly at Mattermost but it's not always obvious exactly what to update or how. Here are some examples of what a Handbook update could be:

* Updating your team page with new team members and AORs.
* Adding a new page to describe a new process.
* Updating existing content to accommodate a change in process, policy, or requirement.
* Archiving old content that should be preserved for reference.

Updating the Handbook can be as easy as fixing a typo, or as complex as reorganizing an entire section. The key is to update it regularly, so that updates are less daunting and time-consuming.

## Hints and tips

The Handbook is a public-facing body of work and although it's a constantly-evolving work-in-progress, we still need to ensure our content is accurate, easy to read, and clear.

* **Be concise:** Say what's essential, not more.
* **Get feedback:** Have someone from your target audience read your draft to share feedback so you can [savor surprises](../about-mattermost/mindsets.md#savor-surprises).
* **Don't aim for perfection:** Our goal is regular iteration and so your content doesn't have to be perfect before it's published. It will be reviewed by an editor prior to publication so any major errors will be addressed then.

## Getting started

If this is your first time contributing to Mattermost, first read the [Mattermost Contributor Agreement](https://mattermost.com/mattermost-contributor-agreement/) and sign it \(at the bottom of the page\), so you can be added to the Mattermost [Approved Contributor List](https://docs.google.com/spreadsheets/d/1NTCeG-iL_VS9bFqtmHSfwETo5f-8MQ7oMDE5IUYJi_Y/pubhtml?gid=0&single=true). Please ensure the **GitHub username** field matches your GitHub username exactly, including capitalization.

Then, please request access to the Mattermost organization [Team:Release Channel](https://community.mattermost.com/private-core/channels/team-release). This means that you can edit the files in the Handbook repo and not have to create a fork for your changes.sssss

Now you're ready to get started.

### Editing an existing page

When you edit an existing page, it's usually to add content, remove content, or edit existing content. In general it's easiest if pages are edited directly, although you're also welcome to edit files directly from the repo if that's easier for you.

All editing is done in GitHub, as that's where the Handbook files are stored. Pages are formatted using Markdown - if you're not familiar with Markdown, you can take a look at [this page](https://docs.mattermost.com/messaging/formatting-text.html) for tips. Don't worry too much about formatting - it can always be adjusted during the review process.

Once a page is edited and you're happy with the changes, it's submitted as a pull request which is then reviewed. If there's any feedback or comments have been made, you'll be alerted. If suggestions have been made, you can choose to commit them (add them to your content) or you can ask the reviewer for more information before doing that.

When the PR is approved, it'll be merged and published. If you have more changes to make, you can simply repeat the process.

#### Editing a page directly

This is probably the quickest way to make changes, as it doesn't require you to find the file in the repo first.

1. Open the Handbook and navigate to the page you want to edit.
2. Select **Edit on GitHub** in the top right navigation. This opens the page in GitHub.
4. In GitHub select the pencil icon in the navigation bar \(above the page header\) called **Edit this file** to open the editable Markdown-format page. If you see **Edit this file in your fork of this project** the process is the same, it just means you're not part of the Mattermost organization and are working in a forked repo.
   * To learn more about Markdown formatting, see the [Mattermost guide for formatting text](https://docs.mattermost.com/messaging/formatting-text.html), or [the guide from GitBook](https://docs.gitbook.com/editing-content/markdown).
5. Make your edits. When you're ready to submit your changes, scroll to the bottom of the page to commit your changes and start a pull request.
6. Add a descriptive title if the default title isn't sufficient. Add an extended description to summarize the changes you've made.
7. The default setting is **Create a new branch for this commit and start a pull request**. In the field below that, you can customize the branch name - you can also leave it as default.
8. Select **Propose changes**.
9. On the next page, you can scroll down to compare changes with the original document to double-check your changes. 
10. If you're happy with them confirm that the title and description are correct, then select **Create pull request**.

Once a pull request has been submitted, a core committer with write-access assigns relevant reviewers and labels to kick off the review process. The review process includes aligning the content with the Style Guide, validating the changes, and tagging any other relevant committers.

Multiple committers may comment on your pull request and provide edits or suggestions which you can commit directly. You can also add line comments. Take a look at [Commenting on pull requests](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/commenting-on-a-pull-request) for more details.

Once the review process is complete, the change is merged and pushed live. We recommend that you review your changes at [https://handbook.mattermost.com](https://handbook.mattermost.com) for potential formatting errors.

#### Editing a file in the repo

This option works best if you know where the file is located in the repo.

1. Open the [Handbook repo](https://github.com/mattermost/mattermost-handbook).
2. Navigate through the directories to the file you want to edit.
3. Once you've found the file, select **Edit this file** in the top corner. If you see **Edit this file in your fork of this project** the process is the same, it just means you're not part of the Mattermost organization and are working in a forked repo.
   * To learn more about Markdown formatting, see the [Mattermost guide for formatting text](https://docs.mattermost.com/messaging/formatting-text.html), or [the guide from GitBook](https://docs.gitbook.com/editing-content/markdown).
5. Make your edits. When you're ready to submit your changes, scroll to the bottom of the page to commit your changes and start a pull request.
6. Add a descriptive title if the default title isn't sufficient. Add an extended description to summarize the changes you've made.
7. The default setting is **Create a new branch for this commit and start a pull request**. In the field below that, you can customize the branch name - you can also leave it as default.
8. Select **Propose changes**.
9. On the next page, you can scroll down to compare changes with the original document to double-check your changes. 
10. If you're happy with them confirm that the title and description are correct, then select **Create pull request**.

## Creating new content

Creating new content can take the form of a new page, or an entirely new section. Some things to keep in mind are naming conventions and that the Table of Contents entry is made manually in the SUMMARY.md file.


### Creating a new page

1. Open the [Handbook repo](https://github.com/mattermost/mattermost-handbook).
2. Navigate through the directories until you reach the section where you'd like to add your new content.
3. Select **Add file > Create new file**.

  When you create a new page in the Handbook ensure that:

  * The page name is all lowercase
  * There are hyphens instead of spaces between the words.
  * New page names end with `.md`.

4. Write your content as needed.
5. When you're ready to submit your changes, scroll to the bottom of the page to commit your changes and start a pull request.
6. Add a descriptive title if the default title isn't sufficient. Add an extended description to summarize the changes you've made.
7. The default setting is **Create a new branch for this commit and start a pull request**. In the field below that, you can customize the branch name - you can also leave it as default.
8. Select **Propose changes**.
9. On the next page, you can scroll down to compare changes with the original document to double-check your changes. 
10. If you're happy with them confirm that the title and description are correct, then select **Create pull request**.
11. Add your new page to the [Handbook table of contents](https://github.com/mattermost/mattermost-handbook/blob/0.2.1/SUMMARY.md). If you plan to reorder the table of contents as part of your change, please tag @jason.blais or @justine.geffen in Mattermost \(@jasonblais or @justinegeffen in GitHub\) as a redirect may need to be set up to accommodate the change.

[Watch a two-minute training video on how to create a new page in GitHub](https://drive.google.com/file/d/12JUpEdP3uU_bPxDVWdlEZv65v1tttlQn/view?usp=sharing).

### Creating a new folder

If you want to create nested content, you can create folders. You cannot create an empty folder and then add files to that folder, but rather creation of a folder must happen together with adding of at least a single file. On GitHub you can do it this way:

1. Navigate to the folder within which you're creating your new folder.
2. Select **Add file > Create new file**.
3. Enter the new folder's name in the text field and add `/` at the end.
4. In the next text box, enter the name of the new page, ending with `.md`.
5. When you're ready to submit your changes, scroll to the bottom of the page to commit your changes and start a pull request.
6. Add a descriptive title if the default title isn't sufficient. Add an extended description to summarize the changes you've made.
7. The default setting is **Create a new branch for this commit and start a pull request**. In the field below that, you can customize the branch name - you can also leave it as default.
8. Select **Propose changes**.
9. On the next page, you can scroll down to compare changes with the original document to double-check your changes. 
10. If you're happy with them confirm that the title and description are correct, then select **Create pull request**.
11. Add your new section to the [Handbook table of contents](https://github.com/mattermost/mattermost-handbook/blob/0.2.1/SUMMARY.md). If you plan to reorder the table of contents as part of your change, please tag @jason.blais or @justine.geffen in Mattermost \(@jasonblais or @justinegeffen in GitHub\) as a redirect may need to be set up to accommodate the change.

## Frequently Asked Questions

### How do I format a page?

All Handbook pages are written in Markdown, which is also the language used to post messages in Mattermost. To learn more about Markdown formatting, see the [Mattermost guide for formatting text](https://docs.mattermost.com/messaging/formatting-text.html), or [the guide from GitBook](https://docs.gitbook.com/editing-content/markdown).

### How do I update the left-hand navigation?

You can update the left-hand navigation in the [SUMMARY.md](https://github.com/mattermost/mattermost-handbook/blob/0.2.1/SUMMARY.md) file.

**Important note:**

GitBook dynamically changes the URL based on the location in the table of contents. This means that when a page changes its location, the previous link results in a 'page not found' error.

There is a redirect file that we use to prevent this in the `gitbook.yaml` file. Please mention @jason.blais or @justine.geffen in Mattermost \(@jasonblais or @justinegeffen in GitHub\) for assistance if needed.

### How do I add an image to the documentation?

Follow these two steps:

* Go to the [/assets](https://github.com/mattermost/mattermost-handbook/tree/0.2.1/.gitbook/assets) folder, select **Upload files**, then upload the image files you want to add to your documentation. Make sure to have a clear name for each file you upload.
* Next, go to the section you want to add an image to and include the following Markdown formatting:

  ```text
  ![](../../../.gitbook/assets/release-timeline-jan2020.png)
  ```

## Training video

[Watch a training video on how to update the handbook in GitHub](https://drive.google.com/file/d/1AOI8H-oe2u1JW6oOA4nPPTSbGnK3Xuq1/view?usp=sharing).

## Approved reviewers and permissions

Below is a list of approved reviewers.

1. @jasonblais, @justinegeffen: Reviews major changes to handbook.mattermost.com, such as updates to the Table of Contents \(SUMMARY.md\).
2. @justinegeffen, @amyblais, @cwarnermm: Editor reviews of all submitted PRs for correct grammar and consistent style.
3. @kevinfayle: Signs off on changes to [marketing ops and analytics](https://handbook.mattermost.com/operations/messaging-and-math/demand-generation-reporting).
4. @aedott: Signs off on changes to [messaging and math](https://handbook.mattermost.com/operations/messaging-and-math).
5. @TQuock: Signs off on changes to [finance](https://handbook.mattermost.com/operations/finance).
6. @natalie-hub: Signs off on changes to [workplace](https://handbook.mattermost.com/operations/workplace).
7. @it33: Signs off on changes to signing authority \([example](https://github.com/mattermost/mattermost-handbook/pull/60)\).
8. @dschalla: Signs off on changes to [Security](https://handbook.mattermost.com/operations/security).

Each PR should be reviewed by at least one approved reviewer. A build check requiring at least one approved review prior to a merge is planned, similar to other Mattermost repositories.

Below is a list of permissions handbook contributors have access to:

1. @jasonblais, @justinegeffen, @amyblais, @cwarnermm: Write permissions to the repository.
2. Staff contributors: Submit changes to handbook.mattermost.com via PRs. May have access to request reviews, add labels, submit PR reviews, and be requested as reviewers.
3. Non-staff contributors: Submit changes to handbook.mattermost.com via PRs. Do not have access to request reviews, add labels. Can submit PR reviews.
