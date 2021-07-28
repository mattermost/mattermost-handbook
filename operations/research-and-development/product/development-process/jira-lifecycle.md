# Jira ticket lifecycle

In addition to GitHub Issues, we also use Jira tickets for managing chunks of work to be performed.

## Ticket creation

Follow these [guidelines](https://handbook.mattermost.com/operations/research-and-development/product/development-process/new-bug-tickets).

## Ticket triage

Ticket triage happens within the team's normal sprint cycle. At that meeting, the team reviews all new tickets, assessing the scope, effort, and impact of the ticket. They make a decision of the priority of the ticket. Once it's decided in triage meeting that the ticket should be worked on, the ticket moves into its [first ticket state](#will-do).

## Ticket states

Tickets are in one of five states, and transition between states is typically linear. Before they reach the first state, the ticket must be [created](#ticket-creation) and [triaged](#ticket-triage) by the team. 

### Will Do

Ticket reach this state by having been assigned a sprint (could be the "Queued" sprint) and having been identified in triage as something the team desires to achieve. Tickets in this state typically do not have anyone assigned to them.

### To Do

Tickets reach this state by being assigned to the implementer, who has clear intention to work on the ticket soon (within the next Sprint or two). A ticket moves back to [Will Do](#will-do) if the implementer no longer has present or future bandwidth to do the work in the ticket.

### In Progress

Tickets reach this state by the implementer beginning to perform the work needed to finish the ticket. A ticket can be in progress for an indefinite period of time, but if tickets are routinely in progress across multiple Sprints, it is likely a sign that the tickets need better definition or reduction in scope. A ticket moves back to [To Do](#to-do) if the implmenter is no longer working towards completing the ticket.

### Submitted

For tickets that require code changes, tickets reach this state by the implementer opening a merge request. They can be in submitted state indefinitely as long as forward progress is being made in the merge request review. A ticket moves back to [In Progress](#in-progress) if are too many issues with the merge request for it to make sense to keep the merge request open.

### Done

Tickets reach this state by having a merge request merged. Once moved to this state, tickets trigger additional work to be performed by the QA team. Tickets move back into [In Progress](#in-progress) from this state if QA detects there are defects or regressions because of the work merged by the ticket.
