# Self Service

![](../../.gitbook/assets/self-service.png)

### Self Service is enabled through the combined capabilities of three major components

* Customer Portal
* blapi \(Business Logic API\)
* License Generator

**Find the Self Service Roadmap in [ProductBoard](	
https://mattermost.productboard.com/roadmap/1657337-customer-portal-roadmap)**

**Ask questions [here](https://community.mattermost.com/private-core/channels/customer-portal)**

## Customer Portal

Customer Portal will provide a portal for customers to self-serve product purchases through Mattermost, reducing time to purchase and manual fulfillment time.

* PM: Eric Sadur
* Technical Lead: Joram Wilander
* Relevant Links:
  * [GitHub Repo](https://github.com/mattermost/customer-web-server)


## blapi \(Business Logic API\)

blapi is responsible for surfacing billings, licensing, and customer data to the Customer Portal, generating required records in SFDC to enable reporting and sales processes, converting SFDC records to information required to run Customer Portal, and lastly charging credit cards in Stripe.

* PM: Rachel Bradley-Haas
* Technical Lead: Alex Dovenmuehle
* Relevant Links:
  * [GitHub Repo](https://github.com/mattermost/blapi)
  * [OpenAPI Schema](https://github.com/mattermost/blapi/blob/master/openapi.json)

## License Generator

The Mattermost License Generator \(MLG\) is a microservice responsible to generate the license that is used in the Mattermost application.

* Technical Lead: Carlos Panato
* Relevant Links:
  * [GitHub Repo](https://github.com/mattermost/license-generator)
  * [License Generator Documentation](https://docs.google.com/document/d/1GsAAQR9Cpmtj46PhSJNuHXpxRUzk4dWUyvvd6B4UT9M/edit?usp=sharing)

