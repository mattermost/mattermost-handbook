# Jira Ticket Lifecycle

In addition to GitHub Issues, we also use Jira tickets for managing chunks of work to be performed.

## Ticket triage

Ticket triage happens within the team's normal sprint cycle. At that meeting, the team reviews all new tickets, assessing the scope, effort, and impact of each ticket. They make a decision on the priority of the ticket. Once it's decided in triage meeting that the ticket should be worked on, the ticket moves into the [To Do](#to-do) state.

## Ticket states

Tickets are in one of several states, and transition between states is typically linear. The beginning to end flow is described below.

### Backlog

Ticket reach this state by being [created](https://handbook.mattermost.com/operations/research-and-development/product/development-process/new-bug-tickets). A ticket usually needs [triage](#ticket-triage) to proceed further. One notable exception is an urgent bug fix, which moves to "In Progress" as soon as the implementer has bandwidth to address the issue.

### Will Do

Ticket reach this state by having been assigned a sprint (could be the "Queued" sprint) and having been identified in triage as something the team desires to achieve. Tickets in this state typically do not have anyone assigned to them. This state is synonymous with "Select for Development".

### To Do

Tickets reach this state by being assigned to the implementer, who has clear intention to work on the ticket soon (within the next sprint or two). A ticket moves back to [Will Do](#will-do) if the implementer no longer has present or future bandwidth to do the work in the ticket.

### In Progress

Tickets reach this state by the implementer beginning to perform the work needed to finish the ticket. A ticket can be in progress for an indefinite period of time, but if tickets are routinely in progress across multiple sprints, it is likely a sign that the tickets need better definition or reduction in scope. A ticket moves back to [To Do](#to-do) if the implmenter is no longer working towards completing the ticket.

### Submitted

For tickets that require code changes, tickets reach this state by the implementer opening a pull request. Many tickets can be tested by QA at the time of the pull request. For such tickets, the QA steps to test and verify should be added to the ticket when moving the ticket to the "Submitted" state.

Tickets can be in submitted state indefinitely as long as forward progress is being made in the pull request review. A ticket moves back to [In Progress](#in-progress) if are too many issues with the pull request for it to make sense to keep the pull request open.

### Done

Tickets reach this state by having a pull request merged. Once moved to this state, tickets trigger additional work to be performed by the QA team. Tickets move back into [In Progress](#in-progress) from this state if QA detects there are defects or regressions because of the work merged by the ticket.

A ticket could also move to "Done" from any state if it is decided that the work or change will not be performed or accepted. Common reasons for this include:

* The ticket is a duplicate of another.
* The ticket is no longer relevant.
* Priorities changed enough that the ticket will never be worked on.
* A bug ticket can not be reproduced.
* What is observed in the bug ticket is deemed acceptable behavior.

### Close

A ticket reaches this state after QA verifies through testing that the change has been completed as anticipated.
