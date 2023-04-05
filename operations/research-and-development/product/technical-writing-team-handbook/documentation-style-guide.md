# Documentation style guide

Mattermost documentation is presented in various forms. We have product documentation, a Handbook, API guides, developer documentation, in-product copy, and microcopy. 

The contents of this document can be applied to our product documentation, Handbook, developer documentation, and API guides. In-product copy and microcopy are covered in a separate guide.

For details about how we write UI text, naming conventions for CTAs, and writing with empathy, take a look at the [User Interface Text Guidelines](operations/research-and-development/product/technical-writing-team-handbook/user-interface-text-guidelines.md).

Apply this style guide in the following situations:

- When you create a new document.
- When you convert a document from Markdown to reStructuredText.
- When you revise a document.

When you revise a document, apply the style guide rules to the part that you changed. If you have time to update the rest of the document, then do so. If the scope is significantly greater than you originally anticipated, then do what you can and what makes sense, and then create an [issue in GitHub](https://github.com/mattermost/docs/issues). Give the issue an appropriate title, such as *File XXX converted to .rst, but needs updating for style guide*.

## General principles

One of our ongoing initiatives is to ensure our documentation is written in natural, clear language. We also focus on empathy and ensuring that we set our readers up for success. 

* **Always think about the audience that will be reading your writing.** We typically communicate with a technical audience and want to present Mattermost as being a friend of the practitioner in development, IT, and operations. Documentation must be accurate and clear, and easy to navigate. 
* **The document structure should be consistent, as should the left-hand navigation sections.** For example, each of our tools' documentation includes a Getting Started section, an Overview section, and the section names are the same. This is as much for us as it is for our audience - consistency makes it easy for contributors to help us with content, and helps provide context and familiarity to readers.
* **Write in the context of achievement.** The documentation should help Mattermost users and administrators achieve their goals. Write imperative sentences as much as possible. Imperative sentences begin with verbs and give instructions, information, and advice to help people install, administer, and use Mattermost with success. Use positive constructs as much as possible, but note that a negative construct can act as a warning that causes a reader to pay closer attention to the content, resulting in higher levels of accomplishment.
* **Write to facilitate scanning.** Readers need to find information quickly. People don't read documentation as much as they scan it for solutions to their immediate problem. Writing and presentation styles that seem redundant in essays or other texts are often helpful to people scanning for information.

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

### Numbers

We borrow from both AP and Chicago in this instance:

Spell out numbers when the number is the first word in a sentence or is less than or equal to ten \(i.e. one to nine\), otherwise use figures \(i.e., 10 upwards\). Use commas to make long number strings easier to read.

Avoid
  3 cows ran for 6 kilometers when they saw 2300097 mosquitoes chasing them.

Preferred
  Three cows ran for six kilometers when they saw 2,300,097 mosquitoes chasing them.

[Helpful overview](https://www.grammarbook.com/numbers/numbers.asp):

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

A section title is usually called H2, H3, H4, etc. Section headings are usually not clickable, but instead have formatting like bold or italics. Section titles are denoted by `#` in Markdown, with the number of #s indicating what level of heading is being used (i.e., `##` for H2, `###`for H3 etc). In reStructuredText the heading rules are slightly more complicated in terms of formatting, as we use Sphinx to process our documentation. You can read more about this in the [using reStructuredText markup](/operations/research-and-development/product/technical-writing-team-handbook/using-restructured-text.md) guide.

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
      <td style="text-align:left">Refers to <a href="https://mattermost.com/about-us/">Mattermost</a> the
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
      <td style="text-align:left">Refers to making a new installation widely accessible. It can also
        refer to releasing an updated version, patch, etc.</td>
      <td style="text-align:left">Desktop App deployment guide</td>
    </tr>
    <tr>
      <td style="text-align:left">configuration</td>
      <td style="text-align:left">Describes the settings and customizations applied to Mattermost
        to change the appearance and behavior.</td>
      <td style="text-align:left">Edit the configuration file to include any custom settings related to
        your domain</td>
    </tr>
    <tr>
      <td style="text-align:left">Mattermost Server</td>
      <td style="text-align:left">Refers to the single Linux binary that is installed on the physical
        server which hosts your Mattermost installation. It is not used to refer
        to the product going beyond the binary name. Always capitalize the &quot;Server&quot;
        when referring to the name of the binary.</td>
      <td style="text-align:left">Download the Mattermost Server binary</td>
    </tr>
    <tr>
      <td style="text-align:left">Mattermost server</td>
      <td style="text-align:left">Refers to the physical server on which you run Mattermost. It is
        also referred to as the customer&#x2019;s Mattermost server. Always lowercase
        &quot;server&quot; when referring to the customer&#x2019;s physical Mattermost
        server</td>
      <td style="text-align:left">Your Mattermost server may need to be rebooted before changes are applied</td>
    </tr>
    <tr>
      <td style="text-align:left">Web App</td>
      <td style="text-align:left">Refers to the Mattermost Web Application. References to general
        web applications are not capitalized.</td>
      <td style="text-align:left">Mattermost Web App</td>
    </tr>
    <tr>
      <td style="text-align:left">Mobile App</td>
      <td style="text-align:left">Refers to the Mattermost Mobile Application. References to general
        mobile applications are not capitalized.</td>
      <td style="text-align:left">Mattermost Mobile App</td>
    </tr>
    <tr>
      <td style="text-align:left">Desktop App</td>
      <td style="text-align:left">Refers to the Mattermost Desktop Application. References to general
        desktop applications are not capitalized.</td>
      <td style="text-align:left">Mattermost Desktop App</td>
    </tr>
    <tr>
      <td style="text-align:left">public channel</td>
      <td style="text-align:left">Refers to channels available to all members to discover and join.
        Written in lowercase and not hyphenated.</td>
      <td
      style="text-align:left">Outgoing webhooks are supported in public channels only</td>
    </tr>
    <tr>
      <td style="text-align:left">private channel</td>
      <td style="text-align:left">Refers to channels managed by synchronized groups. Written in lowercase and not hyphenated.</td>
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
      <td style="text-align:left">Refers to all types of computers, phones, and other
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

## Plan and deloyment support details

Visitors to Mattermost product documentation look for confirmation that a given feature is supported as part of their subscription plan and available in their self-hosted or Cloud-based deployment. This information is placed prominently at the top of every documentation page for easy scanning.

Plan and deployment details can be added to new product documentation pages using the following RST syntax that uses a Sphinx ``include`` directive:

```text
.. include:: ../_static/badges/allplans-cloud-selfhosted.rst
  :start-after: :nosearch:
```

The ``include`` directive points to an RST file, and the file you specify is one of 12 templated files that cover all combinations of plan and deployment support available in the ``/_static/badges`` directory.

**Note:** The ``:start-after`` line is important and shouldn't be omitted. The ``nosearch`` attribute is present in the templated RST files to instruct Sphinx not to return the templated files in search results. The include directive tells Sphinx to hide the ``nosearch`` text present in the templated RST files when publishing the page. 

## Tabbed content

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

## Return Mattermost configuration settings in search results

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

## Manage and resolve merge conflicts

Mattermost hosts the source code and content of its technical documentation in GitHub repositories. Documentation is updated by submitting pull requests on GitHub. After a pull request is reviewed and approved, it is usually merged into the master branch without further changes. Sometimes, however, conflicts between the files being updated and the master branch must be resolved.

GitHub flags conflicting regions of a file with these characters: `<<<<<<<`, `=======`, and `>>>>>>>`. The block of text between `<<<<<<<` and `=======` is the content that the pull request is attempting to merge. The block of text between `=======` and `>>>>>>>` is the block of text from the master branch that conflicts with the content in the pull request. Resolving a conflict may require removing content that has been updated in the pull request, or manually integrating text from the pull request. **The flag characters must also be removed.**

After resolving the conflicts in a given file, mark it as resolved in GitHub. All conflicts must be resolved for the merge to proceed.

The image below shows a section of a file with a merge conflict:

[](https://user-images.githubusercontent.com/74422101/211895979-255e4988-82de-40e9-97dd-5da97b1d98c9.png)

The lines between `<<<<<<< issue-5951-authentication-oauth-ms` and `=======` are from the pull request. The lines between `=======` and `>>>>>>> master` are from the master branch. In this case, metadata had been added to the same region of the file that was edited in the pull request. In order to resolve the conflict, the text from the pull request and the metadata were kept, while part of the text from the master branch was removed.
