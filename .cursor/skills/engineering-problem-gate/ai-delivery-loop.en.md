# AI Delivery Loop

This document describes the larger delivery framework around `engineering-problem-gate`.

## One-Sentence Definition

Use first principles to see through the problem before opening the gate, use AI to structure the architecture after the gate, start AutoResearch only when subproblems enter a closed-loop space, and keep humans in the loop for acceptance and delivery.

## Why This Framework Exists

Teams often mix all of these into one conversation:

- understanding the problem
- designing the architecture
- generating implementation
- validating the result
- deciding whether it is deliverable

That creates drift, weak boundaries, and poor delivery control.

## Four Stages

### 1. See Through

Use first principles to understand:

- the real problem
- non-negotiable constraints
- what is essential vs. habitual
- the smallest correct direction

### 2. Structure

Use AI to break the work into:

- core layers
- adaptation layers
- business layers
- AI-friendly subproblems

### 3. Close the Loop

Start AutoResearch only when a subproblem:

- is small enough
- has clear input and output
- has local completion criteria
- can improve through iteration

### 4. Accept and Deliver

Keep human-in-the-loop for:

- final judgment
- constraint checks
- acceptance
- delivery decisions

## Position of `engineering-problem-gate`

Within this loop, the gate is best understood as:

- the unified entry point
- the front gate
- the bridge from problem understanding to structured decomposition

It should not replace:

- final architecture design
- implementation planning
- delivery acceptance
