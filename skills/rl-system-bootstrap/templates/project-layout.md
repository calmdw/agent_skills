# Project Layout Template

Use this as a minimal RL project skeleton. Rename folders if needed, but keep
the responsibilities clear.

```text
project/
  scripts/
    run.py
  configs/
    task.yaml
    train.yaml
    eval.yaml
    deploy.yaml
  envs/
  controllers/
  algos/
  debug/
  deploy/
  docs/
```

## Layer Ownership

- `scripts/`
  - one main run entrypoint
- `configs/`
  - task, training, evaluation, and deployment configuration
- `envs/`
  - environment implementations
- `controllers/`
  - control implementations or action-to-command layers
- `algos/`
  - RL backend adapters, runner, checkpoint logic
- `debug/`
  - metrics, callbacks, evaluator, plots
- `deploy/`
  - manifests, submission, download, aggregation
- `docs/`
  - architecture, metrics, workflow, priorities, agents

## Replace Per Project

- task names
- backend choices
- exact config split
- deployment system details
