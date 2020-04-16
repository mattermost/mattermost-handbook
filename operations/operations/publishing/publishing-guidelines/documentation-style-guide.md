# Documentation Style Guide

When writing for Mattermost, always think about the audience that will be reading your writing. Mattermost’s 
audience can vary, but we typically communicate with a technical audience and want to present Mattermost as 
being a friend of the practitioner in development, IT, and operations. It must be accurate and clear, be 
presented with a style and tone that is appropriate for technical content, and easy to navigate.

## Document structure

Structure and organization are an important part of a document's ease of use and its understandability. 
Information should be organized and presented in a logical order, with similar subjects grouped together in the 
same section. In most cases, a document has a title, an introductory paragraph, and one or more sections.

Try to keep only one topic in a page. Shorter topics are easier to reuse in other documents, are 
easier to write and edit, and are easier to translate.

### Document title

The title appears in the left-hand navigation and at the top of the table of contents. Use a title that accurately reflects the content of the document. People scan the table of contents looking for answers; it's often faster than using the built-in search engine. 

**Use Title Case for document titles (e.g. "This is an Article about Documentation").**


### Document sections

To make pages easier for people to quickly scan for the content that they're looking for, break your 
document up into logical sections. Each section should have a heading, and the heading should relate 
to the content of the section. A section heading is not required if you have only one section.

**Use sentence case for the section heading (e.g. "This section is about types of headings").**


### Abstract

The abstract provides a high-level overview of the content, includes context, and outlines the value or goal to the reader. 
It often helps to write the abstract first, as it provides a framework for the content that follows. Keep in mind that the 
description is displayed in the search results along with the page title. People read the description to 
help them decide if the document is the one that they want.

### Table of contents

If the document contains more than four sections or subsections, add a table of contents to help the user
navigate the document. The table of contents should be added below the abstract. 

### Introductory paragraph

Each page should have an introduction that acts as a short description of the document. The short description
should be a single paragraph of no more than three sentences. 

## Using ReStructuredText markup (rst)

The reStructuredText specification allows for a certain degree of flexibility in 
markup to achieve your goals. For example, you can use any one of more than a dozen characters for 
section title underlines, and you have the option of using an overline in addition to an underline.

The majority of Mattermost technical documentation is written in `.rst`. However, there are some instances
where Markdown is used. 

Use the following conventions when writing in `.rst`. 

### Page titles

Underline page titles using `=`, with no overline. Underlines should be as long as the title text. For example:

```
  Document Title
  ==============
```

### Section titles

Underline using `-` for section titles. For example:

```
  Section title
  -------------
``` 

Underline subsections using `~` for the first subsection level, and `^` for the second subsection level. For example:

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
| Field names       | ``**bold**`` | "Enter the font in the **Display Font** field." |
| Clickable control |  ``**bold**`` | "Click **File > Save**."|
| Citations      | ``*italic*`` | "Read the book *Clean Code* by Robert Martin." |
| Window titles | ``*italic*``| "The *Account Settings* window opens." |
| User account names      | ``*italic*`` | "Log in to the *mysql* account." |
| Parameter names | ``*italic*``| "Set the *auto-config* parameter to ``false``" |
| Keyboard buttons      | Key1+Key2 | "Press CTRL+U to upload a file." |
| Placeholder field | {placeholder}| "Use the URL in the form of {hostname}.mattermost.com/{team}." |    `  `  
                   

### Bullet lists

For bullet lists and sublists, use `-` before the list item. For example:

```
  - list item one
  - list item two
    - sublist item one
    - sublist item two
  - list item three
```

### Numbered lists and procedure steps

Create numbered lists and procedure steps using numbers for the top-level list and lower case alpha characters for the first nested list. For example:

```
  1. This is item one.
  2. This is item two.

    a. This is nested item one.
    b. This is nested item two.

  3. This is item three.
```

### Name-value groups

To create a name-value group such as a definition list, type the term on a line by itself. On the next line, indent the definition. For example:

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

The `:ref:` role is a two-part construct. One part is the link itself, and the other part is the target. The target has the following form, and should preceed a section title:

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

You can also add the following image options: `height`, `width`, `scale`, `align`, and `target`. For example:

```
  .. image:: ../images/choices.png
    :alt: The choices that you can make.
    :height: 100px //number refers to pixels
    :width: 200px //number refers to pixels
    :align: left //left, right or middle
    :scale: 50 //number is a percentage
 ```

Inserting an inline image is a bit more complicated. It's a two-part construct that consists of a label and the image directive. Surround the label text with vertical bars, the `|` character. For example:

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

To use a literal block with no syntax highlighting, use the Sphinx code-block directive with the language set to `none`. For example:

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

The Mattermost Handbook is written in Markdown, and you can read more about using Markdown 
in the [Formatting Text](https://docs.mattermost.com/help/messaging/formatting-text.html) section of the User's Guide.
