# Submitting a Purchase Order

Log into Accrualify and go to the Purchase Module on the left hand side of the screen. Select the orange **Request PO** button.

![](../../.gitbook/assets/How-to-submit-a-PO-1.png)

A **Request a New Purchase Order** form will appear prompting you to fill out the primary information. The screenshot below highlights all the fields needed to be populated to successfully complete a submission.

![](../../.gitbook/assets/How-to-submit-a-PO-2.png)

Mapping key to each field and purpose:

1. **Vendor/Supplier**: the field is not a drop down list but a search bar. The vendor name must match exactly for the vendor to appear available. Refer to Finding a Vendor on the steps to successfully locate a vendor.
      * **Add Vendor**: Only click this button if you have taken all previous steps to determine if your vendor exists as an active vendor in our repository. Refer to section Requesting a Vendor.
2. **Payment terms**: Mattermost standard payment terms is Net 30. If your vendor accelerated payment terms like Net 15, Net 7, or due on receipt,  this will require additional approval from Finance. You should reach out to procurement@mattermost.com or Finance Team Channel
3. **Amount**: This field is intentionally grayed out as it will pull from the section PO Expenses further down screen window.
4. **Start Date/End Date**: these are the dates for when the services will start and complete. For goods being delivered on a specific date, the start and end date should be the same.
5. **Date/Receive By Date**: Date will automatically populate based on today’s date. This may be changed, but is not recommended as this will account at the request date. The **Receive by** field is the date you would ideally like to PO to be approved. Note that we still maintain standard SLAs. If the request is urgent, we will do our best to accommodate but make no guarantees. If you are working with a new vendor on negotiations, it is advisable to bring the Procurement Team as early as possible to avoid any potential delays or missed dates
6. **Location**: this is the country that the vendor is physically providing services from
7. **Currency Code**: represents the currency preferred by the vendor and what the vendor will invoice Mattermost. This should be defined in the contract 
8. **Department**: the department field is a drop down list that you can choose from. If you are completing a PO Request Form for yourself, it is generally assumed the spend will map to your department. If you are unsure what department you belong to, you can reference your department in Bamboo as seen in the screenshot below. If you are submitting a PO on behalf of someone else, it is advised to use their department in Bamboo. If you believe spend should be allocated to more than one department, make note of this in the Description/Notes section of the form.

![](../../.gitbook/assets/How-to-submit-a-PO-3.png)

9. **Description/Notes**: It’s important that we collect as much information as possible of the purpose and intent of the goods/services that the vendor is providing to Mattermost. The more information the better. However, at a minimum we require the following:
      * *Type of Service*: Software, consulting spend, contractor, etc.
      * *Purpose*: the intention for requesting spend: Example: Product software for UX design or contractor spend for Salesforce administration.
      * *Type of Spend*: is this a fixed amount or variable. Be explicit as to what you are purchasing. Example: monthly retainer for the same amount over 4 months would be considered fixed versus billing on a number of registered users would be variable.
      * *Invoice Billing Frequency*: monthly, quarterly, annually, etc.
      
## Adding Attachments

It would be uncommon not to attach some document or form to accompany the purchase order request. To upload a document, find the blue **Add Attachments** button at the bottom on the **Request a New Purchase Order** form. Attach all associated legal documents needed for review. Some examples of legal documents may include:

1. Vendor Master Service Agreement
2. Vendor Online Terms and Conditions
3. Vendor Supplier Form
4. Vendor Purchase Order Form
5. Vendor Service Order Form
6. Sponsorship Agreement
7. Corporate Agreement
8. Addendum or Amendment to a Contract

![](../../.gitbook/assets/How-to-submit-a-PO-4.png)

## Finding a Vendor

If you are unsure if your vendor is on file or unsure of the legal name of the vendor, you can refer to the Vendor Module to quickly look up a vendor by typing the name of the vendor in the column titled **Vendor** as seen in the screenshot below.

![](../../.gitbook/assets/How-to-submit-a-PO-5.png)

Vendors are named in our system based on the legal name provided on the vendor's W-9. However, the vendor may be Doing Business As “DBA” under an alternative alias.

**Example**: Netsuite is owned by Oracle, Inc. We are billed by Oracle but the software known at Mattermost is Netsuite.

If you unable to locate the vendor and believe that your vendor is active, reach out to the accounting team at AP@mattermost.com or the [Purchases Channel](https://community.mattermost.com/private-core/channels/purchases).

## Requesting a Vendor

If you are unable to find the vendor in question through the following 3 channels, then proceed to clicking the blue **Add Vendor** button and complete the basic vendor information.

* Vendor Module
* Vendor/Supplier search field on the Request a New Purchase Order form
* Accounting Team is unable to locate the vendor or DBA name

If your vendor is a US vendor or supplier and you have a copy of their W-9, go ahead and upload the signed documents by clicking the blue **Upload W9** button Form as seen below. Do not check the box Send Welcome Email if this appears on your screen. The Finance Team will send the new vendor a welcome email once the PO has gone through the proper approval process.

![](../../.gitbook/assets/How-to-submit-a-PO-6.png)

When completing the New Vendor Details, be mindful of the following:

* If the PO request is in a currency other than USD, you can use the currency in the “Currency Code” drop down menu. After you submit the PO, the amount will convert to USD.

## How to complete PO Expenses section

At the bottom half of the page under **Request a New Purchase Order** is a section titled **PO Expenses**. This should be completed as well, but don’t worry if you get this wrong. The Finance Team will be reviewing these sections thoroughly and modifying the PO forms on the back-end. That said, it is still beneficial to complete the following sections:

1. **Category:** represents the type of spend that you will incur. A full list of expenses, definitions, and examples can be found Expense Category Definitions
2. **Amount:** represents the total requested dollar amount. The request should be based on the currency which the vendor will invoice Mattermost. The Currency Code selected above will drive the amount
3. **Department:** should mirror the department selected in the section above 
4. **Location:** should mirror the location selected in the section above 
5. **Business Unit:** classifications used to categorize spend. A full list of expenses, definitions, and examples can be found in Business Unit Definitions
6. **Start and end dates:** should mirror the start and end dates in the section above
7. **Memo:** please copy and paste the test from the Description section above

You do not need to choose an Account and Amortization Template.

![](../../.gitbook/assets/How-to-submit-a-PO-7.png)

The Procurement team will reach out to you if there is follow up needed for additional information.

Once the form is complete, please attach the appropriate legal documents. Then click on the “Submit” button. The approval workflow process will begin. You can always check the status of your request in the Purchase Order Module or feel free to reach out to Procurement@mattermost.com for further details on your request.

## Business Unit Definitions

Please note that these Business Units are similar to the Classifications found in Expensify.

| Business Unit  | Definition  | 
| :------------ |:---------------|
| Advisor | Expense related to Advisory services for MM |
| Bounty Projects | Fees for Services Related to Bounty Projects|
| Business Operations | Expenses to support office and business operations; stamps, postage, supplies, snacks, etc.|
| Conferences & Trade Shows | Expenses incurred to get to, attend, or stay at Conference/Trade Show|
| Consultants | Expense related for payment to Non-ROW Consultants & Contractors|
| Customer Facing | Expenses incurred when meeting, spending time, or entertaining a current or potential customer|
| Marketing Events | Expenses incurred to attend marketing events, seminars, etc.|
| Mattercon | Expenses for Mattercon events only |
| Community Member | Community Member expenses for Mattercon events only |
| Onboarding | Expenses for new hire home and office equipment; travel for onboarding training, etc. |
| Recurring Subscriptions | Expenses that are recurring in nature and support business operations; mobile subscriptions, software licenses, etc. |
| Simulation Projects | Expenses for candidate simulation projects sponsored by Mattermost |
| Staff | Expense related for payment of Monthly Salary & Periodic Bonuses to ROW Staff |
| Support | Revenue and CoS for customer support products |
| systems | Expenses, greater than $500, incurred for work performed on systems |
| Team Celebration | Expenses for department head approved celebration with staff members |
| Team Events, Meetups & Offsites | Expenses incurred for Team Events, Meetups, or Offsites, which include all known travel costs |
| Training | Expenses incurred for work-related online courses and professional development certifications |

## Expense Category Definitions

| Expense Category  | Definition | Examples | GL Acct # |
| :------------ |:---------------| :-----| :-----|
| Advertising | Online and print advertising       |  Google ads, Facebook ads, Twitter ads |   66060 |
| Advisory or Consulting | Advisory (individuals or firms) or consulting (firms) services provided to Mattermost              |   TrustArc, BPE Global |  12040 |
| Audit and Tax Fees | Audit and tax services provided to Mattermost        |    PwC, EY, Deloitte |  62040 |
| Candidate Attainment Projects | Simulations and other related projects for prospective candidates       |    Simulation projects |  62030 |
| Company Events | Services provided to Mattermost for company sponsored events        |    Mattercon|  60530 |
| Company Swag | Mattermost branded swag NOT for marketing campaigns        |    Printfection, Kotis |  60540 |
| Conference and Seminars | Conferences and seminars (NOT Marketing related)        |     |  63070 |
| Contractor or Consultant | Individuals who will provide contractor or consulting services to Mattermost at an hourly or fixed fee for a specified period of time | Bounty Projects, contractors with SOWs |  62030 |
| Left column 3 | Individuals who will provide contractor or consulting services to Mattermost at an hourly or fixed fee for a specified period of time        |    Bounty Projects, contractors with SOWs |  62030 |
| Dues & Subscriptions | Dues and Subscription fees for professional, technical or trade publications        |    Financial Times, Wall Street Journal |  64010 |
| Hosting COS | Hosting web services (e.g. AWS) - allocation for Cost of Sales       |    AWS|  50020 |
| Hosting Expense | Hosting web services (e.g. AWS)      |    AWS|  64080 |
| HR Fees | Human resource services (individuals and firms) provided to Mattermost        |    TriNet, Vistra |  62070 |
| Job Advertising | Fees paid to advertise open positions to potential candidates (e.g. job boards)      |   StackOver Flow, Cyber Coders, Indeed, LinkedIn |  61050 |
| Legal Fees | Legal and compliance services (individuals and firms) provided to Mattermost        |    Law firms |  62050 |
| Marketing Promotional Materials | Promotional marketing materials        |     |  66040 |
| Marketing Swag | Mattermost branded swag for marketing campaigns only       |    Zazzle, Printfection |  66070 |
| Prepaid Insurance | All types of insurance policies, varying in period of time and premium amounts       |    The Hartford |  12010 |
| Prepaid Marketing & Advertising | Marketing and advertising services (e.g. public relations, search engine optimization and web & content development etc.) provided to Mattermost       |    |  12020 |
| Prepaid Software/SaaS Licenses | Software license fees paid in advance (a year or more)        |    NetSuite, Celigo, Snowflake, SalesForce |  12030 |
| Recruiting Fees | Fees paid to third party recruiters for candidate placement        |     |  61010 |
| Recruiting Services | Fees paid to third party service firms for recruitment efforts        |    |  61020 |
| Software Expense | Software licenses and subscription (monthly)        |    Figma, Dribbble |  64040 |
