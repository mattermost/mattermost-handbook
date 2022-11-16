# Documentation style guide

Mattermost documentation is presented in various forms. We have product documentation, a Handbook, API guides, developer documentation, in-product copy, and microcopy. While there are different audiences for all these bodies of work, there are some guiding principles that should be applied to all our content.

The contents of this document can be applied to our product documentation, Handbook, developer documentation, and API guides. In-product copy and microcopy are covered in a separate guide.

Apply the style guide in the following situations:

- When you create a new document.
- When you convert a document from Markdown to reStructuredText.
- When you revise a document.

When you revise a document, apply the style guide rules to the part that you changed. If you have time to update the rest of the document, then do so. If the scope is significantly greater than you originally anticipated, then do what you can and what makes sense, and then create an [issue in GitHub](https://github.com/mattermost/docs/issues). Give the issue an appropriate title, such as *File XXX converted to .rst, but needs updating for style guide*.

## General principles

* **Always think about the audience that will be reading your writing.** Our audience comprises multiple personas, but we typically communicate with a technical audience and want to present Mattermost as being a friend of the practitioner in development, IT, and operations. It must be accurate and clear, and easy to navigate. 
* **The document structure should be consistent, as should the left-hand navigation sections.** For example, each of our tools' documentation includes a Getting Started section, an Overview section, and the section names are the same. This is as much for us as it is for our audience - consistency makes it easy for contributors to help us with content, and helps provide context and familiarity to readers.
* **Write in the context of achievement.** The documentation should help Mattermost users and administrators achieve their goals. Write imperative sentences as much as possible. Imperative sentences begin with verbs and give instructions, information, and advice to help people install, administer, and use Mattermost with success. Use positive constructs as much as possible, but note that a negative construct can act as a warning that causes a reader to pay closer attention to the content, resulting in higher levels of accomplishment.
* **Write to facilitate scanning.** Readers need to find information quickly. People don't read documentation as much as they scan it for solutions to their immediate problem. Writing and presentation styles that seem redundant in essays or other texts are often helpful to people scanning for information.

## How we write things

One of our ongoing initiatives is to ensure our documentation is written in natural, clear language. We also focus on empathy and ensuring that we set our readers up for success. This section of the style guide is about content we reuse across our documentation. 

For details about how we write UI text, naming conventions for CTAs, and writing with empathy, take a look at the [User Interface Text Guidelines](operations/research-and-development/product/technical-writing-team-handbook/user-interface-text-guidelines.md).

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

	.. tab:: TabNameA

		Tab text goes here. Users see this content when users visit this page.

	.. tab:: TabNameB

		Tab text goes here. The user must select this tab to see this content.

	.. tab:: TabNameC

		Tab text goes here. The user must select this tab to see this content
```

Note that tabbed content syntax applies only to RST source files and is not yet available within Markdown source files, and that spacing and indentation are important elements of the syntax. When previewing draft work, if tabbed content isn't displaying as expected, carefully review spacing and indentation.

When presenting content in tabs, tab names must be exactly the same across all instances, for consistency.

"From Mattermost version 6.0..." vs "In Mattermost versions up to v5.39"

## Writing style

While we don't strictly follow a specific Style Guide, we've based our Style Guide on the Chicago Manual of Style for the most part. We also borrow conventions from the AP Style Guide. In cases where we have a blend of the two, we've provided references and explanations.

We try to keep the following top of mind when creating content:

* Work on the premise that "Every page is page 1", as a large portion of users access our documentation directly from a Google search
* Add a summary to the top of each page for readers to be able to quickly assess the content for suitability
* Break long sections into smaller, easily digestable subpages
* Have at most one key point or action per paragraph
* Refer to one thing or idea with the same word throughout the page
* Use ordered lists or bullets where appropriate, as they are generally easier to read than long blocks of text
* Minimize content so it can be found and remembered. Keep pages short, modular, and focused on a single topic

Mattermost documentation is read and used in many countries/regions and cultures. For this reason, you must consider cultural differences on a global scale. Names, places, events, and actions should be chosen as carefully as possible to avoid misunderstanding.

Also remember that English isn't the primary language of many readers of the documentation. Keep the following advice in mind when writing:

* Choose words with one or very few meanings.
* Use simple verb forms in writing. Most verbs in the simple form are likely to have an equivalent in another language.
* Avoid jargon and slang words.
* Limit difficult words to technical terms where their use is unavoidable.
* Always make sure that your spelling is correct.

### Language

We write in English and use American English. This means we use "z" instead of "s" in words like "organization". It helps to set your browser and editing tool to use a US dictionary so that if you inadvertently use British English, you'll be alerted. Currently, our documentation is not localized, but many other aspects of Mattermost's tools, such as in-product copy, are.

One very important rule is to avoid constructs where you are forced to write either _he_ or _she_, or _his_ or _her_. You can use _they_ or _their_ as singular forms instead. As we write in first-person, we generally refer to _you_, _users_, _them_.

### Numbers

We borrow from both AP and Chicago in this instance:

Spell out numbers when the number is the first word in a sentence or is less than or equal to ten \(i.e. one to nine\), otherwise use figures \(i.e., 10 upwards\). Use commas to make long number strings easier to read.

Avoid
  3 cows ran for 6 kilometers when they saw 2300097 mosquitoes chasing them.

Preferred
  Three cows ran for six kilometers when they saw 2,300,097 mosquitoes chasing them.

[Helpful overview](https://www.grammarbook.com/numbers/numbers.asp):

"In terms of numbering, policies and philosophies vary from medium to medium. America's two most influential style and usage guides have different approaches: The Associated Press Stylebook recommends spelling out the numbers zero through nine and using numerals thereafter—until one million is reached. Here are four examples of how to write numbers above 999,999 in AP style: 1 million; 20 million; 20,040,086; 2.7 trillion.

The Chicago Manual of Style recommends spelling out the numbers zero through one hundred and using figures thereafter — except for whole numbers used in combination with hundred, thousand, hundred thousand, million, billion, and beyond (e.g., two hundred; twenty-eight thousand; three hundred thousand; one million). In Chicago style we would write four hundred, eight thousand, and twenty million with no numerals. Chicago style would require numerals for 401; 8,012; and 20,040,086."

### Commas

We use the Oxford \(serial\) comma in our documentation.

Avoid
  The cows ran from wolves, coyotes and mosquitoes.

Preferred
  The cows ran from wolves, coyotes, and mosquitoes.

### Capitalization

#### Document titles

We use sentence case for document names/titles. A document title is usually called an H1 heading and is either denoted by `#` in Markdown or `======` in reStructuredText. The title appears in the left-hand navigation and at the top of the table of contents. Use a title that accurately reflects the content of the document. People scan the table of contents looking for answers; it's often faster than using the built-in search engine.

**Use sentence case for document titles \(e.g. "This is an article about Documentation"\). Where a word/title/name is lowercase, retain that casing in the title \(e.g. "This article covers the mmctl Tool"\).**

Instead of *"Deployment guide for organizations"* we write *"Deployment guide for organizations"*

#### Section titles and headings

We use sentence case for section titles and headings. Each section should have a heading, and the heading should relate to the content of the section. A section heading is not required if you have only one section.

A section title is usually called H2, H3, H4, etc. Section headings are usually not clickable, but instead have formatting like bold or italics. Section titles are denoted by `#` in Markdown, with the number of #s indicating what level of heading is being used (i.e., `##` for H2, `###`for H3 etc). In reStructuredText the heading rules are slightly more complicated in terms of formatting, as we use Sphinx to process our documentation. You can read more about this in the [using reStructuredText markup](using-restructuredtext-markup-rst) section.

**Use sentence case for the section heading \(e.g. "This section is about types of headings"\) except where a word/phrase is a proper noun \(e.g. "Mattermost"\), the name of a country/region \(e.g. "The United States of America"\), and so on.**

**Title example**

Instead of *"Writing Guidelines for Editors"* we write *"Writing guidelines for editors"*

### Person

Use the second person and avoid the first person.

Avoid
  We'll view the status in the *Status* pane.

Preferred
  View the status in the *Status* pane.

### Voice

Use active voice in preference to passive voice. Active voice has the subject of a sentence doing the action. In passive voice, the subject has an action done to it.

Avoid
  The *Status* pane will be opened by the system.

Preferred
  The system opens the *Status* pane.

### Tense

Use the present tense.

Avoid
  Sharing this link will let other users view the linked message.

Preferred
  Sharing this link lets other users view the linked message.

## Terminology Guide

Throughout Mattermost documentation, you’ll see the below terms mentioned and used. Their definitions and reason for usage are defined below.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Terms</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Usage</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Mattermost</td>
      <td style="text-align:left">Used to refer to <a href="https://mattermost.com/about-us/">Mattermost</a> the
        company and <a href="https://mattermost.com/product/">Mattermost</a> the
        product.</td>
      <td style="text-align:left">
        <p>Mattermost is an open-source, self-hosted messaging platform with unlimited
          file sharing, search, and integrations</p>
        <p>Configure Mattermost on your server</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">installation</td>
      <td style="text-align:left">Refers to an on-premises Mattermost environment comprising hardware
        (server/s), database, filestore, etc., which hosts the required files to
        run Mattermost.</td>
      <td style="text-align:left">Your Mattermost installation includes physical servers</td>
    </tr>
    <tr>
      <td style="text-align:left">deployment</td>
      <td style="text-align:left">Used to refer to making a new installation widely accessible. It can also
        refer to releasing an updated version, patch, etc.</td>
      <td style="text-align:left">Desktop App deployment guide</td>
    </tr>
    <tr>
      <td style="text-align:left">configuration</td>
      <td style="text-align:left">Used to describe the settings and customizations applied to Mattermost
        to change the appearance and behavior.</td>
      <td style="text-align:left">Edit the configuration file to include any custom settings related to
        your domain</td>
    </tr>
    <tr>
      <td style="text-align:left">Mattermost Server</td>
      <td style="text-align:left">Used to refer to the single Linux binary that is installed on the physical
        server which hosts your Mattermost installation. It is not used to refer
        to the product going beyond the binary name. Always capitalize the &quot;Server&quot;
        when referring to the name of the binary.</td>
      <td style="text-align:left">Download the Mattermost Server binary</td>
    </tr>
    <tr>
      <td style="text-align:left">Mattermost server</td>
      <td style="text-align:left">Used to refer to the physical server on which you run Mattermost. It is
        also referred to as the customer&#x2019;s Mattermost server. Always lowercase
        &quot;server&quot; when referring to the customer&#x2019;s physical Mattermost
        server</td>
      <td style="text-align:left">Your Mattermost server may need to be rebooted before changes are applied</td>
    </tr>
    <tr>
      <td style="text-align:left">Web App</td>
      <td style="text-align:left">Used to refer to the Mattermost Web Application. References to general
        web applications are not capitalized.</td>
      <td style="text-align:left">Mattermost Web App</td>
    </tr>
    <tr>
      <td style="text-align:left">Mobile App</td>
      <td style="text-align:left">Used to refer to the Mattermost Mobile Application. References to general
        mobile applications are not capitalized.</td>
      <td style="text-align:left">Mattermost Mobile App</td>
    </tr>
    <tr>
      <td style="text-align:left">Desktop App</td>
      <td style="text-align:left">Used to refer to the Mattermost Desktop Application. References to general
        desktop applications are not capitalized.</td>
      <td style="text-align:left">Mattermost Desktop App</td>
    </tr>
    <tr>
      <td style="text-align:left">public channel</td>
      <td style="text-align:left">Used to refer to channels available to all members to discover and join.
        Written in lowercase and not hyphenated.</td>
      <td
      style="text-align:left">Outgoing webhooks are supported in public channels only</td>
    </tr>
    <tr>
      <td style="text-align:left">private channel</td>
      <td style="text-align:left">Used to refer to channels managed by synchronized groups. Written in lowercase and not hyphenated.</td>
      <td style="text-align:left">Users can remove themselves from teams and private channels managed by
        synchronized groups</td>
    </tr>
    <tr>
      <td style="text-align:left">direct message</td>
      <td style="text-align:left">Direct messages are for conversations between two people. Visible only
        to the people involved. Written in lowercase and not hyphenated.</td>
      <td style="text-align:left">Full names appear in the direct messages member list and team management
        modal</td>
    </tr>
    <tr>
      <td style="text-align:left">group message</td>
      <td style="text-align:left">Group messages are direct messages that have conversations among three
        or more people. Visible only to the people involved. Written in lowercase and not hyphenated.</td>
      <td style="text-align:left">Group messages are listed in the sidebar</td>
    </tr>
    <tr>
      <td style="text-align:left">device</td>
      <td style="text-align:left">Used to refer to collectively to all types of computers, phones, and other
        devices.</td>
      <td style="text-align:left">Speak with the owner of any other proxies between your device and the
        Mattermost server</td>
    </tr>
  </tbody>
</table>

To promote consistency and clarity, follow the word usage and spelling guidelines below.

- can, might, may
	- The word *may* can have several meanings. To avoid ambiguity, use *can* or *might* instead of *may*. Use *can* to mean *capable of* and *might* to mean that something is possible. Use *may* only to give permission to do something.

- downtime
	- Use as one word *downtime*, not *down time*.

- emoji, emojis
	- Use *emojis* as the plural form of *emoji*.

- login, log in, log into
	- Use *login* as a noun or adjective, and *log in* and *log into* as verbs. For example: *Log into the Mattermost server using your System Admin login credentials.*

- setup, set up
	- Use *setup* as a noun or adjective, and *set up* as a verb. For example: *Set up your operating system as described in the Ubuntu documentation.*

- sign-in, sign in, and sign into
	- Use *sign-in* as a noun or adjective, and *sign in* and *sign into* as verbs. For example: *Sign into your Mattermost account using the sign-in credentials that were sent to you.*

- Single Sign-on
	- Single Sign-on is abbreviated as SSO. When using the long form in a heading with title case, it's *Single Sign-on*.

## Gender-neutral Text

Avoid constructs where you're forced to write either *he or she* or *his or her*. You can use *they* or *their* as singular forms instead.

Preferred
  The community manager monitors the forum for well-written questions and answers, and posts them to the Contributors channel.
Avoid
  The community manager posts questions and answers that they think are well-written.
Do not use
  The community manager posts questions and answers that he or she thinks are well-written.

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
`:doc:`Link display text </folder/filename>`

For example, when you want to add a link on a Channels page to another Channels page:
  See the :doc:`channel preferences </channels/set-channel-preferences>` documentation for details.
```

Note that the file extension is not part of the syntax, and that two underline characters are missing. Sphinx uses the title of the document as the link text.

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

## Using Markdown

The majority of Mattermost technical documentation is written in `.rst` format. However, there are some instances where Markdown is used, for example the Mattermost Handbook. You can read more about using Markdown in the [Formatting Text](https://docs.mattermost.com/messaging/formatting-text.html) section of the Mattermost product documentation.
