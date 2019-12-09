---
description: 1% Draft
---

# How to create a split test for web page

Split test \(i.e. A/B test\) of a web page is an experiment that enables you to test two or more variations of a web page to determine which variation performs optimally for a given conversion target.

The following gives a split test framework for a web page, inspired by [A/B testing process recommended by Optimizely](https://www.optimizely.com/optimization-glossary/ab-testing/):

1. **Identify Goal**: Which conversion metric are you trying to improve - conversion to a trial, clicking on purchase button, or something else? Deciding the goal is always the first step when creating a split-test on a web page.
2. **Generate Hypothesis**: Create a list of changes that you think may improve the identified conversion rate. Research other sites and talk to other team members as needed. Then, prioritize the list by ROI \(expected impact over cost of implementation\).
3. **Create Variations:** Based on the prioritized list of hypotheses, create variations for each option.
   1. Mattermost currently uses [VWO](https://vwo.com/platform/) to create variations for split tests. In the past, these have been carried out with separate URLs but is not required.
   2. In future, other platforms such as [Optimizely](http://optimizely.com/), or custom JavaScript code for large tests involving user flows may be used.
4. **Run Experiment**: Web page visitors should be randomly assigned to either the control or variation of the web page.
   1. At the start of the test, typically 80-90% of the visitors are assigned to the control group in case the variations result in significantly lower conversion rate. On day 3, the % of visitors assigned to the control group can be reduced.
5. **Analyze Results**: Compare the difference in performance between the variations, and calculate statistical significance. 
   1. Software like VWO and Optimizely usually calculate this for you automatically.
   2. [Read this article to learn more about statistical significance in split-tests](https://data36.com/statistical-significance-in-ab-testing/)
6. **Apply Results:** Regardless of which variation \(or control\) wins, consider if the learnings can be applied on any other pages, and continue to iterate to improve results.

