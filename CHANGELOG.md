# Changelog

All notable changes to this repository will be documented in this file.

## [Unreleased]

### Added

- Added `flow-boundary-notes.md` to clarify where `engineering-problem-gate` should stop and when work should move into later design or delivery stages.
- Added `ai-delivery-loop.md` to describe the larger four-stage delivery framework around the gate skill.
- Added `v0.3-iteration-plan.md` to reposition `engineering-problem-gate` as a delivery entry skill rather than only a problem-framing gate.
- Added `autoresearch-positioning.md` to align the AutoResearch definition with the original `karpathy/autoresearch` loop semantics.
- Added English companion documentation and bilingual language support guidance for the `engineering-problem-gate` skill suite.

### Changed

- Upgraded `engineering-problem-gate/SKILL.md` to v0.3: repositioned as the entry skill of the AI Delivery Loop, added first-principles pre-check, minimum required fields, lightweight vs full workflows, hardened gate pass/fail conditions, explicit closed-loop vs AutoResearch distinction, and human-in-the-loop checkpoints.
- Clarified that `Close the Loop` does not automatically imply `AutoResearch`, and defined stricter experiment conditions for triggering AutoResearch.

## [v0.1] - 2026-04-15

### Added

- Added the `engineering-problem-gate` skill suite for project intake, problem framing, decomposition, rollout, and release support.
- Added the `framing-problems-before-building` skill for early-stage problem clarification.
- Added a root `README.md` to explain repository purpose and entry points.

### Changed

- Expanded `.gitignore` to exclude local macOS metadata, release zip files, and local tool state artifacts.

## [Initial] - 2026-04-14

### Added

- Initial repository setup.
