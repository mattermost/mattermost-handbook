---
description: 1% draft
---

# Public Web Properties

Below is a summary of our public web properties, including their target content, publishing system and areas of ownership:

Domain | Content | Publishing System | Content Owner | Quality Control Owner
--- | --- | --- | --- | ---
your.mattermost.com/docs | Technical product documentation for end users, administrators and developers | Hugo with Markdown | [Justine Geffen](http://github.com/justinegeffen) | [Justine Geffen](http://github.com/justinegeffen) and [Amy Blais](http://github.com/amyblais)
your.mattermost.com/education | Technical articles, guides, videos, and courses should live | Hugo with Markdown | [Jeff Wayman](http://github.com/jwayman) | [Jeff Wayman](http://github.com/jwayman)
your.mattermost.com/community | Contributor documentation and relevant community communications | Hugo with Markdown | [Joram Wilander](http://github.com/jwilander) | [Joram Wilander](http://github.com/jwilander)
your.mattermost.com/support | Self-service support content, including knowledge-based FAQs | TBD | Craig Willis | Craig Willis
handbook.mattermost.com | Internal processes for company operations and recruiting | GitBook with Markdown | [Jason Blais](http://github.com/jasonblais) | [Justine Geffen](http://github.com/justinegeffen) and [Amy Blais](http://github.com/amyblais)
mattermost.com | Commercial site, including blogs, product offerings, customer case studies and more | Wordpress | Zach Trayner | Lauren Nguyen

Note that Hugo is the system of choice for documentation sites, given it supports advanced search, Markdown language and a GitHub review process to ensure consistent quality across the site. The handbook may be migrated to this system in the future as well.

## Information Architecture

Below is the top-level information architecture for each of the above domains.

See a [more detailed analysis on information architecture recommendations](https://docs.google.com/document/d/1CaRpCo0Aic-bDIKGtIA5mbtaH7JarCH-3v7rP-SBFHk/edit#) for Docs, Education, Community and Support.

### handbook.mattermost.com

The handbook is developed with the following structure:

 - About Mattermost, including mssion, vision, values, company, history, mindsets, metrics, and definitions
 - Remote-First Culture and Standards
 - Join Us
 - Onboarding
 - Operations, including cadences

### your.mattermost.com/docs

Since much software follows recognizable patterns these days, product documentation is shaped into familiar schemas. This often takes the form of product areas/topics, or common use cases.

Thus, information architecture is organized by topic or use case, such as below (exact architecture yet to be determined):

 - Install and Configuration
 - Deployment
 - User Management
 - System Administration
 - Account Settings and Notifications
 - Integrations and Plugins
 - RESTful API
 - Customization

Good examples of this approach include: [Stripe](https://stripe.com/docs) | [Docker](https://docs.docker.com/) | [Twilio](https://www.twilio.com/docs)

### your.mattermost.com/education

Here, the focus is on providing learners access to content by their learning style and provides a mechanism with a currently limited scale of content. It is divided into three categories:

 - Guides
 - Videos
 - Courses

From here, further organization based on themes (informed by persona use cases), as content is made available.

Later, as content evolves, content may be based on particular personas and their learning paths.

### your.mattermost.com/community

Here, the information architecture is organized by [types of community members](https://docs.mattermost.com/process/community-overview.html), including users and contributors.

A sample architecture for contributors may look like:

 - Contributor Process
 - Platform and Solution Development, including content in https://developers.mattermost.com
 - Translations
 - Documentation
 - etc. ..

### your.mattermost.com/support

No strict information architecture is yet defined, but in general they will consist of

 - Support Resources (including peer-to-peer forums)
 - Knowledge Base FAQs

### mattermost.com

The Mattermost website is developed with the following structure:

 - Product, including features and integrations
 - Pricing
 - Solutions, including use cases
 - Case Studies
 - Resources
