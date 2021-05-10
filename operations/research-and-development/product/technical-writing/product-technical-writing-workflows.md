# Technical Writing Workflows

The team uses different branching strategies for day-to-day, staging, and release documentation for documentation in the [docs repo](https://github.com/mattermost/docs).

## General workflow

This process applies to general work, such as ad-hoc editing and adding new content/pages to the docs.

### Adding new content

1. Create a branch off `master`.
2. Navigate to the directory you're working in.
3. Select **Add file > Create new file**.
4. Give your file a name with the file format as `.rst`.
5. Edit your file.
6. When you're finished, add an optional description of your change.
7. Optionally, rename your branch.
8. Select **Commit new file**.
9. On the following page, enter a helpful title for the pull request (this adds immediate context for reviewers)..
10. Then select reviewers and add labels.
11. Finally, select **Create pull request**.
12. You can find your PR under the **Pull requests** tab in GitHub.

Shortly after you open your PR, you'll be alerted that the preview is available to view. This preview is linked to the PR and shows only these changes. Select the link provided to view the preview, validate links, and review formatting.

### Editing content

1. Create a branch off `master`.
2. Navigate to the directory you're working in.
3. Select the pencil icon to open the file for editing.
4. Edit the file.
6. When you're finished, add an optional description of your change and optionally, rename your branch.
7. Select **Commit changes**.
8. On the following page, enter a helpful title for the pull request (this adds immediate context for reviewers).
9. In the description box, provide a navigation outline for reviewers to make it easier for them to navigate to the changes.
10. Then select reviewers and add labels.
11. Finally, select **Create pull request**.
12. You can find your PR under the **Pull requests** tab in GitHub.

Shortly after you open your PR, you'll be alerted that the preview is available to view. This preview is linked to the PR and shows only these changes. Select the link provided to view the preview, validate links, and review formatting.

## Staging workflow

This process applies to large documentation projects that use a staging branch for testing and previews prior to merge.

#### What is the staging branch?

The `staging` branch is a branch off `master` where changes for long-running projects are made, previewed, and tested before being pushed to prod.

#### How do I work in the staging environment?

If you're editing content in the `staging` branch, you'll create a new branch off the `staging` branch for your changes. You're able to view a preview of your changes in your PR. When your PR is reviewed and approved, it's merged into the `staging` branch by one of the technical writers and is then visible in that branch's preview. Eventually, once all the change branches are merged into the `staging` branch and the project is approved, it's merged into `master`.

#### How does the staging branch stay aligned with master?

The `staging` branch automatically checks for changes in `master` and provides a prompt to update when changes are detected. Once `staging` is updated, any branches off `staging` will also display a prompt to **Update branch**. In most cases there shouldn't be any merge conflicts but if there are, please read the Merge conflicts section.

#### Creating a staging branch

Create a branch off `master` called `staging`.

#### Creating new content in staging

1. Switch to the `staging` branch.
2. Navigate to the directory you're working in.
3. Select **Add file > Create new file**.
4. Give your file a name with the file format as `.rst`.
5. Edit your file.
6. When you're finished, add an optional description of your change.
7. Optionally, rename your branch.
8. Select **Commit new file**.
9. On the following page, enter a helpful title for the pull request.
10. Then select reviewers and add labels.
11. Add the label `staging` to your PR.
12. In most cases, staging work is in progress so you can also add the `Work in progress` label.
13. Finally, select **Create pull request**.
14. You can find your PR under the **Pull requests** tab in GitHub.

### Editing content in staging

1. Switch to the `staging` branch.
2. Navigate to the directory you're working in.
3. Select the pencil icon to open the file for editing.
4. Edit the file.
5. When you're finished, add an optional description of your change and optionally, rename your branch.
6. Ensure that you select the option to **Create a new branch** - do not commit directly to the `staging` branch.
7. Select **Commit changes**.
8. On the following page, enter a helpful title for the pull request (this adds immediate context for reviewers).
9. In the description box, provide a navigation outline for reviewers to make it easier for them to navigate to the changes.
10. Then select reviewers and add labels.
11. Finally, select **Create pull request**.
12. You can find your PR under the **Pull requests** tab in GitHub.

Shortly after you open your PR, you'll be alerted that the preview is available to view. This preview is linked to the PR and shows only these changes. Select the link provided to view the preview, validate links, and review formatting.

## Merge conflicts

TODO

## Release documentation workflow

This process applies to release documentation.

#### Creating new content in staging

1. Switch to the `vx.xx Documentation` branch.
2. Navigate to the directory you're working in.
3. Select **Add file > Create new file**.
4. Give your file a name with the file format as `.rst`.
5. Edit your file.
6. When you're finished, add an optional description of your change.
7. Optionally, rename your branch.
8. Select **Commit new file**.
9. On the following page, enter a helpful title for the pull request.
10. Then select reviewers and add labels.
11. Finally, select **Create pull request**.
12. You can find your PR under the **Pull requests** tab in GitHub.

### Editing content for a release

1. Switch to the `vx.xx Documentation` branch.
2. Navigate to the directory you're working in.
3. Select the pencil icon to open the file for editing.
4. Edit the file.
5. When you're finished, add an optional description of your change and optionally, rename your branch.
6. Ensure that you select the option to **Create a new branch** - do not commit directly to the `vx.xx Documentation` branch.
7. Select **Commit changes**.
8. On the following page, enter a helpful title for the pull request (this adds immediate context for reviewers).
9. In the description box, provide a navigation outline for reviewers to make it easier for them to navigate to the changes.
10. Then select reviewers and add labels.
11. Finally, select **Create pull request**.
12. You can find your PR under the **Pull requests** tab in GitHub.
