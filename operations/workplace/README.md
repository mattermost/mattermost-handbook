---
description: Description of norms on Mattermost Community server
---

# Workplace

## What is the Mattermost community server?

The Mattermost community server runs the latest stable build of Mattermost's software, including all open source code for Mattermost Team Edition as well as commercial code for Mattermost Enterprise Edition.

It has two objectives:

* Provide a workplace for Mattermost staff.
* Engage with our [communities](../../contributors/contributors/community.md), including users, contributors and partners.

**The Mattermost community server is not a production server and has occasional downtime.**

You can reach the server at:

{% embed url="https://community.mattermost.com" caption="" %}

The server is also available via the following URLs, primarily used to test pre-release features:

* [https://community-release.mattermost.com](https://community-release.mattermost.com), which runs our upcoming stable release. This server includes work-in-progress features, and can contain bugs and have occasional downtime. This server receives regular pushes of features and/or bug fixes of the next release for testing purposes.
* [https://community-daily.mattermost.com](https://community-daily.mattermost.com), which runs latest builds of Mattermost's software, including all pre-release features of our core products. It is the most unstable version of the Mattermost community server. Bugs and occasional downtime is expected as this server receives daily pushes of features and/or bug fixes for testing purposes.

The server has two teams:

### Contributors team

URL: [https://community.mattermost.com/core](https://community.mattermost.com/core/messages/@github)

Available to anyone who'd like to join the server using either an email and password account \([you can sign-up for a free account online](https://community.mattermost.com/signup_user_complete)\) or a Mattermost staff account, which is set up via Okta and requires MFA either through Okta or Google Authenticator.

### Staff team

URL: [https://community.mattermost.com/private-core](https://community.mattermost.com/private-core/channels/fy21-devops-awareness)

A confidential space for [Mattermost staff](../../contributors/contributors/community.md#mattermost-staff) requiring a Mattermost Okta›› account and MFA.

#### Staff usernames on the Mattermost server

All Mattermost staff members hired after Jan 1, 2020 should have a username in the form of `@[FIRST_NAME]_[LAST_NAME]` for example "Alice Evans" should be `alice.evans`.

If there are duplicate first name and last names, the new person added should add a middle initial in the form of `@[FIRST_NAME].[MIDDLE_INITIAL].[LAST_NAME]` for example, "Alice Janice Evans" who joined after the first Alice Evans would be `@alice.j.evans`.

There are some user accounts that for legacy issues cannot use this format, for all other Mattermost staff--even those who joined before Jan 1 2020--should use the format that creates the most clarity.

#### Not mentioning staff while referring to them

By default, people's user names and first names trigger mention notifications in Mattermost. This can be distracting if people have the same first names, for example there are multiple people named "Chris" at Mattermost. If you want to mention someone without triggering a notification consider using their three letter initials, for example, "Alice Emily Evans" would be `AEE`.

As an alternative to saying `@alice.evans` using `AEE` lets you refer to the person in passing without pushing an alert to them. For staff members that want to be alerted to even passing mentions of their name, they can opt in to that model by creating a [keyword notification](https://docs.mattermost.com/help/messaging/mentioning-teammates.html#words-that-trigger-mentions) on their three letter initials.

## Key channels for staff

The following table lists popular channels for Staff:

| Purpose | Name | Description |
| :--- | :--- | :--- |
| ANNOUNCE  Asynchronous Announcements | [Announcements](https://community.mattermost.com/private-core/channels/announcements) | **Public channel in STAFF team** for making staff-wide announcements. |
| ANNOUNCE  Synchronous Announcements | [Customer Obsession Meeting](https://handbook.mattermost.com/operations/operations/company-cadence#customer-obsession-meeting-aka-com) | **Public channel in STAFF team** for weekly all-staff meeting \(see link in header for more info on "COM", past recordings and materials, etc. |
| ANNOUNCE  New Staff Announcements | [Welcome](https://community.mattermost.com/private-core/channels/welcome) | **Public channel in STAFF team** for announcing and welcoming new staff members. |

## Channel naming conventions

Any Mattermost staff member can create, rename and archive channels on the pre-release server. When channels don't contain sensitive information they should default to **Public channel in CONTRIBUTORS team** and welcome participation by contributors.

For example, the [Loc: Seattle](https://community.mattermost.com/core/channels/loc-seattle) channel can be joined any contributor, partner or staff member to socialize with our [community](../../contributors/contributors/community.md).

We trust our staff to use names that are fast, obvious, forgiving, and also to help our colleagues with constructive suggestions when names could be improved through iteration.

The following conventions are in place for channels with common purposes:

<table>
  <thead>
    <tr>
      <th style="text-align:left">Purpose</th>
      <th style="text-align:left">Naming Convention</th>
      <th style="text-align:left">Explanation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">BUILD
        <br />
        <br />Translation Discussion</td>
      <td style="text-align:left">i18n: [LANGUAGE]</td>
      <td style="text-align:left"><b>Public channel in CONTRIBUTORS team</b> for collaborating on translations
        in different languages</td>
    </tr>
    <tr>
      <td style="text-align:left">BUILD
        <br />
        <br />Build EE with <a href="../../contributors/contributors/community.md">community</a>
      </td>
      <td style="text-align:left">EE: [FEATURE]</td>
      <td style="text-align:left"><b>Public channel in CONTRIBUTORS team</b> for openly discussing Enterprise
        Edition features with the public</td>
    </tr>
    <tr>
      <td style="text-align:left">SOCIALIZE
        <br />
        <br />Discuss geographic locations</td>
      <td style="text-align:left">Loc: [CITY OR AREA NAME]</td>
      <td style="text-align:left">
        <p><b>Public channel in CONTRIBUTORS team</b> for socializing with contributors
          including staff, partners and technical contributors in specific geographies.</p>
        <p>Use cases: Organize social and professional meet-ups</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">SUPPORT
        <br />
        <br />Support PS customers</td>
      <td style="text-align:left">PS: [Customer Name]</td>
      <td style="text-align:left"><b>Private channel in CONTRIBUTORS team</b> Channel for Premier Support
        customers engaging with senior Support Engineer</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>COLLABORATE</p>
        <p>Work with partners</p>
      </td>
      <td style="text-align:left">Partner: [Partner Name]</td>
      <td style="text-align:left"><b>Private channel in CONTRIBUTORS team</b> for discussions with close
        partners and Mattermost staff</td>
    </tr>
    <tr>
      <td style="text-align:left">OPERATE
        <br />
        <br />Plan, review and iterate on company operations with MLT</td>
      <td style="text-align:left">MLT [TOPIC]</td>
      <td style="text-align:left"><b>Private channel in STAFF team</b> for topic-specific channels for members
        of <a href="groups.md#mattermost-leadership-team-mlt">Mattermost Leadership Team</a> to
        work on <a href="../operations/mlt-cadence/">Mattermost cadence</a>, E.g.
        MLT Daily, MLT R&amp;D, etc.</td>
    </tr>
    <tr>
      <td style="text-align:left">OPERATE
        <br />
        <br />Plan, review and iterate on company operations with MLX</td>
      <td style="text-align:left">MLX [TOPIC]</td>
      <td style="text-align:left"><b>Private channel in STAFF team</b> for topic-specific channels for members
        of <a href="groups.md#mattermost-leadership-team-extended-mxt">Mattermost Leadership Extended Team</a>.
        E.g. MLX Recruiting, MLT HR, etc.</td>
    </tr>
  </tbody>
</table>

## Email distribution lists 

Workplace messaging solutions like Mattermost are excellent for real-time and topic-based communications.

When it comes to long-form cascaded communications (announced information to be forwarded to groups with context from different leaders), then email and email distribution lists are best, and we do use them at Mattermost.

We have a [Mattermost Board summarizing email distributions lists at Mattermost](https://community.mattermost.com/boards/workspace/4xg6hw6a37bk883ijc3n4n7ofr/b8zc7hz4o37n6jyhgcayx5wcjcc/vpyxigmqm4pbmub4jxm7pdkumgr) (you need to be a staff member subscribed to our Announcements channel for access).
