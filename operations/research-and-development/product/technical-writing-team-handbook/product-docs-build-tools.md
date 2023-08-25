# Product documentation build tools

Mattermost product documentation is built using Sphinx. See the following Mattermost blog articles for an overview of our tools and workflows:

- [An introduction to our tech stack](https://mattermost.com/blog/our-product-documentation-tech-stack/)
- [How we work as a writing team](https://mattermost.com/blog/how-we-work-technical-writing-team/)
- [Sphinx extensions](https://mattermost.com/blog/enhancing-documentation-with-sphinx-extensions/)

## Set up a local development environment

Members of the writing team have two ways to contribute to Mattermost product documentation:

- Using GitHub web tools.
- Working within a local development environment. See the mattermost/docs repository [README](https://github.com/mattermost/docs#building-and-validating) documentation for details on setting up a local environment.

### Clone a documentation fork locally

Mattermost product documentation contributions can be created in one of two ways:

- As a branch (applies only Mattermost staff with appropriate GitHub repository permissions).
- As a fork (applies to all other documentation contributions).

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

## Sitemap generation

1. Open the latest sitemap via `docs.mattermost.com/sitemap.xml` in a browser tab.
2. Generate the product documentation, then use a text compare tool such as [text-compare](https://text-compare.com/) to review the differences between the newly generated sitemap against what's available in production.

You shouldn't see any glaring differences and the sitemap should NOT have any Mattermost version information in any of the URLs. You may see content move around on the page. Confirm that page URLs in production continue to exist in the latest generated sitemap XML file.

## Page redirects

Spot check a handful of redirects specified via the `conf.py` file to ensure they continue to redirect visitors correctly.

## Parallel processing and pickling

When you build the documentation locally, is the build fast? Do you see a message in the terminal indicating that pickling was successful?

If the build takes more than a few minutes to complete, or you don't see the pickling success message, this could indicate an issue with the Sphinx version, and you may want to reconsider an upgrade to this version.

## HTML output

After successfully building the product documentation:

- Navigate around the site to ensure that nothing looks or feels broken.
- Review pages with tables and tabbed content to ensure the content displays as intended.
- Review the landing page as well as subsequent page headers/footers to ensure links take users to expected destinations.
- Review the Changelog pages (which are managed in Markdown source files) to ensure that the changelogs are converted to HTML correctly.
- Perform a few docs searches to confirm that searches continue to work as expected.

## Build warnings and errors

Review and fix issues reported via the `/build/warnings.log` file including broken links, pages missing from the LHS, and syntax and formatting problems. 

### Plan and deloyment support details

Visitors to Mattermost product documentation look for confirmation that a given feature is supported as part of their subscription plan and available in their self-hosted or Cloud-based deployment. This information is placed prominently at the top of every documentation page for easy scanning.

Plan and deployment details can be added to new product documentation pages using the following RST syntax that uses a Sphinx ``include`` directive:

```text
.. include:: ../_static/badges/allplans-cloud-selfhosted.rst
  :start-after: :nosearch:
```

The ``include`` directive points to an RST file, and the file you specify is one of 12 templated files that cover all combinations of plan and deployment support available in the ``/_static/badges`` directory.

**Note:** The ``:start-after`` line is important and shouldn't be omitted. The ``nosearch`` attribute is present in the templated RST files to instruct Sphinx not to return the templated files in search results. The include directive tells Sphinx to hide the ``nosearch`` text present in the templated RST files when publishing the page. 

### Tabbed content

Users visit product documentation looking for a clear, golden path to success. As software complexity grows, the paths to success can become less straightforward and dependent on customer-determined variables like operating systems, databases, and product release versions. 

Organizing product documentation content in selectable tabs is an effective way to reduce clutter and reduce the amount of time readers spend looking for answers. Tabs can display more product information on a page without requiring the user to scroll through an entire page of content, and readers can reach relevant details with just a glance.

Content can be formatted to display in tabs using the following RST syntax:

```text
.. tabs::

	.. tab:: Tab Name A

		Tab text goes here. Users see this content when users visit this page.

	.. tab:: Tab Name B

		Tab text goes here. The user must select this tab to see this content.

	.. tab:: Tab Name C

		Tab text goes here. The user must select this tab to see this content
```

Note that tabbed content syntax applies only to RST source files and is not yet available within Markdown source files, and that spacing and indentation are important elements of the syntax. When previewing draft work, if tabbed content isn't displaying as expected, carefully review spacing and indentation.

When presenting content in tabs, tab names must be exactly the same across all instances, for consistency.

"From Mattermost version 6.0..." vs "In Mattermost versions up to v5.39"

### Return Mattermost configuration settings in search results

The product documentation site returns and prioritizes configuration settings in search results. This is achieved by adding metadata to each configuration settting section in the form of a directive and its options. Please see https://github.com/mattermost/docs/pull/5911 for comprehensive details on how this search engine was designed and implemented in the source code via Sphinx.

This metadata is positioned directly **above** each section header on each config setting docs page, and will look something like this:

```rst
.. config:setting:: web-useletsencrypt
  :displayname: Use Let's Encrypt (Web Server)
  :systemconsole: Environment > Web Server
  :configjson: .ServiceSettings.UseLetsEncrypt
  :environment: MM_SERVICESETTINGS_USELETSENCRYPT
  :description: Enable the automatic retrieval of certificates from Let’s Encrypt.
```

The directive itself needs a unique identifier, such as ``web-useletsencrypt``. The directive's options, including ``displayname``, ``systemconsole``, ``configjson``, ``environment``, and ``description`` essentially duplicates the config setting details. We're doing this so that the config setting details readers want show up on the search results page.

Note that we're currently manually duplicating config details (in this directive metadata as well as the docs content itself), but we'll automate this in the future to ensure only one source of data needs to be maintained. (This manual step is a stepping stone towards that automation approach).

The setting directive supports the following options:

``displayname``: User-friendly text that is displayed as the name of a config setting
``systemconsole``: The location in the System Console of the config setting
``configjson``: The config.json name of the config setting
``environment``: The environment variable for the config setting
``description``: Description of the config setting; can be any length

Note: the ``description`` option also supports basic reStructuredText markup but doesn't support nested directives within that option.

When documenting a new Mattermost configuration setting, ensure you add and populate the metadata in the source file to ensure the config setting can be returned in search results. Missing metadata will result in missing search results. The configuration settings source files contain many examples to work from.

### Archive documentation pages

When a documentation page is no longer needed, that page should be archived. Archiving a page prevents that page from being included in the build altogether.

To archive a documentation page:

1. Identify where you want the reader to go instead of the page that's being archived.
2. Move the source file to the `/source/archive` folder.
3. (RST files only) In the file you just moved to the `archive` folder, add `:nosearch:` at the top of the file (above any anchor identifier, title, or code comment present in the file). This prevents the documentation page from being returned in search results.
4. Add a redirect to the `conf.py` file from the archived page to a new destination page.
5. Search for and replace any links across the documentation set to the archived file, including LHS, landing pages, and paragraph-level links.

### Silence `not in toctree` build warnings

When working and building the documentation locally in a development environment, writers can review build warnings and errors in the `/build/warnings.log` file. Build warnings and errors can include (but aren't limited to):

- Broken links
- Documentation pages missing from the LHS unintentionally
- Syntax and formatting issues

As part of monthly documentation release cycles, technical writers review and take action on build warnings and errors reported.

To silence warnings for RST documentation pages that are missing from the LHS unintentionally, add `:orphan:` at the top of the file (above any anchor identifier, title, or code comment present in the file). The next time the product documentation is built, that warning is silenced. (A documentation page can contain both `:nosearch:` and `:orphan:`, and these two directives can be listed in either order).

### Stop a documentation page from being returned in search results

Some documentation pages should never be returned in search results, including:

- Archived pages.
- Unofficial documentation pages. All unofficial product documentation should live within the [Mattermost Discussion Forums](https://forum.mattermost.com/c/docs/37).
- Pages that exist only to be included on other documentation pages. These pages often don't provide enough context to be useful if accessed directly.

To prevent RST documentation pages from being returned in search results, add `:nosearch:` at the top of the file (above any anchor identifier, title, or code comment present in the file. (A documentation page can contain both `:nosearch:` and `:orphan:`, and these two directives can be listed in either order).

### Add code comments

Adding code comments to documentation source files helps contributors understand why specific decisions were made or what additional knowledge is required when working within a specific source file. For example, if a documentation page isn't accessible in the LHS by design, adding a code comment in the source file helps future contributors understand that it was an intentional decision.

In RST files, format code comments as `.. Code comment text here`. Code comment text isn't visible to users in the published product documentation.

### Embed videos in product documentation

To accommodate the many ways that people learn, its helpful to include visual elements, such as videos, in the Mattermost product documentation. The process and code needed to embed a video on a documentation page differs depending on how the video is hosted. Mattermost typically hosts product videos through either YouTube or Wistia (and Wistia is preferrable over YouTube, when available, because viewers aren't subject to ads).

#### Embed a YouTube video on a page

1. Obtain the YouTube video link.
2. The code to embed the video consists of two parts: a paragraph-level link and iframe code. Copy the code below into the documentation source file, then update the introduction text and replace the `YouTubeVideoLink`.

```text
See our `tutorial video on YouTube <https://www.youtube.com/watch?v=YouTubeVideoLink>`_. 

.. raw:: html

   <div style="position: relative; padding-bottom: 50%; height: 0; overflow: hidden; max-width: 100%; height: auto;">
      <iframe src="https://www.youtube.com/embed/YouTubeVideoLink" frameborder="0" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 95%;"></iframe>
   </div>
```

#### Embed a Wistia video on a page

1. Request the [Wistia inline embedded code snippet](https://wistia.com/support/embed-and-share/media-on-your-website#inline-embeds) from the video producer. 
2. Copy and paste the code you receive into the documentation source file. The code you receive will look similar to the following example:

```text
.. raw:: html

  <script src="https://fast.wistia.com/embed/medias/5gjgi10rr0.jsonp" async></script><script src="https://fast.wistia.com/assets/external/E-v1.js" async></script><div class="wistia_responsive_padding" style="padding:56.25% 0 0 0;position:relative;"><div class="wistia_responsive_wrapper" style="height:100%;left:0;position:absolute;top:0;width:100%;"><div class="wistia_embed wistia_async_5gjgi10rr0 videoFoam=true" style="height:100%;position:relative;width:100%"><div class="wistia_swatch" style="height:100%;left:0;opacity:0;overflow:hidden;position:absolute;top:0;transition:opacity 200ms;width:100%;"><img src="https://fast.wistia.com/embed/medias/5gjgi10rr0/swatch" style="filter:blur(5px);height:100%;object-fit:contain;width:100%;" alt="" aria-hidden="true" onload="this.parentNode.style.opacity=1;" /></div></div></div></div>
```

### Plan and deployment badges

Most Mattermost product documentation pages feature plan and deployment badges located directly under the page title or section title. These badges indicate:

- The Mattermost subscription plans that support the feature or function. Options include **All Plans**, **Enterprise**, and **Professional**.
- The Mattermost deployment approach that supports the feature or function. Options include **Cloud** or **Self-hosted**.

These badges are defined on a per-page basis as inline images located close to the top of the source file. Please be careful to avoid making changes to the badge code when modifing other aspects of the documentation page.

Note that, longer term, it would be ideal to replace the current badge implementation with a more programmatic solution where the badges are defined once and simply referenced across all applicable documentation pages.

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

### Add PRs to monthly documentation release branches

If you encounter a documentation PR that should be included in a monthly documentation release cycle, instead of tracking the PR individually, the PR can be merged into a documentation release branch. 

1. In the PR, identify the branch name you want to include in a documentation release branch. 
2. Ensure your local development environment is up-to-date and contains the same code as the `master` branch.
3. Navigate into the branch where you want to merge in the PR to ensure all code is available locally.
4. From a terminal, run the command `git merge branchname` where `branchname` is the name of the branch you want to commit to a monthly documentation release.
5. If there are no conflicts, you'll see the vi editor. Review the commit message, then type `:x` to save and exit. If there are conflicts, you need to resolve them on the CLI and commit them first before you can move to the next step to push remotely.
6. Push your changes remotely by running the command `git push`.

## Manage and resolve merge conflicts

Mattermost hosts the source code and content of its technical documentation in GitHub repositories. Documentation is updated by submitting pull requests on GitHub. After a pull request is reviewed and approved, it is usually merged into the master branch without further changes. Sometimes, however, conflicts between the files being updated and the master branch must be resolved.

GitHub flags conflicting regions of a file with these characters: `<<<<<<<`, `=======`, and `>>>>>>>`. The block of text between `<<<<<<<` and `=======` is the content that the pull request is attempting to merge. The block of text between `=======` and `>>>>>>>` is the block of text from the master branch that conflicts with the content in the pull request. Resolving a conflict may require removing content that has been updated in the pull request, or manually integrating text from the pull request. **The flag characters must also be removed.**

After resolving the conflicts in a given file, mark it as resolved in GitHub. All conflicts must be resolved for the merge to proceed.

The image below shows a section of a file with a merge conflict:

[](https://user-images.githubusercontent.com/74422101/211895979-255e4988-82de-40e9-97dd-5da97b1d98c9.png)

The lines between `<<<<<<< issue-5951-authentication-oauth-ms` and `=======` are from the pull request. The lines between `=======` and `>>>>>>> master` are from the master branch. In this case, metadata had been added to the same region of the file that was edited in the pull request. In order to resolve the conflict, the text from the pull request and the metadata were kept, while part of the text from the master branch was removed.

## Using ReStructuredText markup \(rst\)

The reStructuredText specification allows for a certain degree of flexibility in markup to achieve your goals. For example, you can use any one of more than a dozen characters for section title underlines, and you have the option of using an overline in addition to an underline.

The majority of Mattermost technical documentation is written in `.rst`. The examples below describe the conventions we use when writing in `.rst`.

### Page titles

Underline page titles using `=`, with no overline. Underlines should be as long as the title text.

```text
  Document Title
  ==============
```

### Section titles

Underline using `-` for section titles.

```text
  Section title
  -------------
```

Underline subsections using `~` for the first subsection level, and `^` for the second subsection level.

```text
  Subsection one
  ~~~~~~~~~~~~~~

  Subsection two
  ^^^^^^^^^^^^^^
```

### Table of contents

Insert a table of contents into a document using the following format:

```text
  .. contents::
      :backlinks: top
```

### Text formatting

Use highlighting of text to visually set off words and phrases that are important to readers. Content that should be highlighted includes file names, UI controls, and window titles. The following table has a comprehensive list with examples.

| Text | Format | Example |  |
| :--- | :---: | :--- | :--- |
| Commands | `````monospace`````  | "At the command line, type `sudo apt-get install nginx`." |  |
| Directory name | `````monospace`````  | `/opt/mattermost` |  |
| File name | `````monospace`````  | `config.py` |  |
| Inline code | `````monospace`````  | `fmt.Printf("2 times %d = %d\n", x, y )` |  |
| Keystrokes | `````monospace`````  | "Type `https://` in the string field." |  |
| Screen output | `````monospace`````  | See :ref:`literal-blocks` for an example. |  |
| Parameter values | `````monospace`````  | "Set the _auto-config_ parameter to `false`" |  |
| Field names | `**bold**` | If the field has punctuation, include that in the formatting. For example "Enter the URL in the **Enter URL:** field." |  |
| Clickable control | `**bold**` | "Click **File &gt; Save**." |  |
| UI elements | `**bold**` | "Open **Main Menu &gt; Account Settings**." |  |
| Dialog boxes | `**bold**` | "The **Create Thread** window opens." |  |
| Citations | `*italic*` | "Read the book _Clean Code_ by Robert Martin." |  |
| User account names | `*italic*` | "Log in to the _mysql_ account." |  |
| Parameter names | `*italic*` | "Set the _auto-config_ parameter to `false`" |  |
| Keyboard buttons | Key1+Key2 | "Press CTRL+U to upload a file." |  |
| Placeholder field | {placeholder} | "Use the URL in the form of {hostname}.mattermost.com/{team}." |  |

### Bullet lists

For bullet lists and sublists, use `-` before the list item.

```text
  - list item one
  - list item two
    - sublist item one
    - sublist item two
  - list item three
```

### Numbered lists and procedure steps

Create numbered lists and procedure steps using numbers for the top-level list and lowercase alpha characters for the first nested list.

```text
  1. This is item one.
  2. This is item two.

    a. This is nested item one.
    b. This is nested item two.

  3. This is item three.
```

### Name-value groups

Use a name-value group instead of a hand-created list.

A name-value group is typically a group of terms and their corresponding definitions, but can also be questions and answers, topics and values, or other name-value groups. In HTML output, a name-value group is represented as a definition list.

Preferred
  Total Users
    The total number of active accounts created on your system. Excludes inactive accounts.
  Total Teams
    The total number of teams created on your system.

Avoid
  **Total Users:** The total number of active accounts created on your system. Excludes inactive accounts.

  **Total Teams:**  The total number of teams created on your system.

To create a name-value group such as a definition list, type the term on a line by itself. On the next line, indent the definition.

```
  Total users
    The total number of active accounts created on your system. Excludes inactive accounts.
  Total teams
    The total number of teams created on your system.
```

### Documentation links 

#### External links

External links take readers to a page outside of the Mattermost product documentation. External link URLs are automatically rendered as links in Sphinx (when formatted correctly). Where possible, incorporate hyperlinks within the text of a sentence by lowercasing the link text. 

External hyperlinks within a sentence can be created using the following formatting:

```text
`Link display text <URL-of-website>`__

For example:
  `Mattermost Product Pricing <https://www.mattermost.com/pricing/>`__
```

Note the full URL, the opening and closing single quotes, and the two underline characters at the end of the link syntax.

The link above renders as: [Mattermost Product Pricing](https://www.mattermost.com/pricing).

#### Internal links

Internal links take readers to a page within the Mattermost product documentation. When creating links to pages in the product documentation, always use a relative URL instead of an external (or absolute) link. A link with an absolute URL is not as flexible as a relative URL. Relative URLs don't break when the documentation is moved to another host, or if the documentation is hosted on a server that's behind a firewall without access to the Internet.

##### Link to another page in the same section

To create a link to another documentation page within the same section of the product documentation, use the following formatting:

```text 
:doc:`Link display text </folder/filename>`

For example, when you want to add a link on a Channels page to another Channels page:
  See the :doc:`channel preferences </channels/set-channel-preferences>` documentation for details.
```

Notes: 

- The file extension is not part of the syntax, and that two underline characters are missing. Sphinx uses the title of the document as the link text.
- If you're looking to create an internal link to a section on another page (as opposed to creating a link to the top of a page in general), the syntax above won't work. Docs is investigating further to identify a solution.

In Sphinx, references are constructed using roles, and roles point to locations in the documentation set. The two roles that are relevant in Mattermost documentation are the `:doc:` role and the `:ref:` role. In both cases, the HTML output is a relative URL for the target location.

- The `:doc:` role is used for creating relative links to other documents. 
- The `:ref:` role is used for creating relative links to arbitrary locations within the documentation set, including within the same document, based on a unique identifier specified at the top of a source file. The `:ref:` role is a two-part construct. One part is the link itself, and the other part is the target on the source page.

  - The link itself is specified as: :ref:`arbitrary-text-label`
  - The target is added as the first line of the source page (preceding the title): `.. _arbitrary-text-label:`

##### Link to a section heading on the current page

To create a link to a section heading on the current page, identify the unique anchor ID assigned to the section title in a local build, a remote build, or within production, then use the following formatting:

```text
`Link display text <#uniqueanchorID>`__
```

### Bullet lists
```

To generate a link to the section, use the `:ref:` role as follows:

```text
  For more information about bullet lists, see :ref:`arbitrary-text-label`.
```

The Sphinx processor creates a relative link to the section, and uses the section title as the link text. On output, the link looks like this: "For more information about bullet lists, see :ref:`arbitrary-text-label`."

### Images

Use the following construct to insert an image:

```text
  .. image:: ../images/choices.png
```

You should use `alt` tag for all images.

You can also add the following image options: `height`, `width`, `scale`, `align`, and `target`.

```text
  .. image:: ../images/choices.png
    :alt: The choices that you can make.
    :height: 100px //number refers to pixels
    :width: 200px //number refers to pixels
    :align: left //left, right or middle
    :scale: 50 //number is a percentage
```

Inserting an inline image is a bit more complicated. It's a two-part construct that consists of a label and the image directive. Surround the label text with vertical bars, the `|` character.

```text
  Some of the emoji that you can use are |emoji|.
```

Then insert the following image directive at the bottom of the document:

```text
  .. |emoji| image:: ../images/emoji.png
    :alt: Some of the emoji that you can use.
    :align: middle
```

### Literal blocks

To use a literal block with no syntax highlighting, use the Sphinx code-block directive with the language set to `none`.

```text
  .. code-block:: none
```

### Code blocks with syntax highlighting

To create a code block with syntax highlighting, use the Sphinx code-block directive with the language set to the language that you want highlighted. [Many languages are available](http://pygments.org/docs/lexers/), but in Mattermost documentation the most likely ones are as follows:

```text
- go
- rest
- html
- javascript
- coffee
- bash
```

The following example is a block of Go code.

```text
  .. code-block:: go
    :linenos:

    newPassword := props["new_password"]
      if err := utils.IsPasswordValid(newPassword); err != nil {
          c.Err = err
          return
      }
```

## Using Markdown

The majority of Mattermost technical documentation is written in `.rst` format. However, there are some instances where Markdown is used, for example the Mattermost Handbook. You can read more about using Markdown in the [Formatting Text](https://docs.mattermost.com/messaging/formatting-text.html) section of the Mattermost product documentation.