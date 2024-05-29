# Working on Security-sensitive Pull Requests

## Overview

This document aims to lay down some guidelines on how to work with security-sensitive changes in public Git repositories.

## Goals

Establish and document a way of working that:

 1. Minimizes the risk of vulnerability information leaking out before a fix is made available.
 2. Minimizes the friction caused for developers, QA, and security engineers actively working on a security issue.
 3. Is easy to understand and adopt, given the existing PR process.
 4. Is easy to remember and follow.

## Scope

The guidelines documented here only apply to open source products maintained by Mattermost. Closed-source work does not have the same considerations and does not need to follow the guidelines laid out here.

## Background reading

Similar documentation by Mozilla used as the inspiration for this document: https://firefox-source-docs.mozilla.org/bug-mgmt/processes/fixing-security-bugs.html

## Guidelines by engineering area

The guidelines below are split by work area; start by reading the [Common Guidelines](#common-guidelines) section, then proceed to whichever follow-up section is relevant to you.

### Common guidelines

When working on security-sensitive changes, pay attention to what is public and what is not. Be mindful about entering information into systems such as Mattermost Channels and Boards, GitHub Issues and Pull Requests, and Jira.

When discussing related work in public channels, such as a CI pipeline failure blocking the security release or feature work that had to be postponed because of the incident, pay attention to the ways you reference the private information. Avoid sharing ticket IDs or mentioning key words like "security": every time you reference the issue in an identifiable way, you add contextual information, and that information can eventually add up to something that's useful to an attacker.
Specific words and phrases to be extra careful with:

 - Obvious key words: "security", "vulnerability", "exploit", "insecure", "attack".
 - Anything that identifies a vulnerability type: "XSS", "authentication bypass", "authorization bug", "SQL injection", "remote code execution", etc.
 - Security-specific tools and terminology: "HackerOne", "CVE", "CVSS", "advisory", "pentest".

### Guidelines for developers

When developing a fix for a security issue, bear in mind that the code, comments, unit tests, and commit messages become public information as soon as they are pushed to the remote repository. Apply [Common Guidelines](#common-guidelines) accordingly.

**When commenting on your code**, keep references to security issues to a minimum. For example: If it's necessary to highlight that a non-obvious validation check is necessary for security, avoid the following:

{% hint style="danger" %}
```go
// Do not remove! This check prevents a security issue!
if url.Opaque != "" {
    return "", errors.New("malformed URL");
}
```
{% endhint %}

Instead refer to the ticket ID or some other opaque identifier only:

{% hint style="success" %}
```go
// See MM-1234
if url.Opaque != "" {
    return "", errors.New("malformed URL");
}
```
{% endhint %}

With the latter, any other staff member or your future self can still easily find the context, but you avoid pointing out to would-be attackers that the change is critical for security.

**When developing unit/e2e tests**, do not use the Proof-of-Concept (PoC) exploits received from the security team or documented on the vulnerability ticket as-is: the purpose of these PoCs is to clearly demonstrate the security issue and its implications, which often means they are very easy to "weaponize". Instead, test the intended functionality using more benign payloads. For example in the case of a Cross-Site Scripting (XSS) issue resulting from missing HTML special character escaping, test the fix using sets of individual characters or garbage input instead of a full XSS payload. If you are unsure about your approach to testing, ask the Security team!

**When submitting PRs**, pay attention to the PR title and description. Remember the Common Guidelines and do not use the title of the Jira ticket as-is. The title of the PR is one of the most visible and obvious indicators of a security issue being worked on! It appears on the PR itself, the pull requests index page—both of which attackers are likely to monitor—and eventually ends up in Git history when the PR is squashed and merged. The guidelines also apply to individual commit messages and the name of the branch!

- If you notice you've made a mistake in the code, unit tests, comments, or commit messages and already pushed it to GitHub, fix it as soon as possible by rewriting the Git history and force-pushing the new, sanitized changes.
- If you notice you've made a mistake in the PR title or description, edit it out and alert the Security team: Edits will still be visible in the GitHub UI and if the information revealed is sensitive enough, Security may choose to fully delete the PR in question.

### Guidelines for QA

When QA testing a security fix, keep in mind that any test steps documented on the Jira ticket are most likely sensitive and should not be publicly disclosed. When a test step fails or the instructions are unclear, feel free to request changes on the Pull Request if applicable, but try to keep the details private: use Jira or Mattermost Channels.

If unsure about how to thoroughly QA test a security fix or how to set up the environment required, feel free to leave QA testing to the security team. For automated testing, also see the [Guidelines for Developers](#guidelines-for-developers) section.

### Guidelines for security engineering

As security engineers coordinate an incident with both engineering staff and external contributors, the same Common Guidelines apply. The security engineer currently responsible for coordinating an incident is also in the end responsible for making sure other engineering staff is aware of the guidelines and follows them to the best of their ability.

Security engineers should monitor any public activity around an incident, such as information unintentionally leaking, outside parties commenting on Pull Requests, or the reporter of the issue actively leaking information on social media.

The responsibility of maintaining this document also rests with security engineering: If a specific guideline cannot be reasonably applied in a large number of cases, the guideline should be updated. Similarly, if information appears to be consistently leaking despite following these guidelines, improvements should be planned and documented.
