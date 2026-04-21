# Changelog — thinking-os

All notable changes to this project are documented here.

Format based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).
This project adheres to [Semantic Versioning](https://semver.org/).

## [1.0.0] — 2026-04-21

### Initial release

First public release of `thinking-os` — a cognitive router skill for Claude that detects the type of problem posed and applies the right thinking framework.

### Added

#### Core routing system
- `SKILL.md` with cognitive router and 12 linguistic signature triggers
- Dual trigger modes: auto-detection (default) + explicit framework naming
- Priority rules for handling ambiguous cases (emotion > analytical, explicit > auto)

#### 12 thinking frameworks (one file each, progressive disclosure)
- `first-principles` — rebuild reasoning from scratch
- `second-order` — map cascading consequences
- `inversion` — avoid failure instead of pursuing success
- `ooda-loop` — fast-moving competitive situations
- `pre-mortem` — visualize failure before committing
- `5-whys` — diagnose root cause
- `expected-value` — trade-off under uncertainty
- `opportunity-cost` — trade-off between known options
- `bayesian` — update beliefs with new evidence
- `circle-of-competence` — assess qualification to decide
- `eisenhower` — urgent vs. important prioritization
- `10-10-10` — emotional decisions

#### Output formats
- Synthesis mode (default): 6-10 lines with clear action + blind spot
- Deep-dive mode (on demand): structured 300-500 word analysis per framework

#### Documentation & validation
- End-to-end examples for decision, problem diagnostic, and emotional cases
- 11 test cases with expected framework routing + red flags
- Apache 2.0 license
- CONTRIBUTING.md guide for new frameworks and router improvements

### Design principles enforced
- One framework at a time (no stacking without explicit request)
- No motivational fluff, no gurus name-dropping
- Emotion priority (10-10-10 or circle-of-competence override analytical frameworks when strong emotional markers detected)
- Action-ready format (every response contains a concrete action + blind spot)

### Known limitations in v1.0
- Trigger descriptions are currently French-first (English linguistic signatures not yet mapped)
- Framework body content is French-only (English translation on v1.1 roadmap)
- No memory of recently used frameworks within a session (planned v1.2)
- No explicit framework combination (planned v2.0)

### Tested on
- Claude Opus 4.7
- Claude Sonnet 4.6

Older Claude models may struggle with the linguistic signature detection.

---

## [Unreleased]

### Planned for v1.1
- Feynman Technique (learning / simplification)
- Minto Pyramid (communication)
- Systems Thinking framework
- English linguistic triggers in `SKILL.md`

### Planned for v1.2
- Memory of recently used frameworks (avoid repetition within conversation)

### Planned for v2.0
- Explicit framework combination (e.g., `first-principles` + `inversion` for strategic teardown)
