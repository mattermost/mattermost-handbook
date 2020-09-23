---
description: Helping teams work better together when time is of the essence.
---

# Incident Response

Owner: @ian.tao

Teams choose Mattermost because it provides a flexible and secure environment for collaboration. This is particularly valuable during incidents that require timely resolution, that's why many of our customers today leverage Mattermost as a key part of their response workflow. This document summarizes our observation and vision for how Mattermost can help your team be more proactive and effective.

## What teams do today

For software operators, the most important incidents tend to be related to site reliability, information security, or development and operations. Regardless of the domain, the response protocol tend to have four broad stages in common: preparation, detection, recovery, summary.

### 1. Preparation

By integrating with your favourite monitoring tools such as [Prometheus](https://prometheus.io/) and [Nagios](https://www.nagios.org/), information flows into Mattermost about potential incidents. Incident Managers can then be notified to review and escalate as appropriate based on standard operating procedure.

### 2. Detection

Our [Incident Response plug-in](https://docs.mattermost.com/administration/incident-response-application.html) can be configured to conditionally escalate alerts and automatically start a workflow - typically by first creating a dedicated channel.

![Nagios integration triggering a war room channel](../../../../.gitbook/assets/incident-response-app-intro-image.png)

The workflow plug-in can be customized to streamline your standard operating procedure, for example:

* Identified on-call team members through integration with tools such as [PagerDuty](https://www.pagerduty.com/), [OpsGenie](https://www.atlassian.com/software/opsgenie), or [Solar Lottery](https://github.com/mattermost/mattermost-plugin-solar-lottery) and add them to the incident channel.
* Spin up a Docker instance to initiate investigation infrastructure.
* Start real-time audio/video meeting using Zoom.
* Configure integrations to funnel relevant posts to the incident channel so response actions are centrally logged.
* Perform diagnostic commands on other systems and post results in the channel.

### 3. Recovery

This stage typically consists of several swim lanes with different team members potentially working in parallel. For example:

* Coordinate efforts and collaboration to keep the team on track.
* Investigate cause of issue by querying other systems.
* Communicate status and update with stakeholders such as Leadership, Legal, or Public Relations.

Here are some of the ways that Mattermost is used to help teams respond more effectively:

* Centralize investigation results and actions performed into one channel so they're visible to the whole team.
* Track statistics such as mean-time-to-acknowledgment \(MTTA\) and mean-time-to-resolution \(MTTR\) in a glanceable report.
* Save time jumping between other tools by leveraging slash command to perform actions on other systems and log who did what and when.
* Pin key messages so that they can be easily reviewed as a mini-timeline of the incident at any time.

### 4. Summary

Once the issues have been resolved, the incident channel becomes a complete record of the entire response, without any additional effort to compile, which is essential for post-mortem and Root Cause Analysis \(RCA\). Message within the channel can be searched, filtered, and eventually exported for reporting and analysis that will help the team learn and improve process.

## Our vision for the future

Based on our observation of how teams leverage Mattermost today, we believe there is amazing potential for us to be more intentional in supporting them. We will work towards making Mattermost the best collaboration platform for software operators by investing in these four areas:

* Integration with monitoring, ticketing, and CI/CD tools to enable out-of-the-box experience most of the time while supporting the flexibility for customization.
* Workflow framework to enable inter-plugin communication and automate actions that can be tailored to your operating procedure.
* Configurable slash commands to query data and perform actions on external systems from within Mattermost to keep information in-context.
* Channel data export and cleansing functionality to support analysis and reporting as well as meet compliance requirements.
