# Education and training style guide

## General writing principles

While Mattermost educational assets target a variety of audiences, there are some general writing principles that apply universally:

- Consider who is consuming your craft. 
  - Is the information and context clear and easy to consume? 
  - Does the information contain an appropriate level of technical detail for the audience?
  - What assumptions have been made about what the user knows/doesn't know/should already know?
- Make information easy to scan.
  - Users access learning materials to answer questions, learn how to do something, or learn how to troubleshoot a situation. 
  - Help users reach the answers they seek using short, direct, second person sentences that are less taxing to scan than long paragraphs of text.
  - Use sentence case instead of title case for all page and heading titles as well as UI text elements.
- Develop educational content in the context of successful achievement.
  - We educate our customers and partners to empower them to have a positive experience with the product that leads to a success end goal. 
  - Warnings, caveats, and notes help steer readers towards a positive outcome, while tips help users get the most out of a given feature, workflow, or use case.
- Develop content that appeals to the widest audience possible.
  - Use plain language, choose simple, unambiguous terms, and avoid jargon to ensure that all audiences, including those for whom English isn't a primary language can follow and understand. Remember that there's a big difference between "jargon" and "terminology".
    - Jargon is usually industry-specific and can be isolating or confusing for users who aren't deeply familiar with them. Terminology is usually universally-accepted and generally understood.
  - Use terms consistency, including capitalization to avoid overwhelming, overloading, or confusing users across educational assets.
  - Use the present tense to describe a current state or condition, and the future tense to state something that is definitely going to happen.
  - Explain the consequences of an action so that the user can decide whether to proceed
  - Use the active voice _except_ for cases where:
    - You'll end up blaming the user. Inform them about what happened, explain why it happened, and suggest a way forward.
    - You're describing something that just happened.
    - The entity taking action is the Mattermost application itself.

**Note**: We're in the process of updating the Mattermost [writer's style guide](operations/research-and-development/product/technical-writing-team-handbook#style-guide-and-ui-writing-guides), as well as guidelines for working with [in-product text](operations/research-and-development/product/technical-writing-team-handbook/user-interface-text-guidelines),[Mattermost terminology](operations/research-and-development/product/technical-writing-team-handbook/our-terminology), [community documentation](operations/research-and-development/product/technical-writing-team-handbook/writing-community-documentation ). terminology guidelineThe following older resources are available

## General principles

* **Always think about the audience that will be reading your writing.** Our audience comprises multiple personas, but we typically communicate with a technical audience and want to present Mattermost as being a friend of the practitioner in development, IT, and operations. It must be accurate and clear, and easy to navigate. 
* **The document structure should be consistent, as should the left-hand navigation sections.** For example, each of our tools' documentation includes a Getting Started section, an Overview section, and the section names are the same. This is as much for us as it is for our audience - consistency makes it easy for contributors to help us with content, and helps provide context and familiarity to readers.
* **Write in the context of achievement.** The documentation should help Mattermost users and administrators achieve their goals. Write imperative sentences as much as possible. Imperative sentences begin with verbs and give instructions, information, and advice to help people install, administer, and use Mattermost with success. Use positive constructs as much as possible, but note that a negative construct can act as a warning that causes a reader to pay closer attention to the content, resulting in higher levels of accomplishment.
* **Write to facilitate scanning.** Readers need to find information quickly. People don't read documentation as much as they scan it for solutions to their immediate problem. Writing and presentation styles that seem redundant in essays or other texts are often helpful to people scanning for information.

## How we write things

One of our ongoing initiatives is to ensure our documentation is written in natural, clear language. We also focus on empathy and ensuring that we set our readers up for success. This section of the style guide is about content we reuse across our documentation. 

For details about how we write UI text, naming conventions for CTAs, and writing with empathy, take a look at the [User Interface Text Guidelines](operations/research-and-development/product/technical-writing-team-handbook/user-interface-text-guidelines.md).

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