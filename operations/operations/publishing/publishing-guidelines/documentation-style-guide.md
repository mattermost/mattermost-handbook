# Documentation Style Guide

When writing for Mattermost, always think about the audience that will be reading your writing. Mattermost’s audience can vary, but we typically communicate with a technical audience and want to present Mattermost as being a friend of the practitioner in development, IT, and operations. It must be accurate and clear, presented with a style and tone that is appropriate for technical or educational content, and easy to navigate.

An exception is **Customer Education** content where the audience is placed at the center of attention, as opposed to technical documentation where it is the document's content that is the primary focus.

## Document structure

Structure and organization are an important part of a document's ease of use and its understandability. Information should be organized and presented in a logical order, with similar subjects grouped together in the same section. In most cases, a document has a title, an introductory paragraph, and one or more sections.

Try to keep only one topic in a page. Shorter topics are easier to reuse in other documents, are easier to write and edit, and are easier to translate.

An exception to this is **Customer Education** content which can cover multiple topics per page.

### Document title

The title appears in the left-hand navigation and at the top of the table of contents. Use a title that accurately reflects the content of the document. People scan the table of contents looking for answers; it's often faster than using the built-in search engine. 

**Use Title Case for document titles (e.g. "This is an Article about Documentation"). Where a word/title/name is lowercase, retain that casing in the title (e.g. "This Article Covers the mmctl Tool").**

### Document sections

To make pages easier for people to quickly scan for the content that they're looking for, break your document up into logical sections. Each section should have a heading, and the heading should relate to the content of the section. A section heading is not required if you have only one section.

**Use sentence case for the section heading (e.g. "This section is about types of headings") except where a word/phrase is a proper noun (e.g. "Mattermost"), the name of a country/region (e.g. "The United States of America"), and so on.**

### Abstract

The abstract provides a high-level overview of the content, includes context, and outlines the value or goal to the reader. It often helps to write the abstract first, as it provides a framework for the content that follows. Keep in mind that the description is displayed in the search results along with the page title. People read the description to help them decide if the document is the one that they want. 

An exception is **Customer Education** content that has no need to outline the content but sets more specific expectations for a well-defined audience. 

For **Customer Education**, clearly name the audience as it can be narrow (System Administrators), but also large (System Administrators, Project Managers, and IT leaders in general). When setting the expectations answer these questions:

- How will the reader benefit from the guide - what exact knowledge is taught?
- How long will it take to work through the guide?
- What similar topics are not covered in this guide?

### Table of contents

If the document contains more than four sections or subsections, add a table of contents to help the user navigate the document. The table of contents should be added below the abstract. 

### Introductory paragraph

Each page should have an introduction that acts as a short description of the document. The short description should be a single paragraph of no more than three sentences. 

An exception is **Customer Education** content where the introduction is replaced by the Learning Objectives section.

## Writing style

### Language

Write documents in English. Use American spelling, and avoid constructs where you are forced to write either *he* or *she*, or *his* or *her*. You can use *they* or *their* as singular forms instead.

### Numbers

Spell out numbers when the number is the first word in a sentence or is less than or equal to ten (i.e. one to nine), otherwise use numeric digits (i.e., 10 upwards). Use commas to make long number strings easier to read.

### Commas

We use the Oxford \(serial\) comma in our documentation. 
 - For example: "Mattermost's writing style is clear, concise, and simple." as opposed to "Mattermost's writing style is clear, concise and simple."

### Capitalization

Use Title Case for document names/titles.
  - For example: "Deployment Guide for Organizations"

Use Sentence case for section titles and headings.
  - For example: "Writing guidelines for editors"

### Person

Use the second person and avoid the first person.
  - For example: "View the status in the **Status** pane." as opposed to "We’ll view the status in the **Status** pane."

An exception is **Customer Education** content which can be written in first or second person to keep the audience focused and interested.
  - For example: "While Mattermost provides options to make mobile deployment as easy as possible, it will take time and iteration. We are here to [support](https://link-to-support-section) you." as opposed to "Deploying the Mattermost Mobile App will take time and iteration."

### Voice

Use active voice in preference to passive voice. Active voice has the subject of a sentence doing the action. In passive voice, the subject has an action done to it.
  - For example: "The system opens the **Status** pane." as opposed to "The **Status** pane will be opened by the system."

### Tense

Use the present tense.
  - For example: "Sharing this link lets other users view the linked message." as opposed to "Sharing this link will let other users view the linked message."

## Using ReStructuredText markup (rst)

The reStructuredText specification allows for a certain degree of flexibility in markup to achieve your goals. For example, you can use any one of more than a dozen characters for section title underlines, and you have the option of using an overline in addition to an underline.

The majority of Mattermost technical documentation is written in `.rst`. The examples below describe the conventions we use when writing in `.rst`.

### Page titles

Underline page titles using `=`, with no overline. Underlines should be as long as the title text. 

```
  Document Title
  ==============
```

### Section titles

Underline using `-` for section titles.

```
  Section title
  -------------
``` 

Underline subsections using `~` for the first subsection level, and `^` for the second subsection level.

```
  Subsection one
  ~~~~~~~~~~~~~~

  Subsection two
  ^^^^^^^^^^^^^^
``` 

### Table of contents

Insert a table of contents into a document using the following format:

```
  .. contents::
      :backlinks: top
```  
    
### Text formatting
-----------------

Use highlighting of text to visually set off words and phrases that are important to readers. Content that should be highlighted includes file names, UI controls, and window titles. The following table has a comprehensive list with examples.

| Text          | Format        | Example             |
| ------------- |:-------------:| --------------------|
| Commands      | ` ``monospace`` ` | "At the command line, type ``sudo apt-get install nginx``." |
| Directory name| ` ``monospace`` ` | ``/opt/mattermost`` |
| File name     | ` ``monospace`` ` | ``config.py`` |
| Inline code   | ` ``monospace`` ` | ``fmt.Printf("2 times %d = %d\n", x, y )`` |
| Keystrokes    | ` ``monospace`` ` | "Type ``https://`` in the string field." |
| Screen output | ` ``monospace`` ` | See :ref:`literal-blocks` for an example. |
| Parameter values | ` ``monospace`` `| "Set the *auto-config* parameter to ``false``" |
| Field names       | ``**bold**`` | If the field has punctuation, include that in the formatting. For example "Enter the URL in the **Enter URL:** field."|
| Clickable control |  ``**bold**`` | "Click **File > Save**."|
| UI elements | ``**bold**``| "Open **Main Menu > Account Settings**." |
| Dialog boxes | ``**bold**``| "The **Create Thread** window opens." |
| Citations      | ``*italic*`` | "Read the book *Clean Code* by Robert Martin." |
| User account names | ``*italic*`` | "Log in to the *mysql* account." |
| Parameter names | ``*italic*``| "Set the *auto-config* parameter to ``false``" |
| Keyboard buttons  | Key1+Key2 | "Press CTRL+U to upload a file." |
| Placeholder field | {placeholder}| "Use the URL in the form of {hostname}.mattermost.com/{team}." |    `  `  
                   
### Bullet lists

For bullet lists and sublists, use `-` before the list item.

```
  - list item one
  - list item two
    - sublist item one
    - sublist item two
  - list item three
```

### Numbered lists and procedure steps

Create numbered lists and procedure steps using numbers for the top-level list and lowercase alpha characters for the first nested list.

```
  1. This is item one.
  2. This is item two.

    a. This is nested item one.
    b. This is nested item two.

  3. This is item three.
```

### Name-value groups

To create a name-value group such as a definition list, type the term on a line by itself. On the next line, indent the definition.

```
  Total users
    The total number of active accounts created on your system. Excludes inactive accounts.
  Total teams
    The total number of teams created on your system.
```

### External links

URLs are automatically rendered as links in Sphinx; however, where possible, it is preferred that hyperlinks are created within the text of a sentence. Hyperlinks within a sentence can be created using the following formatting:

`Link display text <URL-of-website>`__, for example:

```
  `Mattermost Manifesto <https://www.mattermost.org/manifesto/>`__
```

The link renders as: [Mattermost Manifesto](https://www.mattermost.org/manifesto/).

### Internal links to Mattermost documentation

The Sphinx processor extends reStructuredText to implement references, called roles, to locations within a documentation set. The two roles that are relevant in Mattermost documentation are the `:doc:` role and the `:ref:` role.

The `:doc:` role is used for creating relative links to other documents. The `:ref:` role is used for creating relative links to arbitrary locations within the documentation set, including within the same document. In both cases, the HTML output is a relative URL for the target location.

The following example uses the `:doc:` role to link to the **Integrations Overview** page. The source file is called `integrations.rst` and is in the `overview` directory.

```
  For more information about integrating with Mattermost, see :doc:`../overview/integrations`.
```

Note that the filename extension is not part of the construct. On output, the link looks like this: "For more information about integrating with Mattermost, see :doc:`../overview/integrations`." The Sphinx processor pulls in the title of the document to use as the link text.

The `:ref:` role is a two-part construct. One part is the link itself, and the other part is the target. The target has the following form, and should precede a section title:

```
  .. _arbitrary-text-label:

### Bullet Lists
```

To generate a link to the section, use the `:ref:` role as follows:

```
  For more information about bullet lists, see :ref:`arbitrary-text-label`.
```

The Sphinx processor creates a relative link to the section, and uses the section title as the link text. On output, the link looks like this: "For more information about bullet lists, see :ref:`arbitrary-text-label`."

### Images

Use the following construct to insert an image:

```
  .. image:: ../images/choices.png
```

You should use `alt` tag for all images.

You can also add the following image options: `height`, `width`, `scale`, `align`, and `target`.

```
  .. image:: ../images/choices.png
    :alt: The choices that you can make.
    :height: 100px //number refers to pixels
    :width: 200px //number refers to pixels
    :align: left //left, right or middle
    :scale: 50 //number is a percentage
 ```

Inserting an inline image is a bit more complicated. It's a two-part construct that consists of a label and the image directive. Surround the label text with vertical bars, the `|` character.

```
  Some of the emoji that you can use are |emoji|.
```

Then insert the following image directive at the bottom of the document:

```
  .. |emoji| image:: ../images/emoji.png
    :alt: Some of the emoji that you can use.
    :align: middle
```

### Literal blocks

To use a literal block with no syntax highlighting, use the Sphinx code-block directive with the language set to `none`.

```
  .. code-block:: none
```

### Code blocks with syntax highlighting

To create a code block with syntax highlighting, use the Sphinx code-block directive with the language set to the language that you want highlighted. [Many languages are available](http://pygments.org/docs/lexers/), but in Mattermost documentation the most likely ones are as follows:

```
- go
- rest
- html
- javascript
- coffee
- bash
```

The following example is a block of Go code.

```
  .. code-block:: go
    :linenos:

    newPassword := props["new_password"]
  	if err := utils.IsPasswordValid(newPassword); err != nil {
  		c.Err = err
  		return
  	}
```

## Using Markdown

The majority of Mattermost technical documentation is written in `.rst`. However, there are some instances where Markdown is used, for example the Mattermost Handbook. You can read more about using Markdown in the [Formatting Text](https://docs.mattermost.com/help/messaging/formatting-text.html) section of the User's Guide.
