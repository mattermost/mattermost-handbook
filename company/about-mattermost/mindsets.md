# Mindsets

Mindsets are “tool sets for the mind” that help us find blindspots and increase performance in specific situations. They’re a reflection of our shared learnings and culture in the Mattermost community and at Mattermost Inc.

To make the most out of mindsets, remember:

* **Mindsets are tools:** Use common sense to find the right mindset for your situation. Avoid using ones that don’t fit.
* **Mindsets are temporary:** Try on a mindset the way you’d try a tool. You can always put it down if it doesn’t work.
* **Mindsets are not laws:** Mindsets are situation-specific, not universal. Don’t use them to debate.

When you read about great leaders, they share mindsets relevant to success in their specific situations, which differ from their peers. Remember that “advice is personal experience generalized” so be mindful about what you apply.

In this context, here are mindsets for Mattermost:

## Learn, Master, Teach

**Learn** a new topic quickly, develop **mastery** \(be the smartest person at the team/company/community on the topic\), then **teach** it to someone who will start the cycle over.

The best teachers can speed colleagues to surpass them. This mindset helps us constantly grow and rotate into new roles, while preventing single-points of failure where only one person is qualified for a certain task.

## Slow is Smooth, Smooth is Fast

Rushing to get something done can create confusion, errors, and/or \(paradoxically\) delays.

When you feel rushed, consider slowing down and taking a moment to ask: What would it look like for this project to be running smoothly?

If you're running a collaborative project, consider:

1. Are the people I'm working with clear on the intent of this project or workflow?
2. Is everyone clear on who needs to do what?
3. Are we aligned on the measures that signal if our work is a success?

Getting to a "Yes" on these three questions can smooth out your process, and move things faster.

## Boring Solutions

Use the simplest and most boring solution to solve problems.

The speed of innovation for our organization and product is constrained by the total complexity we have added so far, so every little reduction in complexity helps. Don’t pick an interesting technology or methodology just to make your work more fun; using established and proven tech and processes that best match our needs to ensure a more stable and more familiar experience for you and other contributors.

When facing a high impact problem without a simple and obvious solution, focus your time on:

* Understanding the problem you're solving.
* Understanding how others have solved the same problem in an enduring way.
* What vital changes, if any, are needed to apply a proven solution that works.

**More:** Read GitLab's boring solutions mindset and Dan McKinley's blog post on [choosing boring technology](https://mcfunley.com/choose-boring-technology).

## Emotion, Assumption, and Priority

Consider when rational people disagree, the cause often comes from one of three areas: emotion, assumption, and priority. Understanding the underlying difference in thinking can help us get to agreement faster:

1. **Emotion:** Is there a strong emotion biasing the discussion? Talking through that emotion can often solve an issue. It’s okay to have emotions. We're humans, not robots.
2. **Assumption:** People may have different underlying **assumptions** \(including definitions\). Try to understand each other’s assumptions and get to agreement or facts when you can.
3. **Priorities:** Finally, people can have different **priorities**. When everyone’s priorities are shared and understood it’s easier to find solutions that satisfy everyone’s criteria.

While the emotions, assumptions, priority mindset won’t work for everyone in every case, it’s helped resolve complex decisions in our company’s history.

## Likes and Wishes

An easy way to check in with team members about how things are going.

* What do you _like_ about how things are going?
* What do you _wish_ we might change?

Use these one-on-one or in a group as a way to open conversations about what to keep and what to change in how we do things.

## Drafts at 1%, 50%, 99%

Being clear on expectations when asking for someone’s review can help speed and smooth the process. In this mindset, there are three types of review:

* **1% Draft:** Completely open to ideas and changes in direction. Rework is inexpensive.
* **50% Draft:** Half complete work. There is structure, but also a lot of room for change. Some rework is inexpensive, some is expensive.
* **99% Draft:** Nearly completed work. Rework at this point is very expensive.

## Shoulder Check

When a new owner takes over a process or a project from a previous owner, there are a finite number of “blindspots” of which the original owner is aware and the new owner will need to understand.

Using the analogy of changing lanes while driving a vehicle and learning to do a “shoulder check” for information that is not visible from standard controls, we have a process for the new owner and previous owner to jointly review processes until the transfer is complete.

This process is similar to [Mini-boss, End-boss](#mini-boss-end-boss), except that the mini-boss is also the new owner of a process, and not only a reviewer. Shoulder checks should be requested by new owners to avoid “crashing”:

* Making changes to systems that break existing processes may lose data and hurt the productivity of others downstream without notice and without a replacement system in place \(behavior known as [“Dead Tarzan”](#dead-tarzan)\).
* Repeatedly investing in mis-prioritized projects due to a misunderstanding of requirements from project stakeholders and insufficient confirmation of intended outcomes.

Even when not crashing, as part of our [Self Awareness leadership principle](../../company/about-mattermost#leadership-principles.md), top team members will constantly be seeking feedback and review from people around the company.

## Brown M&Ms

A “brown M&M” is a mistake that could either signal dangerous oversights in the execution of a project, or be a completely innocuous and unimportant error. When a brown M&M is found, aim to rule out a dangerous error as quickly as possible. Do fast drilldowns and systematic checks to see if more brown M&Ms are found, and if so, an entire project may need to be reviewed.

Examples of brown M&Ms may include:

* Significant mistakes in process, consistency or documentation suggesting lack of review or lack of understanding of the pre-existing system.
* Ambiguous definitions that would make completion of a procedure difficult or unpredictable.

The name "brown M&M" comes from a safety technique used by the American music band Van Halen, who had to set up large, complex concert stages in third tier cities, where few local workers had experience with the safety standards vital to construction. In the [contract rider](https://en.wikipedia.org/wiki/Van_Halen#Contract_riders) with each venue, Van Halen required a bowl of M&M candies with all brown M&Ms removed. Failure to provide the bowl was grounds for Van Halen’s stage crew to inspect all of the local vendor’s work for safety issues, because it meant the vendor had not paid attention to detail, and safety could be at risk.

## Correct Minimums: Medic, Field Surgeon, Plastic Surgeon

When making project investment decisions, we optimize for high impact in the context of customer obsession, empowered by ownership, while being constrained by “be proud of what you build”.

The failure case is over-investing in processes and infrastructure, stealing mana from higher priority work, reducing speed and agility for the company and unnecessarily increasing cost and bureaucracy.

The objective of optimization is to invest at minimal levels for efficiency and safety while maximizing impact.

In making these trade-offs, consider the following mindsets:

* **Correct Minimum 1: Medic**

  > Safely fix something that is important, broken, and dangerous as fast as possible. Speed is critical - don't worry about “leaving a scar” on our architecture or business process, just own it and get it done. Solve the problem, **do not overbuild**.
  >
  > _Example:_ Something incorrect on our public website with more than 100 page views a month should be fixed immediately and not delayed to be done with a longer-term project, such as a website redesign. If the staging server cannot be pushed, this means manually fixing production and duplicating that change on staging, rather than trying to fix staging.

* **Correct Minimum 2: Field Surgeon**

  > Triage tasks that are important and broken but not dangerous, and fix the most important things with a minimum time and cost. Scarring should be a low-priority consideration – it's fine to leave scars and it's fine to spend a little energy to avoid big ones. Solve the problem for the next stage of growth, but don’t solve it in two to three stages ahead.
  >
  > _Example:_ In Mattermost, spend 2 mana to enable automated messages over 4000 characters to be broken into multiple posts instead of being rejected, which is a problem every developer hits when they attempt to output log information via `curl` commands.

* **Correct Minimum 3: Plastic Surgeon**

  > Fix and optimize critical, high volume flows in our customer experience and product with heavy investment if needed to make high impact changes. Scars can be avoided and removed to produce a high impact result.
  >
  > _Example:_ Click-tracking traffic on about.mattermost.com and optimizing flows to direct visitors to learn about the product and downloading it is a flow that should be continually optimized.

## Mini-boss, End-boss

After completing the initial draft of a project, there may often be more than one reviewer to approve changes. This may be for different disciplines to review the work \(for example, both development and design teams reviewing code changes to the user experience\) and it may also be for reviewers with different levels of experience to share feedback.

When reviewing significant user interface changes, code changes, responses to community or customers, or changes to systems or marketing material changes, it is ideal to have at least two reviewers:

* **Mini-boss:** Reviewer less experienced in domain or Mattermost standards for the first review.
* **End-boss:** Reviewer more experienced in domain or Mattermost standards for the final review for the discipline \(e.g. development, design, documentation, etc.\).

This system has several benefits:

1. The Mini-boss provides feedback on the most obvious issues, allowing the End-boss to focus on nuanced issues the Mini-boss didn’t find.
2. The Mini-boss learns from the End-boss feedback, understanding what was missed, and becoming a better reviewer.
3. Eventually the Mini-boss will be as skilled at reviewing as the End-boss, who will have nothing further to add after the Mini-boss review. At this point, the Mini-boss becomes an End-boss, ready to train a new Mini-boss.

The naming of this term comes from video games, where a person submitting material for review must pass a “mini-boss” challenge before a “end-boss” challenge for different disciplines.

## Savor Surprises

When we make important decisions quickly it's important to run at least a lightweight analysis to identify blindspots that could put success at risk. "Savoring surprises" means discussing unexpected findings from an analysis and understanding root cause in order to de-risk our original plan and/or find new opportunities.

Example: In our early days, just months after launching our first commercial product Mattermost had a product roadmap for security and DevOps features that was vetted by customer roadmap reviews. We "savored the surprise" that custom emojis \(which we assumed was a vanity feature to be cut\) was highly important to support legacy processes that used them to communicate different outcomes of an automated process, like a build break. The surprise made our roadmap more valuable and effective.

A good analysis will result in surprises uncovering blindspots. An analysis that has no surprises is a surprise in itself and the blindspot should be determined. Did the analysis use the right data and methodology? Was it free from the unconscious or conscious bias of someone influential?

**More:** Watch Scott Cook's talk on [savoring surprises](https://vimeo.com/254376327).

## RAPID for Complex Projects

When practical, projects and decision making should be run at the lowest possible level of the organization, by people who are closest to the facts and data.

When a project is complex and involves many stakeholders, a different approach may be needed. We use a RAPID framework for complex, multi-stakeholder projects where clarity in the roles of stakeholders is vital.

RAPID is an acronym for the five different roles a stakeholder might be asked to take on in a complex project: Recommend, Agree, Perform, Input, Decide.

Each stakeholder can take on one or more roles:

| Letter | Role | Responsibility |
| :--- | :--- | :--- |
| R | Recommend | Recommend a decision or action |
| A | Agree | Formally agree with decision. Views - especially Obstacles - should be documented in final proposal shared |
| P | Perform | Accountable for executing the decision once made |
| I | Input | Provide input to a recommendation. Views may or may not be included in final proposal |
| D | Decide | Make the decision and commit the organization to action |

**More:** RAPID framework from [Bain Consulting](https://www.bain.com/insights/rapid-tool-to-clarify-decision-accountability/).
