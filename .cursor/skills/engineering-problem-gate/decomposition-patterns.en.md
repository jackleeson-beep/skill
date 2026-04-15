# Decomposition Patterns

Use this guide after the problem is clear enough to move into structured decomposition.

## What Counts as AI-Friendly Granularity

A subproblem is usually at a good granularity when it:

- has one core goal
- has clear input
- has clear output
- has a clear completion criterion
- has limited dependencies
- does not span too many domains at once
- can be explained in 1 to 3 sentences

If a task still contains multiple goals, multiple outputs, many hidden assumptions, or cross-role coordination, it is still too large.

## First-Principles Checklist

Before decomposing, answer:

1. What is the real result this task must achieve?
2. Which constraints are non-negotiable?
3. Which current practices are habits rather than true requirements?
4. What is the smallest loop that proves the direction is correct?
5. What is the smallest verification action that tests the direction?

## Standard Subproblem Template

```markdown
### Subproblem N
- Goal:
- Input:
- Output:
- Completion criteria:
- Dependencies:
- Suitable for direct AI work:
- Human review points:
```

## Recommended Decomposition Order

1. define the objective
2. fix the constraints
3. define interfaces or boundaries
4. isolate the core execution unit
5. define verification and acceptance

Prefer:

`problem essence -> constraints -> smallest loop -> verification`

instead of:

`feature list -> implementation list`

## Typical Good AI Tasks

- draft generation
- field normalization
- rule comparison
- option tables
- risk lists
- test case enumeration
- document rewriting
- local implementation under known constraints

## Tasks That Need More Framing First

- unclear goals
- conflicting constraints
- unverifiable success criteria
- complex multi-role collaboration
- high-risk design choices still under debate
