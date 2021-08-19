# Overview

This document will provide an overview of Mattermost’s A/B Testing methodology. It consists of a sequence of steps and considerations to design valid A/B tests.

## A/B Testing Methodology
### Defining the Goal/Objective
Before you can determine the success criteria \(i.e. the metric that measures success\), you must clearly articulate what the goal/objective of your AB test is. This goal/objective is a statement about the behavior you're trying to influence, the direction of that influence, and the method for achieving that influence. 

An example of a goal/objective could be:
1. Objective: Increase early user retention and engagement.
  * Method: Alter the location and design of the invite member feature.
2. Objective: Increase Cloud free-to-paid conversions.
  * Method: Alter design of the purchasing process within the Billing & Subscription section of the Admin Console.
3. Objective: Increase conversions of Mattermost Cloud Trial Sign Ups
  * Method: Alter paid ad messaging, visuals, and/or targeting.

All of the above goals/objectives have a clear metric that can be measured to compare the performance of various tests and control groups. It is important when conceptualizing an AB test to define a goal/objective that produces a measurable outcome.

### Success Criteria
First you must decide what the success criteria of your A/B test will be. The following questions must be answered in order to formulate a proper A/B testing hypothesis:

1. What is the metric or measure you are trying to influence? \(i.e. What action or outcome are you trying to influence?\)
  * This must be a concise definition that prevents the metric from changing over time.
  * A/B tests tend to work best when working with proportions i.e. the percentage of users to take an action similar to conversion rates.
2. Which direction are you trying to influence the measure \(increase, decrease or no directional preference\)?
3. Can the measure be compared to historical benchmarks?
  * Is it a static measure \(one that will not change as more time passes\)?
  * Historical benchmarks simplify sample size requirement calculations and provide us with a better understanding of the time required to run a test \(i.e. the amount of time required to collect enough data/reach a large enough sample\).
4. Once this has been established, you will need to establish the MDE \(Minimum Detectable Effect Size\). You can learn more about the [MDE statistic in this section](https://handbook.mattermost.com/operations/research-and-development/product/growth/ab-testing#minimum-detectable-effect-size-mde).

The success criteria of an A/B test is based on one to two clearly defined measures, and how an intervention hopes to influence them i.e. increase, decrease, or change \(regardless of direction\). Clearly defined measures ensure the ability to quantify the impact of interventions, thereby allowing you to measure the success or failure of a test.

Examples of valid success criteria metrics/measures:
1. First 14-Day Invite Member Conversion Rate: Proportion of total users to invite new members w/in the first 14 days of first activity
    * I.e. the percentage of total users that trigger an invite member event w/in 14 days of the user’s first active timestamp.
2. Cloud Workspace Creation Conversion Rate: Proportion of unique visitors to the Cloud Trial Signup Page that successfully create a cloud workspace

### Formulating Hypotheses
Once you’ve defined the target measure and established the success criteria, you must determine the [null and alternative hypotheses](https://www.youtube.com/watch?v=_Qlxt0HmuOo) of the test. The null hypothesis is always that the intervention will have no effect on the target measure i.e. Test Outcome = Control Outcome. The alternative hypothesis determines the type of change we’re testing for. If the alternative hypothesis is that the intervention will affect the measure, regardless of direction (Test Outcome ≠ Control Outcome), then the test is 2-sided. If the alternative hypothesis is that the intervention will increase \(or decrease\) our target measure \(Test Outcome > | < Control Outcome\) then this is a 1-sided test.

Example of valid Null & Alternative Hypothesis:
* H𝞱 \(Null Hypothesis\): Adding an invite members icon to the banner will have no effect on the First 14-Day Invite Member Conversion Rate. 
  * 𝞱 = 𝞱0
* Ha \(One-Sided Alternative Hypothesis\): Adding an invite members icon to the banner will increase the First 14-Day Invite Member Conversion Rate. 
  * 𝞱 > 𝞱0
* Ha \(Two-Sided Alternative Hypothesis\): Adding an invite members icon to the banner will change \(either direction\) the First 14-Day Invite Member Conversion Rate. 
  * 𝞱 ≠ 𝞱0


### Minimum Detectable Effect Size \(MDE\)
The MDE is essentially the minimum relative change between test and control means to justify the changes. A smaller MDE requires a larger sample size, i.e. ability to confidently claim a small change to the baseline in the test group is statistically significant. 

#### Example 
The Product Team wants to increase the proportion of users that invite members within the first 14 days on the platform. They’re evaluating two potential UI changes \(interventions\) to affect this change: 
1. Test 1: Placing an icon at the top of the left-hand sidebar channel switcher.
2. Test 2: Placing a banner button at the bottom of the left-hand sidebar channel switcher. 
3. Control: Hold the current UI constant.

The Product Team is targeting at least a 20% relative increase in the proportion of users that invite members within the first 14 days on the platform. This desired relative change in the proportion of users to “convert” will help govern our calculations for the minimum required sample size, and transitively the amount of time the A/B test will have to run in order to collect the minimum required sample size for each group \(test 1, test 2, and the control group\).

### Sample Size
The next step in formulating an A/B test involves determining the minimum required sample size to produce statistically significant results i.e. adequate confidence level and statistical power.

This step is key. It does not need to be done in advance, although it will help you better understand how long the test will need to be run in order to achieve the desired statistical power \(Default = .8\) and confidence level \(Default = .95\). 

The statistical power \(β\), the confidence level \(1-𝜶\), the minimum detectable effect size \(𝝈\), the desired test outcome, as well as the historical measure benchmark \(as a buffer for the control outcome\) are all required to calculate the minimum required sample size. As the test progresses, the calculation for minimum required sample size will change as you’re able to substitute hypothesized outcomes with actual results. The greater the change between groups, the smaller the sample size needed.

These variables and assumptions are listed below, as well as the formula for calculating the sample size for varying types of tests \(1-tailed vs. 2-tailed\).
#### Variables & Assumptions
n = Sample Size
* This represents the sample size of each group. Ideally, the samples will be the same size for each test group and the control.
* The sample size must be sufficiently large in order for the A/B test to have adequate statistical power \(the typical statistical power for A/B tests is .8, which is 1 - β\)

𝜶 = Alpha: Uncertainty Level \(Probability of Committing Type I Error\)
* Default = .05
  * Meaning 1/20 chance there is an effect, but you conclude there is no effect

𝜷 = Beta: \(Probability of Committing Type II Error\)
* 1 - β = Statistical Power

𝞺1 = Proportion of group 1 to convert

𝞺2 = Proportion of group 2 to convert

𝝈 = |𝞺1 - 𝞺2|
* Absolute difference between proportion of group 1 and group 2

Z = Z Score
* Z Score dependent on the specified 𝜶 \(alpha\) & 𝜷 \(beta\) statistics

One-sided Test Sample Size Formula: 
* n = \( \(Z1-𝜶 * √ 𝞺1*\(1- 𝞺1\) \) + \(Z1-𝜷 * √ 𝞺2*\(1- 𝞺2\) \) \) / 𝝈 )^2 

Two-sided Sample Size Formula: 
* n = \( \(Z1-𝜶/2 * √ 𝞺1*\(1- 𝞺1\) \) + \(Z1-𝜷 * √ 𝞺2*\(1- 𝞺2\) \) \) / 𝝈 \)^2

![](../../../.gitbook/assets/z-score-table.png

There are online AB test sample size calculators that allow you to determine the minimum required sample size per test variation. These tests allow you to quickly check the required sample size to achieve an adequate level of statistical power and confidence. [This AB Test Sample Size Calculator by AB Testguide](https://abtestguide.com/abtestsize/) provides the option to switch between one and two-sided tests, as well as specify industry standard powers and confidence levels. The duration of the test depends on the volume of users and instances being created over time. The fewer being created the longer the test will take. Given Mattermost's current Cloud sign up frequency it would take at least 12-16 weeks for a single test on new end users to reach a industry-accepted level of statistical power and confidence. Which requires patience our fast-paced culture does not often permit... All the more reason to increase the breadth and depth of our marketing and business development initiatives.

### Design & Implementation
When designing an A/B test, it’s key to:
1. Simplify the test changes as much as possible.
  * This ensures there are minimal confounding factors that could affect the outcome of a test. 
    * I.e. do not make multiple changes in a single test group or we will not be able to attribute a specific change as the factor affecting the test outcome. 
    * For instance, don’t add a new icon to the UI, while simultaneously adding emphasis to that icon without testing for just the icon placement \(w/ no emphasis\) in another test group.
2. Minimize the number of test variations
  * Running too many variations of tests at a time can also cause the time required to achieve appropriate power and confidence to increase exponentially.
3. Monitor data collection to ensure the sample sizes are \(approximately\) equally distributed.
  * If the sample sizes begin to diverge, additional calculations must be performed to determine the minimum required sample sizes for adequate confidence and statistical power. Significantly different sample sizes also require a pooled variance calculation to account for the imbalances.
4. Close out the test once adequate confidence and statistical power has been reached.
  * This will allow us to expedite analysis of the test outcomes and implementation of the changes if the desired outcome is achieved.

### Analyzing Results
1. Calculate mean value of the target metric
2. Calculate the variance standard deviation for each test & control group
  * For proportion-based target metrics the calculation is:
  * Variance
    * s1 = \(𝞺1 * \(1-𝞺1\)\) / n1
    * s2 = \(𝞺2 * \(1-𝞺2\)\) / n2
  * Standard deviation
    * s1 = √ \(𝞺1 * \(1-𝞺1\)\) / n1
    * s2 = √ \(𝞺2 * (1-𝞺2\)\) / n2
3. Calculate p-value
  * Ensure no overlap between confidence intervals of tests and control
4. Reject or accept null hypothesis