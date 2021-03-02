---
description: '1% DRAFT (created by Carrie Warner on March 2, 2021)'
---

# Links SEO Checklist

Ensure every page link:

* Has a clear purpose to guide the reader or a search engine to relevant Mattermost or trusted external web pages.
* Isn’t a selectable icon, navigation bar option, or button.
* Includes anchor text that clearly identifies the destination page.
  * Correct:
  * Incorrect: 
* Isn’t added more than once per web page.
* Is formatted using the HTML `<a>` tag and contains the following syntax: `<a href="url">link text</a>`
  * Correct:
  * Incorrect:
* (HTML pages only) Leverages the data library of Mattermost keywords, key phrases, and target URLs. (e.g. [example here]) Contact Jack O’Brien and the Marketing team for more information on working with the SEO data library.
* Is valid, contains no typos or other formatting errors, points to a live page, and resolves correctly when visited.

## Link to final destinations
It is also important that the `href` value points to the final destination of the target resource. Different Mattermost properties use different URL formats. 
For example, all web pages on mattermost.com end in a `/`, whereas all pages on `docs.mattermost.com` in `.html`.
* Correct: `https://mattermost.com/download/`
  * Incorrect: `https://mattermost.com/download`
  * Incorrect: `https://www.mattermost.com/download/`

While both incorrect URLs listed above take the reader to the target page, this happens only after the `mattermost.com` server first redirects the reader from the initial URL which degrades the SEO value of the link.

## Moving web pages
When moving web page content to a different location:

* Ensure that every moved page uses a 301 (permanent) redirect instead of simply adding a link on the existing page to the new page.
* Avoid creating a chain of links a user or search engine has to follow to reach the new page destination.

## Why these things matter

When you include internal links to other Mattermost collateral, you’re not only providing additional context for our customers, you’re also:
* Ensuring that search engine crawlers can find all of our web pages site’s pages.
* Passing link equity (which equals ranking power) to other Mattermost pages.
* Helping visitors navigate our online presence.
* Links in the form of icons, navigation bars, or buttons are often hidden from search engine crawlers, so ensure they are converted to links that are directly accessible on the page.
* Unclear or ambiguous anchor text such as “here” or “this page” does not identify the destination page which can negatively impact crawl rates.
* Multiple links on a single page that point to the same destination page can dilute our relevance rankings.
* When leveraging the data library, apply keywords, key phrases, and target URLs for body copy fields only. Include a maximum of x links of this type on a given web page.
* Broken links frustrate readers and can result in web pages being removed from a search engine’s index. 
* Moved content that relies on a link to forward readers and search engines to a new destination page frustrates users being forced to follow breadcrumbs, and can result in pages being removed from a search engine’s index. Using a 301 redirect transfers link equity from the page’s old location to the new URL.
