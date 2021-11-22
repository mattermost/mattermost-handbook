# Release Scorecard Definitions

[Google spreadsheet](https://docs.google.com/spreadsheets/d/1Aoj4OTaWoyrKIcQNiHH1MVoRG51T20Y_0w2tg5oVw-M/edit#gid=825551144)

## Release Output

<table>
  <thead>
    <tr>
      <th style="text-align:left">Metric</th>
      <th style="text-align:left">How to Measure</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Ratio of story-to-bug tickets</td>
      <td style="text-align:left">Total of feature tickets over total of bug tickets. Include current quality
        release and previous feature release.</td>
    </tr>
    <tr>
      <td style="text-align:left">Mean time from P1 bug report to delivery</td>
      <td style="text-align:left">
        <p>With a new or existing Jira filter, with:</p>
        <ol>
          <li>Project = Mattermost</li>
          <li>Fix Versions = Latest released version</li>
          <li>Issue Type = Bug</li>
          <li>Label = P1</li>
          <li>Created Date = 17th of the previous month</li>
          <li>Release Date = 16th of the current month</li>
        </ol>
        <p>Copy a list of Jira tickets with the above information and paste them
          into a spreadsheet. Calculate the average by using a formula &#x201C;=Release
          Day-Created&#x201D;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Mean time from P2 bug report to delivery</td>
      <td style="text-align:left">
        <p>With a new or existing Jira filter, with:</p>
        <ol>
          <li>Project = Mattermost</li>
          <li>Fix Versions = Latest released version</li>
          <li>Issue Type = Bug</li>
          <li>Label = P2</li>
          <li>Created Date = 17th of the previous month</li>
          <li>Release Date = 16th of the current month</li>
        </ol>
        <p>Copy a list of Jira tickets with the above information and paste them
          into a spreadsheet. Calculate the average by using a formula &#x201C;=Release
          Day-Created&#x201D;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Mean time from P3 bug report to delivery</td>
      <td style="text-align:left">
        <p>With a new or existing Jira filter, with:</p>
        <ol>
          <li>Project = Mattermost</li>
          <li>Fix Versions = Latest released version</li>
          <li>Issue Type = Bug</li>
          <li>Label = P3</li>
          <li>Created Date = 17th of the previous month</li>
          <li>Release Date = 16th of the current month</li>
        </ol>
        <p>Copy a list of Jira tickets with the above information and paste them
          into a spreadsheet. Calculate the average by using a formula &#x201C;=Release
          Day-Created&#x201D;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Number of P1 bugs reported in production</td>
      <td style="text-align:left">Count of major issues reported in product, documentation or marketing
        by customers, CSMs, Support, or Product (e.g. dot releases from customer
        reports, undocumented breaking changes).</td>
    </tr>
    <tr>
      <td style="text-align:left">Number of P2 bugs reported in production</td>
      <td style="text-align:left">Count of medium level issues reported in product, documentation or marketing
        by customers, CSMs, Support, or Product (e.g. dot releases from customer
        reports, undocumented breaking changes).</td>
    </tr>
    <tr>
      <td style="text-align:left">Number of P3 bugs reported in production</td>
      <td style="text-align:left">Count of small issues reported in product, documentation or marketing
        by customers, CSMs, Support, or Product (e.g. dot releases from customer
        reports, undocumented breaking changes).</td>
    </tr>
  </tbody>
</table>

## Release Management

| Metric | How to Measure |
| :--- | :--- |
| Number of misses in each release cycle | Count of issues encountered during the release cycle \(e.g. no process for an early advance notification for upcoming deprecated ESR\). |
| Number of setbacks to users/staff resulting in a negative reaction | Manual count of negative reactions reported by CSMs, Support, or Product \(e.g. features that got pushed\). |
| Number of measurable actions from each Release Retrospective driven from root causes and completed and reported to R&D | Count of completed and reported items from Release Retrospective document. |
| Number of deadlines missed in Release Checklist | Manual count of deadlines not met from items posted to Release Checklist. |

## Release Hearbeat

<table>
  <thead>
    <tr>
      <th style="text-align:left">Metric</th>
      <th style="text-align:left">How to Measure</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Time updated to RC1 (PST)</td>
      <td style="text-align:left">Check Release Discussion channel history for date/time RC1 was cut.</td>
    </tr>
    <tr>
      <td style="text-align:left">How many RCs cut</td>
      <td style="text-align:left">Check Release Discussion channel history for how many RCs were cut for
        that release.</td>
    </tr>
    <tr>
      <td style="text-align:left">Number of days between when final RC is cut and the release date</td>
      <td
      style="text-align:left">Check Release Discussion channel for post with official release build.
        Oxygen = 16th - Day Final RC is cut</td>
    </tr>
    <tr>
      <td style="text-align:left">Community + customer bugs reported during release timeframe (17th to 16th)</td>
      <td
      style="text-align:left">
        <p>With a new or existing Jira filter, with:</p>
        <ol>
          <li>Project = Mattermost</li>
          <li>Fix Versions = Latest released version</li>
          <li>Issue Type = Bug</li>
          <li>Label = Customer-bug and Community-bug</li>
          <li>Created Date = 17th of the previous month</li>
          <li>Release Date = 16th of the current month</li>
        </ol>
        </td>
    </tr>
    <tr>
      <td style="text-align:left">Number of customer bugs fixed during release</td>
      <td style="text-align:left">
        <p>With a new or existing Jira filter, with:</p>
        <ol>
          <li>Project = Mattermost</li>
          <li>Fix Versions = Latest released version</li>
          <li>Issue Type = Bug</li>
          <li>Status = Closed and Resolved</li>
          <li>Label = Customer-bug</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Total valid bugs in fix version</td>
      <td style="text-align:left">
        <p>After closing current release:</p>
        <p>project = Mattermost AND issuetype = Bug AND resolution not in (Duplicate,
          &quot;Cannot Reproduce&quot;, &quot;Won&apos;t Fix&quot;) AND fixVersion
          = latestReleasedVersion()</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Total valid bugs in fix version found by test automation</td>
      <td style="text-align:left">Check &quot;Se&quot;, &quot;Selenium-found, &quot;Rainforest-found&quot;
        Jira labels.</td>
    </tr>
    <tr>
      <td style="text-align:left">Total valid bugs found after RC1 is cut</td>
      <td style="text-align:left">
        <p>After closing current release, adjust dates as per above, and use this
          Jira query:</p>
        <ol>
          <li>Check Jira timezone + Pre-release timezone and make sure times match</li>
          <li>Replace START with date (yyyy-MM-dd HH:mm) RC1 was cut</li>
          <li>Replace END with date (yyyy-MM-dd HH:mm) test servers returned to master</li>
        </ol>
        <p>project = Mattermost AND issuetype = Bug AND resolution not in (Duplicate,
          &quot;Cannot Reproduce&quot;, &quot;Won&apos;t fix&quot;) AND created &gt;
          &quot;START&quot; AND created &lt; &quot;END&quot;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Valid bugs found after RC1 fixed in release</td>
      <td style="text-align:left">
        <p>After closing current release, adjust dates as per above, and use this
          Jira query:</p>
        <p>project = Mattermost AND issuetype = Bug AND resolution not in (Duplicate,
          &quot;Cannot Reproduce&quot;, &quot;Won&apos;t Fix&quot;) AND created &gt;
          &quot;START&quot; AND created &lt; &quot;END&quot; AND fixVersion = latestReleasedVersion()</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Valid bugs found after RC1 pushed to next release</td>
      <td style="text-align:left">
        <p>After closing current release, adjust dates as per above, and use this
          Jira query:</p>
        <p>project = Mattermost AND issuetype = Bug AND resolution not in (Duplicate,
          &quot;Cannot Reproduce&quot;, &quot;Won&apos;t Fix&quot;) AND created &gt;
          &quot;START&quot; AND created &lt; &quot;END&quot; AND fixVersion = earliestUnreleasedVersion()</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Valid bugs found after RC1 fix version = other (eg unscheduled, not set)</td>
      <td
      style="text-align:left">
        <p>After closing current release, adjust dates as per above, and use this
          Jira query:</p>
        <p>project = Mattermost AND issuetype = Bug AND created &gt; &quot;START&quot;
          AND created &lt; &quot;END&quot; AND resolution not in (Duplicate, &quot;Cannot
          Reproduce&quot;, &quot;Won&apos;t Fix&quot;) AND (fixVersion not in (latestReleasedVersion(),
          earliestUnreleasedVersion()) OR fixVersion is EMPTY)</p>
        </td>
    </tr>
    <tr>
      <td style="text-align:left">(Non-security) Bugs requiring patch release</td>
      <td style="text-align:left">After any patch release goes out (after the normal release date): Check
        Changelog for total number of non-security patch releases.</td>
    </tr>
    <tr>
      <td style="text-align:left">Total features/improvements in fix version</td>
      <td style="text-align:left">
        <p>With a new or existing Jira filter, with:</p>
        <ol>
          <li>Project = Mattermost</li>
          <li>Fix Versions = Latest released version</li>
          <li>Issue Type = Story</li>
          <li>Status = Closed and Resolved</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Critical security issues found during release timeframe</td>
      <td style="text-align:left">
        <p>With a new or existing Jira filter, check for Security Vulnerability tickets:</p>
        <ol>
          <li>Project = Mattermost</li>
          <li>Fix Versions = Latest released version</li>
          <li>Impact = High</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Moderate security issues found during release timeframe</td>
      <td style="text-align:left">
        <p>With a new or existing Jira filter, check for Security Vulnerability tickets:</p>
        <ol>
          <li>Project = Mattermost</li>
          <li>Fix Versions = Latest released version</li>
          <li>Impact = Medium</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Minor security issues found during release timeframe</td>
      <td style="text-align:left">
        <p>With a new or existing Jira filter, check for Security Vulnerability tickets:</p>
        <ol>
          <li>Project = Mattermost</li>
          <li>Fix Versions = Latest released version</li>
          <li>Impact = Low</li>
        </ol>
      </td>
    </tr>
  </tbody>
</table>

