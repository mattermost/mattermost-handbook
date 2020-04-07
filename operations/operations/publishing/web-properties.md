# Public Web Properties

This page is a work in progress.

## Areas of Ownership

Below is a summary of our public web properties, including their target content, publishing system and areas of ownership:

| Domain | Content | Publishing System | Content Owner | Quality Control Owner |
| :--- | :--- | :--- | :--- | :--- |
| docs.mattermost.com | Technical product documentation for end users, administrators and developers | Exploring Hugo with Markdown\*\* | [Justine Geffen](http://github.com/justinegeffen) | [Justine Geffen](http://github.com/justinegeffen) and [Amy Blais](http://github.com/amyblais) |
| TBD | Technical articles, guides, videos, and courses | Exploring Hugo with Markdown\*\* | [Jason Blais](http://github.com/jasonblais) | [Sebastian Faase](https://github.com/faase) |
| TBD | Contributor documentation and relevant community communications | Exploring Hugo with Markdown\*\* | [Joram Wilander](http://github.com/jwilander) | [Joram Wilander](http://github.com/jwilander) |
| TBD | Self-service support content, including knowledge-based FAQs | TBD | Craig Willis | Craig Willis |
| handbook.mattermost.com | Internal processes for company operations and recruiting | GitBook with Markdown | [Hilary Clarke](https://github.com/hilaryclarke) | [Justine Geffen](http://github.com/justinegeffen) and [Amy Blais](http://github.com/amyblais) |
| mattermost.com | Commercial site, including blogs, product offerings, customer case studies and more | Wordpress | Zach Trayner | Lauren Nguyen |

\*\* We are exploring Hugo as the system of choice for documentation sites, given it supports advanced search, Markdown language and a GitHub review process to ensure consistent quality across the site. [https://github.com/mattermost/mattermost-documentation](https://github.com/mattermost/mattermost-documentation)

## Information Architecture

Below is the tentative top-level information architecture for each of the above domains, work in progress.

See a [more detailed analysis on information architecture recommendations](https://docs.google.com/document/d/1CaRpCo0Aic-bDIKGtIA5mbtaH7JarCH-3v7rP-SBFHk/edit#) for Docs, Education, Community and Support.

### handbook.mattermost.com

The handbook is developed with the following structure:

* About Mattermost, including mission, vision, leadership principles; company, and history
* Culture, including our remote-first culture, standards and MatterCon
* Join Us, including why to work at Mattermost and open positions
* Onboarding, including guides for new staff and managers
* Operations, including mindsets, cadences, metrics, and definitions

### .../docs

Since much software follows recognizable patterns these days, product documentation is shaped into familiar schemas. This often takes the form of product areas/topics, or common use cases.

Thus, information architecture is organized by topic or use case, such as below \(exact architecture yet to be determined\):

* Install and Configuration
* Deployment
* User Management
* System Administration
* Account Settings and Notifications
* Integrations and Plugins
* RESTful API
* Customization

Good examples of this approach include: [Stripe](https://stripe.com/docs) \| [Docker](https://docs.docker.com/) \| [Twilio](https://www.twilio.com/docs)

### .../education

Here, the focus is on providing learners access to content by their learning style and provides a mechanism with a currently limited scale of content. It is divided into three categories:

* Guides
* Videos
* Courses

From here, further organization based on themes \(informed by persona use cases\), as content is made available.

Later, as content evolves, content may be based on particular personas and their learning paths.

### .../community

Here, the information architecture is organized by [types of community members](https://docs.mattermost.com/process/community-overview.html), including users and contributors.

A sample architecture for contributors may look like:

* Contributor Process
* Platform and Solution Development, including content in [https://developers.mattermost.com](https://developers.mattermost.com)
* Translations
* Documentation
* etc. ..

### .../support

No information architecture is yet defined, but in general they will consist of

* Support Resources \(including peer-to-peer forums\)
* Knowledge Base FAQs

### mattermost.com

The Mattermost website is developed with the following architecture:

* Product, including features and integrations
* Pricing
* Solutions, including use cases
* Case Studies
* Resources, including training and blog
* Docs, including installation and configuration

