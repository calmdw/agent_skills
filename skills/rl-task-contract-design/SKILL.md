---
name: rl-task-contract-design
description: Use when defining or porting a reinforcement learning task and you need a stable contract for episode, reset, success, reward, fixed evaluation, and pre-learning baseline semantics before implementation details spread through the stack.
---

# RL Task Contract Design

## Purpose

Use this skill to define the task-level semantics that should remain clear even
when the simulator, controller, robot, or RL backend changes.

This skill is about designing the task contract, not implementing one specific
task.

## When To Use

Use this skill when:

- starting a new RL task
- porting an existing task to a new simulator or controller
- clarifying what should count as success before large training work begins
- separating task semantics from stack-specific implementation details

## When Not To Use

Do not use this skill when:

- only refactoring implementation details in an already stable task
- tuning a controller without task-level ambiguity
- investigating a local bug that does not involve task semantics

## Core Questions To Answer

Before implementation expands, answer these questions explicitly:

- what is the task outcome the system is trying to achieve
- what counts as one complete episode
- what reset must guarantee
- what domain randomization is allowed to perturb
- what exactly counts as success
- what role reward plays
- what fixed evaluation should hold constant
- how pre-learning or warmup data should be treated

If these questions stay implicit, later metrics and model-selection logic will
drift.

## Stable Reusable Rules

- Define episode semantics before tuning.
- Keep reset and domain randomization separate.
- Define success independently from reward.
- Treat success as the primary task-completion surface by default.
- Treat reward as shaping or diagnostics unless deliberately promoted.
- Keep fixed evaluation separate from sampled online training metrics.
- Keep pre-learning data as baseline/debug evidence, not best-model evidence.

## Common Mistakes

- using reward as the final winner signal when the real target is success
- adding fixed evaluation only after online metrics become confusing
- letting success semantics drift as implementation changes
- mixing reset semantics with randomization semantics
- allowing pre-learning episodes to influence learned-policy selection

## Minimal Checklist

- write the task goal in one sentence
- write episode start and end semantics
- write reset responsibilities
- write randomization responsibilities
- write success semantics
- write reward role
- write fixed-eval role
- write pre-learning policy

## Bundled Templates

Use:

- `templates/task-contract-template.md`
  - a fillable task-contract template covering goal, episode, reset,
    randomization, success, reward, fixed evaluation, and pre-learning policy

This skill is often best paired with:

- `rl-system-bootstrap`
  - to place the task contract into a usable project skeleton early
- `metrics-layering-and-eval-design`
  - to turn the task contract into clear metrics, eval, and model-selection
    layers

## Lessons Reused From Current Project

- online training progress and final model selection should not be the same
  surface
- pre-learning baseline is valuable for warmup, comparison, and debugging
- campaign aggregation becomes misleading when task semantics are not defined
  cleanly early
- fixed evaluation is much easier to trust when its role is specified before
  implementation grows

## Current Project Details Intentionally Excluded

This skill deliberately does not include:

- any current task geometry thresholds
- current reward term decomposition
- current randomization details
- current controller-specific action interpretation
- current checkpoint naming conventions

## Notes On Stack-Bound Advice

If you must give stack-specific advice while using this skill:

- label it as backend-dependent
- keep it outside the core task rules
- avoid presenting implementation quirks as task semantics
