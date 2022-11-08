# How to make Packaging decisions: 

The following chart can be used when making decisions about what offering a feature will be available in. 



||Free|Professional|Enterprise
|---|---|---|---|
|Use Case |Technical outcomes<br> <br> DevOps Productivity <br> <br> Single or smaller teams | Technical + Business outcomes <br> <br> Sophisticated DevOps workflows <br> <br> Multiple teams (up to 25 teams ~ 250 people) requiring more advanced administration features | Business outcomes (ROI)<br> <br> Enterprise workflows <br> <br> Scale & Compliance <br> <br> More than 25 teams|
|Decision Maker Persona|IC, Team lead / manager | Director(s)| VP/CXO (smaller companies)| VP / CXO / LOB |



**Example 1:** 
Calls is working on a feature to offers self-hosted customers an option to deploy a standalone server that separates audio and screenshare processing from their main Mattermost server.

Standalone Calls server with Kubernetes support <> Enterprise
Why? *A standalone server enables an organization to support more scalable and secure deployments of Mattermost by reducing the impact the calls feature has on an already active Mattermost server with Channels, Playbooks, and Boards.*  

**Example 2:**
Channels is working on a feature, high priority messages. Here is how you can apply these principles to this feature that offers different use cases:

 //image

Post importance labeling <> Free
Why? *This feature helps technical users bring attention to a message they want others to notice in a channel. This ensures others have the information they need to move work forward.*  

Example use case: I am finalizing my development today for the critical bug, be on the lookout for code review requests. 

Acknowledgment <> Professional
Why? *This feature helps ensure that a message is specifically read by another person or group, so that work is not missed and an outcome is not missed. This is especially helpful when a responsibility is being delegated between different teams, who aren’t used to actively monitoring each other’s work.* 

Example use case: “@release-manager There is a critical bug found in release testing, my recommendation is holding this release until it is fixed.”

Persistent notifications <> Professional
Why? *When a message is especially critical and a business outcome is dependent on a person or a group responding (such as a major outage of a software system).*

Example use case: “@sre-team: We have customers in our eastern region complaining of not being able to access our site at all right now, who’s available to investigate?” 

