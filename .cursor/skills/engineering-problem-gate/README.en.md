# Engineering Problem Gate

This directory contains the `engineering-problem-gate` skill suite.

Its purpose is to help engineering teams:

- collect project context before execution
- frame problems before writing plans or code
- decompose work into AI-friendly subproblems
- decide when something is mature enough to become a `skill` or `harness`

## What Is Included

```text
engineering-problem-gate/
├── README.md
├── README.en.md
├── SKILL.md
├── SKILL.en.md
├── project-intake.md
├── project-intake.en.md
├── role-fields.md
├── role-fields.en.md
├── decomposition-patterns.md
├── decomposition-patterns.en.md
├── ai-delivery-loop.md
├── ai-delivery-loop.en.md
├── stage-transition-rules.md
├── stage-transition-rules.en.md
└── ... rollout and release docs
```

## Recommended Reading Order

1. `project-intake.md` / `project-intake.en.md`
2. `SKILL.md`
3. `decomposition-patterns.md` / `decomposition-patterns.en.md`
4. `role-fields.md` / `role-fields.en.md`
5. `ai-delivery-loop.md` / `ai-delivery-loop.en.md`
6. `stage-transition-rules.md` / `stage-transition-rules.en.md`

## Practical Positioning

`engineering-problem-gate` is not a final architecture engine.

Its best role is:

- a front gate
- a problem framing layer
- a structure entry layer
- a transition point into deeper design, iteration, or human review

## Language Support

The skill now supports both Chinese and English workflows:

- Chinese input -> Chinese output
- English input -> English output
- Mixed input -> use the dominant language and keep important terms aligned when useful
