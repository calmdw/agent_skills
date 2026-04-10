# Skill Index

## Planned Core Skills

- `rl-system-bootstrap`
  - start a new reinforcement learning project with a stable skeleton, interfaces, metrics, and artifact flow
- `rl-task-contract-design`
  - define task, reset, success, reward, fixed-eval, and pre-learning semantics before implementation spreads
- `metrics-layering-and-eval-design`
  - separate training metrics, fixed evaluation, aggregation, baseline handling, and model-selection semantics
- `hpc-experiment-ops`
  - run, validate, retrieve, and re-aggregate remote experiments in a repeatable way
- `paper-reproduction-audit`
  - ensure result packages are reproducible, auditable, and reportable

## Recommended Use Order

1. `rl-system-bootstrap`
2. `rl-task-contract-design`
3. `metrics-layering-and-eval-design`
4. `hpc-experiment-ops`
5. `paper-reproduction-audit`

## Common Skip Cases

- Skip `rl-system-bootstrap` when the project skeleton is already mature.
- Skip `rl-task-contract-design` when the task contract is already written and trusted.
- Skip `metrics-layering-and-eval-design` when metrics and evaluation semantics are already stable.
- Skip `hpc-experiment-ops` when all work stays local.
- Skip `paper-reproduction-audit` when the work is still exploratory and not reportable.
