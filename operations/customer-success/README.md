# Customer Success

## Purpose

Deliver the ideal customer journey experience to all customers at scale.

### Customer Success Journey Principles

- See first from the customer’s perspective (golden rule).
- Strive to be a partner, looking to meet both the current and future needs of the customer.
- Be solution-oriented.
- Focus on customer outcomes and creating value.
- Make Mattermost better by sharing learnings and feedback.

### Customer Segmentation

- **Goal:** Deliver a great customer journey for all customers.
- **Reality:** Not all customers are created equally.
- **Plan:** Tailor the journey based on existing investment AND the opportunity to grow.

See [Post Sales Customer Journey Playbook](https://docs.google.com/document/d/1WB9Qr4ZRjZixprLKiX6tlbb4784qw5luV3eqzk_9hyw/edit#heading=h.hy6fak6l0x08) for customer segmentation details.

### Customer Feedback

#### Overview

Customer Feedback calls are conducted by all customer facing employees at Mattermost. The objective of a Customer Feedback call is to gather the following information from a customer:

- Feature requests
- Integration usage
- Use cases
- Understand which teams use Mattermost
- Product design review feedback
- Challenges being solved

These calls are logged in Salesforce for tracking and reporting purposes.

#### Logging a Customer Feedback in Salesforce

Below are the links to the training videos for Enterprise and non-Enterprise customers.

* [1) Non-Enterprise feedback calls](https://drive.google.com/drive/u/0/folders/1k9M0wfolXf34XQndtqzLYcCBVkGsBob2)
* [2) Enterprise feedback calls](https://drive.google.com/drive/u/0/folders/1k9M0wfolXf34XQndtqzLYcCBVkGsBob2)

Use the following steps to log calls for licensed and non-licensed customers in Salesforce.

##### Enterprise Customers

1. Log into Salesforce.
2. Type in account name in the search bar located in the middle of the screen.
3. Select the account.
4. Hover over **Activity history**.
5. Select **Log a call** in the top-right corner of the screen.
6. Fill out the following sections:
   - **Subject:** Brief description of the call (e.g. "Customer Reply Thread Design Review").
   - **Name:** Customer contact(s) that attended the call.
   - **Type:** Was this a call or in-person meeting.
   - **Related To:** Account name.
   - **Sub-Type:** Choose **Customer Feedback**.
   - **Due Date:** Auto-populated to today's date.
   - **Comments:** Details of the call or meeting.
 7. Select **Save**.
 
 ##### Non-Enterprise Customers - Account Exists in Salesforce
 
1. Search for an account in Salesforce and select the account from the drop-down menu.
2. If the Account exists, click on the account.
3. Hover over contacts to check that customer contact from the call exists. If the contact does not exist, select **New** to create a contact.
4. Fill out the following fields and select **Save**.
  - **First Name**
  - **Last Name**
  - **Email** 
  - **Check “Email Opt-Out”**
  - **Check “Marketing Suspend”**
5. Hover over activity history and select **Log a Call** in the top right-hand side of the screen.
6. Fill in the highlighted sections. Select **Customer Feedback** as sub-type.
7. Select **Save**.

##### Non-Enterprise Customers - Account Does Not Exist in Salesforce

1. Search for Account “Hold Public” in the search bar and select the account from the drop-down menu.
2. Hover over contacts and select **New** to create a contact.
3. Fill out the following fields and select **Save**.
  - **First Name**
  - **Last Name**
  - **Email** 
  - **Check “Email Opt-Out”**
  - **Check “Marketing Suspend”**
4. Hover over activity history. Select **Log a Call** in the top right-hand side of the screen.
5. Fill in the highlighted sections. Select **Customer Feedback** as sub-type.
6. Select **Save**.

 _Note: Salesforce Customer Feedback calls are pushed through Zapier into productboard and the Internal Customer Feedback Channel in Mattermost._

### Customer Reference

#### Overview

Customer Reference is a customer story on how Mattermost made a positive impact on a customer's day-to-day processes. Customer Reference can be shared in the following formats:

- Case study
- Guest blog post
- Press release
- Video testimony
- LinkedIn post
- Webinar/podcast
- Quote

#### Logging a Customer Reference in Salesforce

Mattermost uses Salesforce to log Customer References. [Here is a quick video](https://drive.google.com/drive/u/0/folders/1k9M0wfolXf34XQndtqzLYcCBVkGsBob2) on how to log a Customer Reference in Salesforce.

Below are detailed steps on how to log a Customer Reference in Salesforce.

1. Search for the account.
2. Hover over **Customer Reference** under **Related Lists** and select **New**.
3. Enter information into the form.
   - **Account:** Automatically populated.
   - **Contact:** Main contact for the reference.
   - **Reference type:** How will the reference be shared? (e.g. Case Study, LinkedIn post, Customer Logo).
   - **Reference Category:** What is the theme for this reference? (e.g. DevOps, Integration, Just Chat, ChatOps).
   - **Cool Use Case:** Brief description of how Mattermost impacted the customer.
   - **Audience:** Who is this reference for? (e.g. DevOps, ChatOps, Everyone).
   - **Internal/External:** Can this reference be discussed outside of the walls of Mattermost?
   - **Published Reference URL:** Link for published case study, LinkedIn story, blog, etc.
   - **Status:** Is the reference in progress, identified, completed?
   - **Target Completion Date:** If the reference is not completed, what is the expected date of completion?
   - **Start Date:** From what date is the reference usable.
   - **End Date:** Populate if the customer will no longer allow us to use their case study, logo, LinkedIn post, etc. Please add to the notes section on why the customer has an end date.
   - **Owner:** Automatically populated and assigned to the person who creates the reference. It can be changed by using the **Change Owner** button.
   - **Approved by Customer Legal:** Customer contact has approval from their legal team.
   - **Approved by Mattermost Legal:** Owner of the reference has reached out to Mattermost legal to ensure there are no clauses in the MSA that Mattermost cannot use their logo or publish case studies.
   - **Notes:** Field to add any additional details.
4. Select **Save**.

### Customer Risk

Risk is the chance or probability that a customer will not renew their existing Enterprise license. The Customer Success team categorizes risk into two buckets:

* **At-Risk:** Customer has actively told Mattermost there is a high probability of non-renewal.
* **Early Warning:** The customer has not told Mattermost there is a probability of non-renewal. Early Warning customers have voiced frustrations or are non-responsive.

The Customer Risk object in Salesforce was created to track At-Risk and Early Warning customers. Managing customer risk in Salesforce allows for better visibility among departments at Mattermost.

To log Customer Risk in Salesforce you can watch the [Creating Customer Risk video](https://drive.google.com/drive/u/0/folders/1_nbZhAirM2-4q4oFdygSgmS1H_pAn5qm) or follow the step-by-step instructions below.

#### Instructions for Logging in Salesforce

1. Log into your Salesforce account.
2. Type the Account Name in the search bar.
3. Hover over **Customer Risk** in the quick links section at the top of the account page and select **New**.
4. The quick form appears in a small pop-out window. You don't need to fill out all fields. Any fields that don't have a red asterisk will automatically be populated upon saving. Below are the fields you need to fill out:
   - **Customer Risk Name:** Put the name of the customer account and type of risk. For example *XYZ Company At-Risk* or *XYZ Company Early Warning*.
   - **Key Contact:** Who is the main contact at the account.
   - **Status:** Choose if the customer is **At-Risk** or **Early Warning**. Note: **Churned** and **Renewed** fields will be used later based on the renewal outcome.
   - **# of Seats At-Risk:** How many seats could be potentially non-renewed. Seat number could be all of the seats available for renewal or a portion of the seats available for renewal.
   - **Risk Amount:** What is the amount of ARR that could be potentially non-renewed. Risk amount could be all ARR available for renewal or a portion of the ARR available for renewal.
   - **Engagement:** Current interaction between the customer and Mattermost. For example: Is there a call scheduled, is the customer unresponsive, have you reached out to the customer, etc.
   - **Competitor:** Who is the competitor the customer is evaluating.
   - **Reason:** What is the reason the customer is considering non-renewal.
   - **Summary:** Description of why the customer is being flagged as an At-Risk or Early Warning.
   - **Next Step:** What is the next action item with the customer.
