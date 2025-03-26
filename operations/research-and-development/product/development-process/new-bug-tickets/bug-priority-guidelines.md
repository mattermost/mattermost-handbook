# Priority Levels for Tickets

| **Priority** | **Definition**                                                                           | **Example Issues**                                                                                                        | **Target Resolution** |                                                   **Release Guidelines**                                                   |
|--------------|------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|-----------------------|:--------------------------------------------------------------------------------------------------------------------------:|
| **High**     | **A customer-reported issue or blocker that prevents or severely delays a user’s goal.** | App crash, data loss, broken website forms, broken authentication flow                                                    | Fixed within 30 days  | Fix can be committed after T-10 Code Freeze                                                                                |
| **Medium**   | **A frustrating friction point or an issue so “cringey” it erodes trust.**               | Documentation gaps, misleading error text or guidance, complex UX, inconsistent user interactions, functional regressions | Fixed within 60 days  | Fix can only be committed before T-10 Code Freeze                                                                          |
| **Low**      | **An inconsistency that affects polish.**                                                | UI misalignment, unclear labels, minor documentation errors, cosmetic regressions                                         | Fixed within 90 days  | Fix should be committed before T-19 Code Complete, if submitted after Code Complete it may get bumped to the next release. |


## Assigning priority levels

Priority levels on Jira tickets should be filled in by the ticket reporter using the **Priority** field. The triage team will review and update priority levels based on the guidelines above. 

Bug tickets are sometimes assessed on a case-by-case basis and further considerations may be applied, such as whether the bug is a recent regression or not, how risky the bug fix is, or whether it’s more effective to revert code that initially caused the bug.

## Frequently Asked Questions

**Why are we doing this?**

* We want to consistently deliver high quality products and interactions with our customers. Priority guidelines enable us to prioritize and address quality issues that can erode trust in our brand.
