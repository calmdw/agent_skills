# Skill Index

## Current Formal Skills

- `rl-system-bootstrap`
  - start a new reinforcement learning project with a stable skeleton, interfaces, metrics, and artifact flow
  - template support: yes
- `rl-task-contract-design`
  - define task, reset, success, reward, fixed-eval, and pre-learning semantics before implementation spreads
  - template support: yes
- `metrics-layering-and-eval-design`
  - separate training metrics, fixed evaluation, aggregation, baseline handling, and model-selection semantics
  - template support: yes
- `hpc-experiment-ops`
  - run, validate, retrieve, and re-aggregate remote experiments in a repeatable way
  - template support: yes
- `paper-reproduction-audit`
  - ensure result packages are reproducible, auditable, and reportable
  - template support: yes

## Recommended Use Order

1. `rl-system-bootstrap`
   - use when project skeleton, config layering, and artifact flow are not yet stable
2. `rl-task-contract-design`
   - use when task, reset, success, reward, and pre-learning semantics are still ambiguous
3. `metrics-layering-and-eval-design`
   - use when metrics, fixed evaluation, and model-selection rules need to be defined
4. `hpc-experiment-ops`
   - use when work moves from local runs to remote experiment execution
5. `paper-reproduction-audit`
   - use when results must support reporting, reproduction, or audit

## Common Skip Cases

- Skip `rl-system-bootstrap` when the project skeleton is already mature.
- Skip `rl-task-contract-design` when the task contract is already written and trusted.
- Skip `metrics-layering-and-eval-design` when metrics and evaluation semantics are already stable.
- Skip `hpc-experiment-ops` when all work stays local.
- Skip `paper-reproduction-audit` when the work is still exploratory and not reportable.

## Short Boundary Reminder

- Skills explain reusable method.
- Project docs explain current-project fact.
- If a rule depends on one task, one simulator, or one cluster, keep it out of
  the library core.
