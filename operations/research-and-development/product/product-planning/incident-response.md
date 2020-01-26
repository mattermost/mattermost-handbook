# Incident Response

Today many Mattermost users run incident response workflows. This document is a work-in-progress summarizing the vision for the incident response workflows and scenarios. 

Owner: @ian.tao   
Discussion channel: XXX

The four main components are: 

* Integration with toolchains
* Workflow automation 
* Data cleansing and export from tools, followed by analysis 
* Distributed commandline to query data to various tools

These support core incident response workflows: 

* **Monitoring** information flows into Mattermost about potential incident
  * Incident manager reviews reports and escalates as appropriate based on standard operating procedure
* **Escalate** by creating Mattermost channel and spinning up scanning infrastructure, starting real time audio/video call with stakeholders
* **Assemble** - Bring in PR, legal and marketing as needed into channel
* **Investigate** - Identify the symptoms, bring in the right people to find out who to bring in. Run queries on different systems in different swim lanes, identify symptoms that trigger the incident
* **Communicate** - Someone is keeping everyone up to date regularly externally and to stakeholders 
* **Resolve** undo the damage. Address the symptoms and revert the damage, may or may not fix the underlying issue
* **Post-mortem** - Wrap up the issue with reports and logs, aggregated and archive for regulatory reporting, learning and process improvement





