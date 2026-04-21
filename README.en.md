# thinking-os

![Version](https://img.shields.io/badge/version-1.0.0-blue) ![License](https://img.shields.io/badge/license-Apache%202.0-green) ![Claude](https://img.shields.io/badge/Claude-Skill-purple)

🌍 **[Français](README.md)** · **English**

> A cognitive router for Claude: detects the type of problem you're facing and applies the right thinking framework — instead of dumping generic advice.

## What it does

Most people collect mental models like stamps and then apply none of them correctly. `thinking-os` does the opposite:

1. **Diagnoses** the problem type automatically (decision, trade-off, diagnostic, comprehension, prioritization, emotional decision)
2. **Selects** the most relevant framework from a library of 12
3. **Applies** that framework rigorously to your specific case
4. **Produces** a short synthesis with a clear action + blind spot, with deep-dive available on demand

## The 12 frameworks

| Framework | When to apply |
|---|---|
| **First Principles** | Rebuild a topic cluttered with conventions |
| **Second-Order Thinking** | Decisions with cascading consequences |
| **Inversion** | "How to avoid failure" rather than "how to succeed" |
| **OODA Loop** | Fast-moving competitive situations |
| **Pre-Mortem** | Before an irreversible launch/commitment |
| **5 Whys** | Root-cause diagnostic |
| **Expected Value** | Trade-off under uncertainty |
| **Opportunity Cost** | Trade-off between known options |
| **Bayesian Update** | Integrate new information |
| **Circle of Competence** | "Am I qualified to decide on this?" |
| **Eisenhower Matrix** | Urgent vs. important prioritization |
| **10-10-10 Rule** | Emotional decisions |

## Trigger modes

**Auto mode (default)** — Claude detects via linguistic signatures:
- *"I'm torn between X and Y"* → trade-off
- *"Why is this not working"* → diagnostic
- *"I'm about to launch X"* → pre-mortem
- *"I've had enough"* → emotional decision
- etc.

**Explicit mode** — Name the framework:
- *"Apply first principles to X"*
- *"Do a pre-mortem on Y"*
- *"Use 10-10-10 on this decision"*

## Installation

### For Claude.ai (user skills)

1. Download or clone this repo.
2. Place the folder in `/mnt/skills/user/thinking-os/` (or your equivalent Claude.ai skill directory).
3. The skill triggers automatically on matching prompts.

### For Claude Code

```bash
cp -r thinking-os ~/.claude/skills/
```

Then verify with `/plugin` that the skill appears in your available skills.

### For Claude API

Package the folder as a `.skill` file and upload via the `/skills` endpoint. See the [official docs](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview).

## Usage examples

### Investment decision
> *"I have €50k. Should I put it into my startup or keep it as a safety buffer?"*

→ The skill detects `expected-value`, quantifies the scenarios, and outputs a recommendation with a ruin check.

### Product diagnostic
> *"My users are churning en masse. I've already redesigned the onboarding three times."*

→ The skill applies `5-whys`, tracing back to the root cause.

### Competitive situation
> *"A competitor just announced my feature, two weeks before my launch."*

→ The skill applies `ooda-loop`, producing a 48h action plan.

### Emotional decision
> *"I've had enough. I want to quit my job tomorrow."*

→ The skill applies `10-10-10`, protecting the user from the reflex decision.

## Complementary skill

[**execution-os**](https://github.com/alphilippo/execution-os) — execution system that composes with thinking-os:
- `thinking-os` answers **WHAT** to do (decisions, trade-offs, diagnostics)
- `execution-os` answers **HOW** to actually do it (sprint planning, deep work, weekly ritual, accountability)

Use them together to go from intent to execution.

## Structure

```
thinking-os/
├── SKILL.md                    # Metadata + cognitive router
├── README.md                   # French version
├── README.en.md                # This file
├── frameworks/                 # One file per framework (loaded on demand)
│   ├── first-principles.md
│   ├── second-order.md
│   ├── inversion.md
│   ├── ooda-loop.md
│   ├── pre-mortem.md
│   ├── 5-whys.md
│   ├── expected-value.md
│   ├── opportunity-cost.md
│   ├── bayesian.md
│   ├── circle-of-competence.md
│   ├── eisenhower.md
│   └── 10-10-10.md
├── examples/                   # End-to-end examples
│   ├── decision-example.md
│   ├── problem-example.md
│   └── emotional-example.md
└── tests/
    └── test-cases.md           # 11 validation prompts
```

## Design philosophy

- **Progressive disclosure**: the `SKILL.md` only contains the router. Frameworks are loaded on demand so they don't clutter the context window.
- **One framework at a time**: the skill refuses to stack frameworks without an explicit request — otherwise it turns into a pointless Charlie Munger seminar.
- **No name-dropping**: no "as Buffett said..." unless it's genuinely illuminating.
- **Emotion priority**: if the prompt contains strong emotional markers, `10-10-10` or `circle-of-competence` take precedence over analytical frameworks.
- **Action-ready format**: every output contains a concrete action + a blind spot. No fluff.

## Limitations

- Does not replace professional financial, legal, or medical advice.
- Trade-off frameworks rely on probabilities estimated by the user — the skill does not fabricate them.
- Doesn't trigger on pure-info questions (*"what's the capital of Chile?"*) — that's intentional.

> **Note**: Content in French (frameworks, examples, tests) is currently the reference version. An English translation of the framework bodies is on the roadmap.

## Roadmap

- **v1.0** (current): 12 frameworks + auto router + explicit mode
- **v1.1**: add Feynman Technique (learning), Minto Pyramid (communication), Systems Thinking
- **v1.2**: memory of recently used frameworks to avoid repetition
- **v2.0**: explicit framework combination (e.g., `first-principles` + `inversion` for strategic teardown)

## License

Apache 2.0 — fork, adapt, republish. If you make a useful fork, please share the link.

## Credits

Built with Claude as Skill Architect. Inspired by the work of Charlie Munger (mental models), Ray Dalio (principles), Shane Parrish (Farnam Street), and John Boyd's OODA tradition.
