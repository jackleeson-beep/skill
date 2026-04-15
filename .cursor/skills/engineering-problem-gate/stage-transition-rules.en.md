# Stage Transition Rules

This file turns the delivery loop into actionable decision rules.

Its job is to decide:

- when to keep asking
- when to move into decomposition
- when to start a closed loop
- when human review is mandatory

## 1. Keep Asking

Stay here when any of the following is still unclear:

- the concrete object
- the actual pain point
- the scope of change
- the success criteria
- the key constraints
- the explicit unknowns

Do not start:

- detailed solutioning
- implementation planning
- AutoResearch

## 2. Move to Decomposition

Move from `See Through` to `Structure` only when:

1. the object is clear
2. the main pain point is clear
3. the scope is clear
4. the success criteria are basically testable
5. at least 1 to 2 real constraints are known
6. unknowns are explicitly listed

## 3. Enter Closed Loop

Move from `Structure` to `Close the Loop` only when a subproblem:

1. has one core goal
2. has clear input
3. has clear output
4. has clear completion criteria
5. has controllable dependencies
6. will not change goals every round

Only then should AutoResearch be considered.

## 4. Human Review

Human review is required for:

1. validating the problem essence
2. validating the decomposition structure
3. confirming that a subproblem is truly in a closed-loop space
4. checking whether candidate outputs satisfy key constraints
5. deciding whether the result is deliverable

## Minimal Practical Rules

1. If the problem is not seen through, keep asking.
2. If the problem is clear, decompose before implementing.
3. If the subproblem is not closed-loop, do not start AutoResearch.
4. If there is no human review, it is not real delivery.
