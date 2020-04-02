# Self-Service


![](https://github.com/mattermost/mattermost-handbook/blob/rbradleyhaas/.gitbook/assets/self-service.png)


#### Self Service will be enabled throught the combined capabilities of three ongoing projects
* Customer Web Portal
* blapi (Business Logic API)
* License Generator


## Customer Web Portal
Customer Web Portal will provide a portal for customers to self-serve product purchases through Mattermost, reducing time to purchase and manual fulfillment time. 
* [Internal Customer Web Server/Portal Spec](https://docs.google.com/document/d/1pa-pdY3bt-bUoENohbvf-LPV5c5GnFfsLkq8pQE2s00/edit?usp=sharing)
* [Jira Epic](https://mattermost.atlassian.net/browse/MM-22058)
* [GitHub Repo](https://github.com/mattermost/customer-web-server)


## blapi (Business Logic API)
blapi is responsible for surfacing billings, licensing, and customer data to the Customer Web Portal, generating required records in SFDC to enable reporting and sales processes, converting SFDC records to information required to run Customer Web Portal, and lastly charging credit cards in Stripe.
* [blapi Documentation](https://docs.google.com/document/d/1Qj_NyQIVYOmOraNkSWUKpM_Cz9Oq9K1HKDz689M4gkA/edit?usp=sharing)
* [OpenAPI Schema](https://github.com/mattermost/blapi/blob/master/openapi.json)


## License Generator
The Mattermost License Generator (MLG) is a microservice responsible to generate the license that is used in the Mattermost application.
* [License Generator Documentation](https://docs.google.com/document/d/1GsAAQR9Cpmtj46PhSJNuHXpxRUzk4dWUyvvd6B4UT9M/edit?usp=sharing)


## Current Phases Being Scope
* **Phase 1:** Purchases Under $5k
* **Phase 2:** Renewals and Upgrades Under $5k
* **Phase 3:** Mattermost Private Cloud Beta Trial
* **Phase 4:** Co-Termed Expansion / True-Up Automation
* **Phase 5:** Advanced Organization & Account Management
