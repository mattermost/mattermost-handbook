# Documentation Style Guide

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

## Writing style

While we don't strictly follow a specific Style Guide, we've based our Style Guide on the Chicago Manual of Style for the most part. We also borrow conventions from the AP Style Guide. In cases where we have a blend of the two, we've provided references and explanations.

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

We use Title Case for document names/titles. A document title is usually called an H1 heading and is either denoted by `#` in Markdown or `======` in reStructuredText. The title appears in the left-hand navigation and at the top of the table of contents. Use a title that accurately reflects the content of the document. People scan the table of contents looking for answers; it's often faster than using the built-in search engine.

**Use Title Case for document titles \(e.g. "This is an Article about Documentation"\). Where a word/title/name is lowercase, retain that casing in the title \(e.g. "This Article Covers the mmctl Tool"\).**

Instead of *"Deployment guide for organizations"* we write *"Deployment Guide for Organizations"*

#### Section titles and headings

We use Sentence case for section titles and headings. Each section should have a heading, and the heading should relate to the content of the section. A section heading is not required if you have only one section.

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
      <td style="text-align:left">Refers to an on-premises Mattermost environment comprised of hardware
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
      <td style="text-align:left">Public channel</td>
      <td style="text-align:left">Used to refer to channels available to all members to discover and join.
        Don&#x2019;t hyphenate and use lowercase for &quot;channel&quot;.</td>
      <td
      style="text-align:left">Outgoing webhooks are supported in Public channels only</td>
    </tr>
    <tr>
      <td style="text-align:left">Private channel</td>
      <td style="text-align:left">Used to refer to channels managed by synchronized groups. Don&#x2019;t
        hyphenate and use lowercase for &quot;channel&quot;.</td>
      <td style="text-align:left">Users can remove themselves from teams and Private channels managed by
        synchronized groups</td>
    </tr>
    <tr>
      <td style="text-align:left">Direct Message</td>
      <td style="text-align:left">Direct Messages are for conversations between two people. Visible only
        to the people involved.</td>
      <td style="text-align:left">Full names appear in the Direct Messages member list and team management
        modal</td>
    </tr>
    <tr>
      <td style="text-align:left">Group Message</td>
      <td style="text-align:left">Group Messages are Direct Messages that have conversations among three
        or more people. Visible only to the people involved.</td>
      <td style="text-align:left">Group Messages are listed in the sidebar</td>
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

can, might, may
  The word *may* can have several meanings. To avoid ambiguity, use *can* or *might* instead of *may*. Use *can* to mean *capable of* and *might* to mean that something is possible. Use *may* only to give permission to do something.

downtime
  Use as one word *downtime*, not *down time*.

emoji, emojis
  Use *emojis* as the plural form of *emoji*.

login, log in, log into
  Use *login* as a noun or adjective, and *log in* and *log into* as verbs. For example: *Log into the Mattermost server using your System Admin login credentials.*

setup, set up
  Use *setup* as a noun or adjective, and *set up* as a verb. For example: *Set up your operating system as described in the Ubuntu documentation.*

sign-in, sign in, and sign into
  Use *sign-in* as a noun or adjective, and *sign in* and *sign into* as verbs. For example: *Sign into your Mattermost account using the sign-in credentials that were sent to you.*

Single sign-on
  Single sign-on is abbreviated as SSO. When using the long form in a heading with title case, it's *Single Sign-on*.

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

### External links

URLs are automatically rendered as links in Sphinx; however, where possible, it is preferred that hyperlinks are created within the text of a sentence. Hyperlinks within a sentence can be created using the following formatting:

```text
`Link display text <URL-of-website>`__

For example:
  `Mattermost Manifesto <https://www.mattermost.org/manifesto/>`__
```

The link renders as: [Mattermost Manifesto](https://www.mattermost.org/manifesto/).

### Internal links to Mattermost documentation

When creating a link to another document in the Mattermost documentation, create a link with a relative URL.

A link with an absolute URL is not as flexible as a relative URL. Relative URLs don't break when the documentation is moved to another host, or if the documentation is hosted on a server that's behind a firewall without access to the Internet.

The Sphinx processor extends reStructuredText to implement references, called roles, to locations within a documentation set. The two roles that are relevant in Mattermost documentation are the `:doc:` role and the `:ref:` role.

The `:doc:` role is used for creating relative links to other documents. The `:ref:` role is used for creating relative links to arbitrary locations within the documentation set, including within the same document. In both cases, the HTML output is a relative URL for the target location.

The following example uses the `:doc:` role to link to the **Integrations Overview** page. The source file is called `integrations.rst` and is in the `overview` directory.

```text
  For more information about integrating with Mattermost, see :doc:`../overview/integrations`.
```

Note that the filename extension is not part of the construct. On output, the link looks like this: "For more information about integrating with Mattermost, see :doc:`../overview/integrations`." The Sphinx processor pulls in the title of the document to use as the link text.

The `:ref:` role is a two-part construct. One part is the link itself, and the other part is the target. The target has the following form, and should precede a section title:

```text
  .. _arbitrary-text-label:

### Bullet Lists
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

The majority of Mattermost technical documentation is written in `.rst`. However, there are some instances where Markdown is used, for example the Mattermost Handbook. You can read more about using Markdown in the [Formatting Text](https://docs.mattermost.com/messaging/formatting-text.html) section of the Mattermost product documentation.
