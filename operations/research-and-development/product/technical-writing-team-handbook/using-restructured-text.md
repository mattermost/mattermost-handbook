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