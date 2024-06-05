# Severity Levels for Bug Tickets

## Criteria for bugs

* “Scale” of impact
  * S1 - `Data loss or crash` - Prevents app use (e.g. Mattermost crashes when posting a message). These are the only bugs that can be committed after the T-10 Code Freeze deadline.
  * S2 - `Functionality loss or glaring UI regressions` - Most users’ functionality affected (e.g. cannot favorite a channel) or includes functional and UI regressions that affect functionality. In addition to S1 bugs, these are the only bugs that can be committed after Code Complete deadline until T-10 Code Freeze.
  * S3 - `Minor issues or cosmetic UI regressions` - Half or less than half of users’ functionality affected. Cosmetic UI issues or regression (e.g. cannot create custom emoji if System Admin).

## Assigning severity levels

Severity levels on bug tickets should be filled in by the ticket reporter by using the **Severity** field.

Bug tickets are sometimes assessed on a case-by-case basis and further considerations may be applied, such as whether the bug is a recent regression or not, how risky the bug fix is, or whether it’s more effective to revert code that initially caused the bug.

## Frequently Asked Questions

**Why are we doing this?**

* This will help with prioritizing release bug fixes, and composing release metrics. Severity guidelines are important so that we can ensure high quality releases for customers.

**Will customer/Enterprise bugs be prioritized any differently?**

* This doesn't change existing processes and customer bugs will continue to be assessed on a case-by-case basis \(e.g. how severe and urgent is the issue for the customer\). For example, a fix for an issue where [Mattermost server crashed when running a compliance export](https://mattermost.atlassian.net/browse/MM-23157) was fixed for v5.21.0 at T-3 because it was an urgent, high severity customer bug.

