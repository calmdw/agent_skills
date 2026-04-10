---
name: hpc-experiment-ops
description: Use when running reinforcement learning experiments on HPC and you need a stable workflow for upload, container validation, GPU validation, submission, log inspection, result download, re-aggregation, and post-run diagnosis.
---

# HPC Experiment Ops

## Purpose

Use this skill to run RL experiments on HPC in a way that is repeatable,
diagnosable, and safe to aggregate later.

This skill is about the experiment operations workflow, not one specific
cluster.

## When To Use

Use this skill when:

- launching remote experiment campaigns
- working with containerized training jobs
- validating that remote runs actually use the intended runtime and device
- downloading results for local aggregation or diagnosis
- rerunning experiments after deployment or runtime fixes

## When Not To Use

Do not use this skill when:

- experiments are purely local
- only one cluster-specific command is needed and no reusable workflow is being
  designed
- the issue is purely task semantics or trainer logic rather than remote
  operations

## Core Workflow

Treat HPC experiment operations as one continuous workflow:

1. upload code
2. upload or update the runtime container
3. validate the runtime environment
4. validate GPU usage on an allocated GPU node
5. submit a small test or smoke run
6. inspect logs early
7. submit the full campaign
8. download results
9. re-aggregate locally

The stable idea is:

- submission is not the end of the workflow
- validation and retrieval are part of the workflow

## Stable Reusable Rules

- Keep code sync and large artifact sync separate.
- Validate the runtime before launching a full campaign.
- Validate GPU usage on a compute node, not only on a login node.
- Let one manifest row correspond to one experiment execution.
- Preserve enough run-local artifacts for later diagnosis.
- Rebuild summaries locally from run artifacts when in doubt.
- Read logs early enough to stop obviously bad runs.

## Common Failure Modes

- requested GPU but training actually used CPU
- incomplete runs treated as final evidence
- walltime too short for the true training budget
- duplicate runs mixed into one aggregation set
- downloading too much data too early instead of doing targeted diagnosis

## Minimal Checklist

- sync source
- sync or confirm runtime container
- validate runtime
- validate GPU visibility
- run a small test first
- inspect logs
- submit the main campaign
- download artifacts
- re-aggregate locally

## Bundled Templates

Use:

- `templates/hpc-diagnostic-checklist.md`
  - a short validation and diagnosis checklist for runtime, GPU, smoke run,
    logs, artifact download, and local re-aggregation

This skill is often best paired with:

- `rl-system-bootstrap`
  - when a new project needs remote experiment flow designed from the start
- `paper-reproduction-audit`
  - when downloaded artifacts must support reporting or reproduction claims

## Lessons Reused From Current Project

- whole-campaign download is useful, but targeted run diagnosis is often faster
- scheduler-level GPU allocation and trainer-level CUDA usage are separate
  checks
- walltime should be treated as part of experiment design
- scheduler log, resolved config, eval outputs, metrics, and checkpoint
  manifests are the highest-value diagnosis bundle

## Current Project Details Intentionally Excluded

This skill deliberately does not include:

- current scheduler partition names
- current container runtime flags
- current workspace root layout
- current cluster module names
- current username or path conventions

## Notes On Stack-Bound Advice

If you must include cluster-specific advice:

- mark it as scheduler-specific or cluster-specific
- keep it outside the reusable workflow rules
- treat it as an implementation note, not as the core method
