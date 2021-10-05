# Channels

Channels is split into feature teams and platform teams.

## Feature Teams

The feature teams are responsible for designing, developing, and maintaining the features of the Channels product. They are full stack and own feature development across the entire tech stack (Web App, Mobile, Desktop, and backend).

These teams are flexible enough to work on whatever is highest impact. Each team does have areas of expertise and features they own but any feature team can work on any portion of the product.

The teams are:

### Ursa (feature team #1)

Areas of expertise:

* Groups
* LDAP
* Permissions
* System Console
* Compliance
* Data Retention
* Mobile sidebar/categories

### Interstellar (feature team #2)

Areas of expertise:

* Apps
* Webhooks
* Slash Commands
* Plugins

### Apollo (feature team #3)

Areas of expertise:

* Posts
* Threads
* File Previews

## Platform Teams

The platform teams are responsible for building and maintaining the systems that the feature teams rely on.

**Why are these teams in the Channels product vertical and not the Platform division?**

Until recently Channels was the only product Mattermost had and was itself the platform. As a result of this a lot of the platform is tightly coupled to the Channels product. The server and web app parts of the platform are especially tightly coupled. The goal is to eventually move these teams, or some version of them, out of the Channels product vertical when that coupling is looser.

The teams are:

### Web Platform

The role of the Web Platform team is to own the infrastructure behind the Web App and Desktop App while supporting other teams that are using that infrastructure.

Within the Web App, that means tooling (e.g. build tools, testing frameworks, style checking), core systems (e.g. Redux, routing), and helping maintain the core features of the app. For the areas owned, the team is also responsible for educating other teams about those areas and helping them coordinate work that might require changes to those things.

The team is also responsible for dictating the coding style and practices used throughout the Web App which can be used as a reference for other JS projects. As recommended practices change, the team will work with the community and other teams to implement those in the Web App whenever possible.

The team is not responsible for experimenting with new technologies or dictating the project structure/tooling used for all other JS projects within Mattermost. Because feature teams are able to move much quicker when they're writing brand new code, they have more opportunities to try out new technologies and practices. When those experiments are successful, the Web platform team will help integrate them back into the Web App and make them available for other Mattermost projects.

### Server Platform

The role of the Server Platform team is to own the backend multi-product architecture and server performance while supporting other teams that rely on the server.
