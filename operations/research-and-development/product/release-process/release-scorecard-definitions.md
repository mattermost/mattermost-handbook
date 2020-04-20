# Release Scorecard Definitions

For
https://docs.google.com/spreadsheets/d/1Aoj4OTaWoyrKIcQNiHH1MVoRG51T20Y_0w2tg5oVw-M/edit#gid=825551144

## Release Output

<table>
<colgroup>
<col style="width: 46%" />
<col style="width: 53%" />
</colgroup>
<thead>
<tr class="header">
<th>Metric</th>
<th>How to Measure</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Ratio of story-to-bug tickets</td>
<td>Total of feature tickets over total of bug tickets. Include current quality release and previous feature release.</td>
</tr>
<tr class="even">
<td>Mean time from P1 bug report to delivery</td>
<td><p>With a new or existing Jira filter, with:</p>
<ol type="1">
<li>Project = Mattermost</li>
<li>Fix Versions = Latest released version</li>
<li>Issue Type = Bug</li>
<li>Label = P1</li>
<li>Created Date = 17th of the previous month</li>
<li>Release Date = 16th of the current month</li>
</ol>
<p>Copy a list of Jira tickets with the above information and paste them into a spreadsheet. Calculate the average by using a formula “=Release Day-Created”.</p></td>
</tr>
<tr class="odd">
<td>Mean time from P2 bug report to delivery</td>
<td><p>With a new or existing Jira filter, with:</p>
<ol type="1">
<li>Project = Mattermost</li>
<li>Fix Versions = Latest released version</li>
<li>Issue Type = Bug</li>
<li>Label = P2</li>
<li>Created Date = 17th of the previous month</li>
<li>Release Date = 16th of the current month</li>
</ol>
<p>Copy a list of Jira tickets with the above information and paste them into a spreadsheet. Calculate the average by using a formula “=Release Day-Created”.</p></td>
</tr>
<tr class="even">
<td>Mean time from P3 bug report to delivery</td>
<td><p>With a new or existing Jira filter, with:</p>
<ol type="1">
<li>Project = Mattermost</li>
<li>Fix Versions = Latest released version</li>
<li>Issue Type = Bug</li>
<li>Label = P3</li>
<li>Created Date = 17th of the previous month</li>
<li>Release Date = 16th of the current month</li>
</ol>
<p>Copy a list of Jira tickets with the above information and paste them into a spreadsheet. Calculate the average by using a formula “=Release Day-Created”.</p></td>
</tr>
<tr class="odd">
<td>Number of P1 bugs reported in production</td>
<td>Bug severity guidelines are in progress, after which a Jira query will be built</td>
</tr>
<tr class="even">
<td>Number of P2 bugs reported in production</td>
<td>Bug severity guidelines are in progress, after which a Jira query will be built</td>
</tr>
<tr class="odd">
<td>Number of P3 bugs reported in production</td>
<td>Bug severity guidelines are in progress, after which a Jira query will be built</td>
</tr>
</tbody>
</table>

## Release Management

<table>
<colgroup>
<col style="width: 46%" />
<col style="width: 53%" />
</colgroup>
<thead>
<tr class="header">
<th>Metric</th>
<th>How to Measure</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Number of misses in each release cycle</td>
<td>Same as number of bugs reported in production, + count of issues reported in documentation or marketing by customers, CSMs, Support or Product. E.g. dot releases from customer reports, undocumented breaking changes.</td>
</tr>
<tr class="even">
<td>Number of setbacks to users/staff resulting in a negative reaction</td>
<td>Manual count of negative reactions reported by CSMs, Support or Product. E.g. features that got pushed.</td>
</tr>
<tr class="odd">
<td>Number of measurable actions from each release retrospective driven from root causes & completed and reported to R&D</td>
<td>Count of completed and reported items from Release Retrospective document.</td>
</tr>
<tr class="even">
<td>Number of deadlines missed in release checklist</td>
<td>Manual count of deadlines not met from items posted to Release Checklist.</td>
</tr>
</tbody>
</table>

## Release Hearbeat

<table>
<colgroup>
<col style="width: 34%" />
<col style="width: 65%" />
</colgroup>
<thead>
<tr class="header">
<th>Metric</th>
<th>How to Measure</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Time updated to RC1 (PST)</td>
<td>Check Release Discussion channel history for date/time RC1 was cut.</td>
</tr>
<tr class="even">
<td>How many RCs cut</td>
<td>Check Release Discussion channel history for how many RCs were cut for that release.</td>
</tr>
<tr class="odd">
<td>Number of days between when final RC is cut and the release date</td>
<td>Check Release Discussion channel for post with official release build. Oxygen = 16th - Day Final RC is cut</td>
</tr>
<tr class="even">
<td>Community + customer bugs reported during release timeframe (17th to 16th)</td>
<td><p>With a new or existing Jira filter, with:</p>
<ol type="1">
<li>Project = Mattermost</li>
<li>Fix Versions = Latest released version</li>
<li>Issue Type = Bug</li>
<li>Label = Customer-bug and Community-bug</li>
<li>Created Date = 17th of the previous month</li>
<li>Release Date = 16th of the current month</li>
</ol></td>
</tr>
<tr class="odd">
<td>Number of customer bugs fixed during release</td>
<td><p>With a new or existing Jira filter, with:</p>
<ol type="1">
<li>Project = Mattermost</li>
<li>Fix Versions = Latest released version</li>
<li>Issue Type = Bug</li>
<li>Status = Closed and Resolved</li>
<li>Label = Customer-bug</li>
</ol></td>
</tr>
<tr class="even">
<td>Total valid bugs in fix version</td>
<td><p>After closing current release:</p>
<p>project = Mattermost AND issuetype = Bug AND resolution not in (Duplicate, "Cannot Reproduce", "Won't Fix") AND fixVersion = latestReleasedVersion()</p></td>
</tr>
<tr class="odd">
<td>Total valid bugs in fix version found by test automation</td>
<td>Check "Se", "Selenium-found, "Rainforest-found" Jira labels.</td>
</tr>
<tr class="even">
<td>Total valid bugs found after RC1 is cut</td>
<td><p>After closing current release, adjust dates as per above, and use this Jira query:</p>
<ol type="1">
<li>Check Jira timezone + Pre-release timezone and make sure times match</li>
<li>Replace START with date (yyyy-MM-dd HH:mm) RC1 was cut</li>
<li>Replace END with date (yyyy-MM-dd HH:mm) test servers returned to master</li>
</ol>
<p>project = Mattermost AND issuetype = Bug AND resolution not in (Duplicate, "Cannot Reproduce", "Won't fix") AND created &gt; "START" AND created &lt; "END"</p></td>
</tr>
<tr class="even">
<td>Valid bugs found after RC1 fixed in release</td>
<td><p>After closing current release, adjust dates as per above, and use this Jira query:</p>
<p>project = Mattermost AND issuetype = Bug AND resolution not in (Duplicate, "Cannot Reproduce", "Won't Fix") AND created &gt; "START" AND created &lt; "END" AND fixVersion = latestReleasedVersion()</p></td>
</tr>
<tr class="odd">
<td>Valid bugs found after RC1 pushed to next release</td>
<td><p>After closing current release, adjust dates as per above, and use this Jira query:</p>
<p>project = Mattermost AND issuetype = Bug AND resolution not in (Duplicate, "Cannot Reproduce", "Won't Fix") AND created &gt; "START" AND created &lt; "END" AND fixVersion = earliestUnreleasedVersion()</p></td>
</tr>
<tr class="even">
<td>Valid bugs found after RC1 fix version = other (eg unscheduled, not set)</td>
<td><p>After closing current release, adjust dates as per above, and use this Jira query:</p>
<p>project = Mattermost AND issuetype = Bug AND created &gt; "START" AND created &lt; "END" AND resolution not in (Duplicate, "Cannot Reproduce", "Won't Fix") AND (fixVersion not in (latestReleasedVersion(), earliestUnreleasedVersion()) OR fixVersion is EMPTY)</p></td>
</tr>
<tr class="odd">
<td>(Non-security) Bugs requiring patch release</td>
<td>After any patch release goes out (after the normal release date): Check Changelog for total number of non-security patch releases.</td>
</tr>
<tr class="even">
<td>Total features/improvements in fix version</td>
<td><p>With a new or existing Jira filter, with:</p>
<ol type="1">
<li>Project = Mattermost</li>
<li>Fix Versions = Latest released version</li>
<li>Issue Type = Story</li>
<li>Status = Closed and Resolved</li>
</ol></td>
</tr>
<tr class="odd">
<td>Critical security issues found during release timeframe</td>
<td><p>With a new or existing Jira filter, check for Security Vulnerability tickets:</p>
<ol type="1">
<li>Project = Mattermost</li>
<li>Fix Versions = Latest released version</li>
<li>Impact = High</li>
</ol></td>
</tr>
<tr class="even">
<td>Moderate security issues found during release timeframe</td>
<td><p>With a new or existing Jira filter, check for Security Vulnerability tickets:</p>
<ol type="1">
<li>Project = Mattermost</li>
<li>Fix Versions = Latest released version</li>
<li>Impact = Medium</li>
</ol></td>
</tr>
<tr class="odd">
<td>Minor security issues found during release timeframe</td>
<td><p>With a new or existing Jira filter, check for Security Vulnerability tickets:</p>
<ol type="1">
<li>Project = Mattermost</li>
<li>Fix Versions = Latest released version</li>
<li>Impact = Low</li>
</ol></td>
</tr>
</tbody>
</table>

