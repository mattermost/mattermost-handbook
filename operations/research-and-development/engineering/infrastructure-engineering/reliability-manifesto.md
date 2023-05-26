# Reliability Manifesto

The Reliability Manifesto is a collection of rules, guidelines, and best practices that reflect our current thinking on what it takes to build a reliable and cost-effective system following a cloud first approach. This manifesto should keep things short, clear and easy to implement and monitor. This document should be acknowledged by all Mattermost teams that use the Mattermost cloud services and that develop code that will run in the production infrastructure.

To make things simple, we decided to split this document into a number of distinct categories that can be considered individual manifestos and can be seen below. 

- Foundation
- Continuous Improvement 
- Design & Architecture 
- Observability 
- Performance & Cost Efficiency
- Resilience
- Security

## Foundation
The set of rules that should set the foundation for this reliability manifesto.

**F-1** We do not silently bypass the rules in this document, but instead, start a discussion to change the rules when we think something does not fit our situation.

**F-2** This set of rules should reflect measurable targets in the quarter OKRs of the teams that utilize the Infrastructure platform. 

**F-3** We assess the validity of the rules in this document twice a year and we adapt accordingly.

## Continuous Improvement

There is always room for improvement in our knowledge and our systems. The continuous improvement manifesto aims to make us more efficient, resilient and better engineers.

**C-1** We should track all our production incidents. Major and critical incidents are reported and updated using our statuspage. All incidents are tracked via a Infrastructure Incident Response v2.0 playbook run. More details here.

**C-2** Post mortem meetings and documents should follow every major and critical production incident. Runbooks if any should be added in the internal documentation for future reference.

**C-3** No single engineer should fully deploy a new service across all environments. We share knowledge and reduce the team bus factor. 

**C-4** Blameless culture is a key. People make mistakes and systems (do) fail. We need to learn from them and help each other. 

## Design & Architecture

Better design and architectures create more reliable systems and reduce technical debt. This is what the Design & Architecture manifesto is all about. 

**D-1** Infrastructure team should be involved early in the design process for applications that will run in the infrastructure systems. Read about the [Production Readiness Review](/operations/research-and-development/engineering/infrastructure-engineering/production-readiness-review.md)

**D-2** All new services should go through the POC phase and findings should be presented in a team meeting, together with proposal, design architecture and implementation steps. Example reference [here](https://docs.google.com/document/d/1KZlemVB_75Xv4CDao5bcWpKml3fHbpcoAk_gWl8nFSY/edit).

**D-3** We should avoid monolithic designs for custom services when possible. Microservice design should be the aim and services should be open sourced for community usage when they don’t expose private company information.
 
**D-4** All services should be followed by architecture diagrams (we use Lucidchart) when possible and documentation. 

**D-5** Always be mindful that services work in a different way at scale. Configurations that might work in local environments could have a major impact in production systems. For example, a possible abuse of the amount of database connections used. 

**D-6** All services should support the ability to turn off/on on demand without affecting the rest of the infrastructure services.

## Observability

The observability manifesto should cover three main pillars:
- Logs
- Metrics
- Tracing

### Logs

**O-1** Logs should include meaningful messages and stack trace should not be a requirement to understand the log message.

**O-2** Service logs are enriched with metadata & attributes that differentiate the service (e.g service: boards).

**O-3** Logging levels should be consistent across services and false errors should be avoided to enable generation of metrics, patterns and dashboards.

**O-4** Logging format structure should be consistent across services and should be agreed across all teams. String and JSON formats should be used for all logs. 

**O-5** Retention of 30 days for all critical and 7 days of all non-critical production system logs should be met. With exceptions, logs can be kept up to 1 year in S3 utilizing Glacier options.

### Metrics
**O-6** All services should export key metrics under /metrics path and should be enriched with metadata & attributes that differentiate the service (e.g service: playbooks).

**O-7** All the application metrics should be exposed via 8067 port.

**O-8** Application and service software version metrics of all applications should be exposed.

**O-** The application and services should expose availability and latency metrics.

**O-10** Raw metrics should be kept for 7 days and 5m/1h resolution metrics should be kept for 365 days for all production systems. 

### Tracing (Placeholder)
O-11 As we are moving more into microservices, request tracing should be implemented for each microservice to enable distributed request tracing analysis.

## Performance & Cost Efficiency

Improving performance and cutting costs of our systems makes our services more competitive and efficient. This is what the Performance & Cost Efficiency manifesto is all about. 

**P-1** We avoid the solution of throwing money to the problem. If a system constantly needs money to perform, we need to seek for other solutions.

**P-2** We utilize cost optimization at scale. The more customers we add, the better we should utilize our shared infrastructure and cost per customer KPI should be reduced. 

**P-3** We should aim for a 2% increase in our spot machines in each quarter with a maximum of 50% of the total fleet.

**P-4** The cost of non production environments should not exceed 30% of the total Mattermost infrastructure environments cost.  

## Resilience

Resilience ensures that our services are there for our customers even on bad days. This is what this manifesto is about.

**R-1** We should always aim for higher SLOs than the ones promised to our customers. The SRE team would influence other teams on what needs to be improved to meet higher SLAs. 

**R-2** Each service should have a dedicated SLO target, which should always be higher than the external SLO.

**R-3** We run monthly gamedays, injecting chaos to the system. The impact should be measured and post game day actions should be defined. The whole team should be involved.

**R-4** Disaster recovery protocols and playbooks should be defined for all our key components (K8s Clusters, Database Clusters, DNS, etc.)

## Security

Keeping our systems secure, keeps our customers safe and our nights lighter. This is what the Security manifesto is all about. 

**S-1** We follow security team guidelines and we get security team approval on new system deployments.

**S-2** We reduce our attack surface by not exposing to the public internet whatever should not be public. 

**S-3** Secrets should be stored in secret management services (eg. Vault, AWS Secret Manager) and not in Gitlab/Github repos. 

**S-4** Security groups should be applied in all machines and limit access only to ports and sources needed. Both deployment and evaluation should be done in an automated way.

**S-5** IAM Roles should be used when possible, IAM users should be avoided and IAM policies should be granting least privilege.

**S-6** We should always aim to eliminate high severity issues arising from security tooling analysis (e.g Stackrox).
