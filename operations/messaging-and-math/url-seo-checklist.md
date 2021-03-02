---
description: '1% DRAFT (created by Carrie Warner on March 2, 2021)'
---

# URL SEO Checklist

Ensure all website URLs: 
* Clearly describe the contents of the page.
  * Correct: `https://docs.mattermost.com/help/getting-started/organizing-your-sidebar.html`
  * Incorrect: `https://docs.mattermost.com/mobile/mobile-appconfig.html`

* Are between x and y characters long.
* Are unique across the website.

* Follow a consistent pattern in their naming convention.
  * Correct: `https://docs.mattermost.com/help/messaging/mentioning-teammates.html`
  * Incorrect: `https://docs.mattermost.com/help/messaging/emoji.html`

* Are human readable and consist only of characters, dashes, and periods.
  * Correct: `https://docs.mattermost.com/administration/custom-terms-of-service.html`
  * Incorrect: `https://docs.mattermost.com/deployment/cluster-310.html`

* Are links you would personally feel safe clicking on because the destination URL looks obvious and legitimate.
  * Correct: `https://docs.mattermost.com/cloud/cloud-administration/custom-terms-of-service.html`
  * Incorrect: `http://www.5z8.info/_x2r3rq_5waystowin`

* Don’t include a mix of capital letters and lower-case characters.
  * Correct: `https://docs.mattermost.com/administration/data-retention-policy.html`
  * Incorrect: `https://docs.mattermost.com/administration/Data-Retention-Policy.html`

* Use only hyphens to separate multiple words.
  * Correct: `https://docs.mattermost.com/install/install-ubuntu-2004.html`
  * Incorrect: `https://docs.mattermost.com/install/install-ubuntu-20.04.html`

* Don’t run multiple words together without a hyphen separator.
  * Correct: `https://docs.mattermost.com/install/mattermost-omnibus.html#backup-and-restore-using-the-mattermost-omnibus-cli`
  * Incorrect: `https://docs.mattermost.com/install/mattermost-omnibus.html#backupandrestore-mattermost-omnibus-cli`

* Ensure that each website repository:
  *  Includes a `Robots.txt` file located in the root directory of the repository that instructs search engines on how to crawl and index the website.

## Why these things matter
* URLs are visible in search results.
* URLs need to be long enough to be clearly descriptive, but short enough to avoid being cut off by the search engine when returning it as a search result.
* Only one version of a URL for a given page should exist. Multiple versions dilute the organization’s online presence.
* Keywords in URLs must be used judiciously and thoughtfully, particularly across subfolders and sub pages. Using the same keywords repeatedly across pages negatively affects search engine crawl rates.
* URLs should be constructed such that they teach visitors and search engines how the site is organized and where information can be found. 
* Search engines can incorrectly interpret URLs that contain parameters, numbers, or symbols. It’s best to avoid these symbols altogether in URLs.
* Keyword overuse in URLs can appear spammy and manipulative. If the URL doesn’t look legitimate to you, it would likely look questionable to a potential customer too. 
* Case sensitive URLs increase the risk that the URL will be incorrectly entered or linked to. For sites that contain indexed mixed-case URLs already, a rewrite formula can be added to the .htaccess file to automatically convert uppercase URLs to lowercase.
* Not all web apps accurately interpret separators such as underscores `_`, plus signs `+`,  spaces `that resolve as %20`, or URLs where multiple words run together without any separators. 
* If there are aspects of the website that should not be crawled or indexed, these details must be included in the `Robots.txt` file. 
