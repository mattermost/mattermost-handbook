# Voice, Tone, and Writing Style Guidelines (1%)

## Goal

Create guidelines for unified user experience and reduce barriers to entry for content contributions. 

## Questions and Context

The first step of this process was to consider how well our guidelines are applied and understood across the company and community. This opened a discussion on both the voice/tone side of things as well as how these guidelines contribute to/detract from a feeling of empowerment and ownership of Mattermost content. 

Some initial questions were: 
- What is Mattermost’s current voice and tone?
- Is it possible to have multiple voice and tone guides for the various areas of Mattermost (blogs, developer documentation etc)?
- What's the best way to collaborate and communicate across the teams and with the community? 
- How do we implement a style guide for formatting, writing style, grammar, naming, UI entities, bullet list formatting etc (Chicago Manual of Style) and make it simple enough for all areas to stick to it to create a unified experience?

## Current Style Guides in Use

There are multiple style guides with different focus areas: 
- The [Marketing style guide](https://docs.google.com/document/d/1XWjtWdF77qKdxDso_-aC_S1c3E0ohOoxCRL_PIf3pco/edit#heading=h.sjfmtlwco6lj): Focus on voice 
- The [Marketing content guide](https://docs.mattermost.com/process/marketing-guidelines.html): Focus on voice
- [Screenshots guidelines](https://handbook.mattermost.com/operations/messaging-and-math/how-to-guides-for-m-and-m/how-to-create-screenshots-and-gifs)
- The [Documentation style guide (including UI text guidelines)](https://docs.mattermost.com/guides/core.html#documentation-style-guide): Focus on style 
- The [developer blog guidelines](https://developers.mattermost.com/internal/writing-a-blog-post/) (more guidance than specific stylist conventions): General 
- [Community content guidelines](https://docs.mattermost.com/process/marketing-guidelines.html): Similar to Marketing style guide and can be applied in general 

## Ensuring a Delightful Experience

To empower everyone to document their contributions to Mattermost and submit the documentation either as part of a larger PR (e.g., a code change PR) or a stand-alone PR (e.g., a new piece of content) it's important to consider that:

Mattermost engagement exists in multiple formats including:
- Marketing blogs
- Developer blogs
- PM blogs
- Technical documentation
- Support replies
- Customer education material
- Forum
- Community server

We also need to consider why contributors contribute?
- Annoyance because something is not documented. 
- People contribute if something is broken/not there.
- As part of a new feature/contribution.
- To gain experience in Open Source.

What makes people become regular contributors?
- Very clear guidelines of HOW to contribute
- Very quick response from reviewers
- Make it easy to edit, update, add content

Barriers to contributing
- Unsure where to put content
- Too many rules 
- English not first language 
- Unsure of how to structure the content (paragraphs etc)
- Comments/feedback intimidating
- Not experienced writing documentation

Taking this into account the style and tone guide needs to:
- A balance between the different types of content (blogs, technical docs, API docs).
- Understand who the contributors are (internal/external).
- Strike a balance between “Perfect” vs. “Acceptable”.
- Be aware of "High Standards" vs. understanding the nature of open source. 
- Consider the potential impact that differing standards may have on customer perception. 
- Know what type of contributions we want to increase.
- Align our expectations with what is achievable in terms of applying the guidelines and expecting adherance to them.

### Goals for Ensuring MVP Documentation with all PRs 

- Remove obstacles for community. 
- Use discretion/address “issues” quietly. 
- Build relationships wuth contributors through measured and respectful dialog. 
- Comprehensive intro document > community members encouraged to reach out
- Required/MVP otherwise inherit cost of lack of documentation which results in bigger workload for everyone. 
- Instil a culture of including docs in code PRs

## Next Steps and Recommendations

### Voice, tone, writing style

Work on the premise that "Every page is page 1" - a large portion of users enters our documentation from a Google search and lands on a page in docs. They will not often start navigating from the home page. 

- Choose four top pages to break down (either using GA or number of related open issues, e.g. Docker installation).
- Restructure and rewrite pages using shorter sentences, more bullet points, and more goal-based writing. 
- Write abstracts and use cases for each page to make them easier to understand at a glance.
- Add customer thermometer to these pages to assess whether they're effective. 
- Create samples of millennial voice vs. corporate voice.
- Create a guide for writing documentation for developers, not just writers.

### Contribution and Process Changes

- Make it easier for contributors to write docs by asking for less upfront. 
- Change the review/feedback process to cut out review time. 
- Add a step to the [developer contribution checklist](https://developers.mattermost.com/contribute/getting-started/contribution-checklist/) to include documentation in the PR.  
- Outline of what an MVP looks like (provide some examples of helpful and not helpful MVP content)
- Include the following guidelines around documentation outlining MVP documentation expectations: 

"Documenting your contribution

*When you submit a PR for your contribution, please include documentation with it. The documentation can be submitted as a new file using the following format.*

*## Title (e.g. "Compliance Reporting Notifications")*

*Details of the current feature/function and what the contribution fixes or adds. 
This can be presented as bullet points.*

*## Title (e.g. "Code Samples")*

*Include any code samples that should be included in the user-facing documentation.*

*## Title (e.g. "Process")*

*Include any processes or procedures that users have to perform to enable/use the change/addition.*

*We don't expect a huge body of documentation or that it's perfectly-written - but it's helpful to keep the following do's and don't in mind:*

*Do:*
*- Use active voice*
*- Write as you would speak - avoid using jargon if possible.*
*- Writer shorter sentences and sections - they're easier to read than walls of text.*
*- Focus on what the user wants to accomplish by being outcome-focused (get to the point concisely instead of muddling with unnecessary jargon)*
*- Remember to write for an international audience.*

*Avoid:*
*- Focusing too much on punctuation or formatting - we'll sort out that side of things.*
*- Using "he" and "she"; rather use "they" or "them". 
*- Saying "we recommend"; rather use "it's recommended". 

*During the editorial review, editors may make punctuation and/or terminology changes and commit them to save time on the review process. This only applies to punctuation/terminology - any content suggestions and questions will follow the usual review and discussion process.*

*Once the editorial review is complete, we'll move your documentation contribution to the appropriate part of the guide (if it's not there already). We'll share the URL and you can edit it at any time if you need to.*

## Style Guide Consolidation

A longer-term process is addressing current documentation, identify misalignment across the board, and bring the content up to standard. This includes all Mattermost content types but as phase one would cover technical documentation first. 

- The various style guides to be consolidated into a single big guide to begin with.
- Merge the Marketing voice/tone recommendations across the style guide to ensure a standard, casual yet professional voice is maintained across all content types.
- Large guide to be distilled into common themes and areas of alignment.
- Areas that are not aligned (such as Marketing headings vs. tech docs headings) to be discussed. 
- Voice and tone across the guide to be standardized and also presented as its own section.
- Create a terminology guide for all terminology in use across Mattermost. 
- Create a channel for communication about any updates/changes to the guide/s. 
- Nominate a representative across each team to manage style guide/section updates. 

## Technical Recommendations

- Investigate adding a linter to the build process.
- Investigate the required overhead (for example, would the linter pause the build process and block the PR until the issues are fixed?) and should we rather focus on going forward and fix current content ad-hoc?
