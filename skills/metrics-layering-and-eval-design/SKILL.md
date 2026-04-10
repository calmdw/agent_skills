---
name: metrics-layering-and-eval-design
description: Use when designing or repairing reinforcement learning metrics, fixed evaluation, campaign aggregation, pre-learning baseline handling, and model-selection semantics, especially when online best signals and final reported quality are drifting apart.
---

# Metrics Layering And Eval Design

## Purpose

Use this skill to design metrics and evaluation so that:

- training progress is observable
- final model selection is defensible
- campaign comparisons are interpretable
- pre-learning baseline data is useful without polluting learned-policy claims

Many RL projects become confused here because reward, online success, fixed
evaluation, and aggregated reporting are allowed to collapse into one vague
surface.

## When To Use

Use this skill when:

- starting a new project and defining metrics/eval from scratch
- an existing project shows a mismatch between online best and true best
- you need to define a model-selection rule for reports or papers
- campaign aggregation is mixing signals that should stay separate

## When Not To Use

Do not use this skill when:

- you only need to inspect one training curve
- the current metrics/eval design is already stable and not being revised
- the problem is purely deployment, task semantics, or controller behavior

## Core Principles

- Keep reward separate from success unless there is a deliberate reason not to.
- Keep training metrics separate from fixed evaluation.
- Keep run-level outputs separate from campaign-level aggregation.
- Keep pre-learning baseline as analysis context, not final learned-policy
  evidence.
- Define model-selection semantics explicitly before large comparison work.
- Treat diagnostics as support signals, not final decision surfaces.

## Metrics Layers

Design the metrics system as distinct layers.

### Run-Level Training Metrics

Use for:

- learning progress
- episode behavior
- reward, geometry, contact, and horizon diagnosis

Do not use as the only final model-selection surface.

### Run-Level Fixed Evaluation

Use for:

- comparing saved checkpoints on a controlled evaluation surface
- selecting the preferred reportable checkpoint

### Campaign-Level Training Aggregation

Use for:

- comparing training dynamics across seeds and configurations
- understanding stability and late-stage behavior

### Campaign-Level Evaluation Aggregation

Use for:

- comparing configurations under fixed evaluation
- deciding whether online gains survive standardized comparison

### Pre-Learning Baseline

Use for:

- warmup/baseline analysis
- debugging
- comparison against learned behavior

Do not let it compete in learned-policy best-model selection.

## Common Mistakes

- using reward as the final winner signal
- trusting online training best as if it were fixed-eval best
- treating training plots as final evaluation
- omitting a fixed evaluation protocol
- allowing pre-learning data to influence best-model selection
- aggregating incomplete, duplicate, or heterogeneous runs together
- mixing training summaries and eval summaries into one undifferentiated number

## Minimal Design Checklist

- define the primary task-quality metric
- define which metrics are diagnostic only
- define the fixed evaluation protocol
- define the model-selection rule
- define the pre-learning baseline policy
- separate run-level and campaign-level outputs
- separate training summaries and eval summaries
- decide how incomplete or duplicate runs are handled

## Bundled Templates

Use:

- `templates/metrics-layer-template.md`
  - a fillable template for primary metric, diagnostics, training/eval layers,
    pre-learning baseline, and model-selection rule

This skill is often best paired with:

- `rl-task-contract-design`
  - to define success and reward roles before metric layers are finalized
- `rl-system-bootstrap`
  - to place the resulting metrics design into a broader project skeleton

## Lessons Reused From Current Project

- online training progress and final model selection should not be the same
  surface
- fixed evaluation is more reliable than online best alone for reported model
  choice
- pre-learning data is useful, but it should not define learned-policy quality
- campaign aggregation is only trustworthy when metrics layers stay distinct
- reward can be highly informative without being the final reported objective

## Current Project Details Intentionally Excluded

This skill deliberately does not include:

- current field names
- current plot file names
- current checkpoint compatibility history
- current task-specific reward terms
- current task-specific success rules

## Notes On Stack-Bound Advice

If a design choice depends on the trainer stack:

- mark it explicitly as backend-dependent
- keep the general semantic rule separate from the stack-specific mechanism
- avoid presenting one framework's callback, logging, or serialization behavior
  as universal RL practice
