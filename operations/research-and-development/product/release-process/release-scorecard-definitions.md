# Release Scorecard Definitions

 - [Spreadsheet](https://docs.google.com/spreadsheets/d/1Aoj4OTaWoyrKIcQNiHH1MVoRG51T20Y_0w2tg5oVw-M/edit#gid=825551144)

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
      <td style="text-align:left">Date/time RC1 cut (PST)</td>
      <td style="text-align:left">Check Release Self-Hosted/Cloud channel history for date/time RC1 was cut.</td>
    </tr>
    <tr>
      <td style="text-align:left">Total number of RCs cut</td>
      <td style="text-align:left">Check Release Self-Hosted/Cloud channel history for how many RCs were cut for
        that release.</td>
    </tr>
    <tr>
      <td style="text-align:left">Number of days the final build is cut before the 16th</td>
      <td
      style="text-align:left">Check Release Self-Hosted/Cloud channel for post with official release build.
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
      <td style="text-align:left">Number of bugs reported within a week after the release</td>
      <td style="text-align:left">
        <p>With a new or existing Jira filter, with:</p>
        <ol>
          <li>Project = Mattermost</li>
          <li>Issue Type = Bug</li>
          <li>Status = Open</li>
          <li>Label = Customer-bug and Community-bug</li>
          <li>Created Date = Between the 16th and 23rd of the month</li>
        </ol>
      </td>
    </tr>
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
      <td style="text-align:left">Total valid bug fixes in fix version</td>
      <td style="text-align:left">
        <p>After closing current release:</p>
        <p>project = Mattermost AND issuetype = Bug AND resolution not in (Duplicate,
          &quot;Cannot Reproduce&quot;, &quot;Won&apos;t Fix&quot;) AND fixVersion
          = latestReleasedVersion()</p>
      </td>
    </tr>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Total valid regression fixes in fix version</td>
      <td style="text-align:left">
        <p>After closing current release:</p>
        <p>project = Mattermost AND issuetype = Bug AND resolution not in (Duplicate,
          &quot;Cannot Reproduce&quot;, &quot;Won&apos;t Fix&quot;) AND fixVersion
          = latestReleasedVersion() AND label = rc2, rc3</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Valid bugs found after RC1 is pushed to next release</td>
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
      <td style="text-align:left">Total valid bugs found after RC1 is cut</td>
      <td style="text-align:left">
        <p>After closing current release, adjust dates as per above, and use this
          Jira query:</p>
        <ol>
          <li>Check Jira timezone + Community server timezone and make sure times match</li>
          <li>Replace START with date (yyyy-MM-dd HH:mm) RC1 was cut</li>
          <li>Replace END with date (yyyy-MM-dd HH:mm) release was published</li>
        </ol>
        <p>project = Mattermost AND issuetype = Bug AND resolution not in (Duplicate,
          &quot;Cannot Reproduce&quot;, &quot;Won&apos;t fix&quot;) AND created &gt;
          &quot;START&quot; AND created &lt; &quot;END&quot;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Number of PRs reverted</td>
      <td style="text-align:left">Check recently merged GitHub PRs (with the word "Revert" in the PR title).</td>
    </tr>
    <tr>
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
  </tbody>
</table>
