---
name: rl-system-bootstrap
description: Use when starting a new reinforcement learning project or rebuilding the core training stack for a new simulator, controller, robot, or RL backend, and you need a practical blueprint for architecture, metrics, evaluation, reproducibility, and experiment workflow from day one.
---

# RL System Bootstrap

## Purpose

Use this skill to bootstrap a new RL training system that is:

- trainable
- diagnosable
- evaluable
- reproducible
- aggregatable

This skill is about engineering method, not about one simulator, controller, or
RL library.

## When To Use

Use this skill when:

- starting a new RL project from zero
- replacing the simulator, controller, robot, or RL backend in an existing
  project
- building a training stack that should support fixed evaluation and campaign
  comparisons early
- preparing a project that may later need paper-style reproduction

## When Not To Use

Do not use this skill when:

- fixing a small bug in an already mature training stack
- tuning a single hyperparameter in an existing project
- working in a project that already has clear interfaces, metrics layers, and
  experiment operations in place

## Core Principles

- Keep one main run entrypoint.
- Layer configuration by responsibility, not convenience.
- Define task semantics before tuning.
- Keep reward separate from success unless there is a deliberate reason not to.
- Add structured episode metrics from day one.
- Add fixed evaluation before large sweeps.
- Keep pre-learning data as baseline evidence, not best-model evidence.
- Treat training metrics, fixed evaluation, and campaign aggregation as
  separate layers.
- Capture resolved config and artifact metadata early.
- Keep runtime artifacts separate from source.

## Recommended Architecture

Use a layout close to this shape:

- `scripts/`
  - one main run entrypoint
- `configs/`
  - task, train, eval, deploy surfaces
- `envs/`
  - environment implementations
- `controllers/`
  - control implementations
- `algos/`
  - backend adapters, runner, checkpoint logic
- `debug/`
  - metrics, callbacks, evaluator, plots
- `deploy/`
  - manifests, submission, download, aggregation
- `docs/`
  - architecture, metrics, debug, experiment workflow, priorities, agents

Prefer explicit boundaries between:

- simulator and env
- env and controller
- env and trainer
- trainer and metrics/checkpoint/eval
- experiment runner and remote execution/artifacts

## Must-Have Capabilities From Day 1

Before scaling experiments, make sure the project has:

- one run entrypoint
- a typed or otherwise explicit config schema
- a minimal environment that can reset and step
- a minimal backend path that can run a short train loop
- structured episode metrics
- resolved config snapshot
- explicit checkpoint roles
- fixed evaluation entrypoint

## Recommended Build Order

1. Build the skeleton and run entrypoint.
2. Define task, interface, and config boundaries.
3. Make one minimal environment/controller/backend path work.
4. Add structured metrics and resolved config capture.
5. Add checkpoint semantics and fixed evaluation.
6. Add campaign/remote execution flow and local aggregation.
7. Add reproducibility, reporting, and polish surfaces.

## Common Mistakes

- using reward as the final winner metric when the real goal is success
- relying only on online training windows for model selection
- delaying fixed evaluation until late in the project
- skipping structured episode metrics
- mixing runtime artifacts into the source surface
- using hand-written per-run commands after the experiment count grows
- defining task semantics implicitly through implementation details
- allowing pre-learning or warmup data to influence best-model selection

## Minimal Bootstrap Checklist

- write the task contract
- write the system interface boundaries
- define the metrics layers
- make one short training run finish
- make one fixed evaluation run finish
- confirm run artifacts exist and are organized
- confirm resolved config is saved
- confirm checkpoint semantics are explicit
- confirm campaign inputs can be reconstructed later

## Bundled Templates

Use these when you want a faster starting point without copying an old project:

- `templates/project-layout.md`
  - a minimal project directory skeleton with ownership by layer
- `templates/bootstrap-checklist.md`
  - a short build-order checklist from zero to a minimally usable RL stack
- `templates/agents-template.md`
  - a short project-level `AGENTS.md` starter for working style, boundaries,
    validation, reporting, and artifact hygiene

This skill is often best paired with:

- `rl-task-contract-design`
  - to define task semantics before implementation spreads
- `metrics-layering-and-eval-design`
  - to define metrics, fixed evaluation, and model-selection surfaces early

## Lessons Reused From Current Project

- A project becomes easier to evolve when the run entrypoint stays singular and
  explicit.
- Interface boundaries matter more than one concrete implementation.
- Fixed evaluation is easier to add early than to retrofit later.
- Pre-learning baseline is useful, but it should not define learned-policy
  quality.
- Campaign aggregation should be rebuilt from run artifacts, not from memory or
  ad hoc notes.
- Documentation should separate current-project facts from reusable methods.

## Current Project Details Intentionally Excluded

This skill deliberately does not include:

- task-specific reward terms
- task-specific success thresholds
- simulator-specific API details
- robot-specific control assumptions
- RL-library-specific callback behavior presented as universal truth
- cluster-specific scheduler, container, or path conventions
- compatibility artifacts kept only for historical reasons

## Notes On Stack-Bound Advice

If you must use stack-specific advice while applying this skill:

- mark it explicitly as backend-dependent
- keep it outside the core rules
- treat it as an implementation note, not as part of the reusable method
