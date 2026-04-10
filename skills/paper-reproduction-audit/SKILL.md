---
name: paper-reproduction-audit
description: Use when preparing or reviewing reinforcement learning experiment results for paper reproduction, reporting, or audit, and you need explicit rules for saved artifacts, checkpoint selection, evaluation protocol, seed discipline, and evidence quality.
---

# Paper Reproduction Audit

## Purpose

Use this skill to determine whether an experiment result is reproducible,
auditable, and reportable rather than merely runnable.

This skill is about evidence quality and reproduction discipline, not about one
paper or one project.

## When To Use

Use this skill when:

- reproducing a paper
- preparing reportable experiment results
- auditing whether a run set is strong enough to support a claim
- checking whether checkpoint selection and evaluation protocol are documented

## When Not To Use

Do not use this skill when:

- doing quick exploratory runs with no reporting goal
- debugging a local issue unrelated to reproducibility
- investigating implementation-only details that do not affect evidence quality

## Reproduction Questions To Answer

Any reproducible result package should be able to answer:

- what configuration actually ran
- which seeds were used
- what the training budget was
- which checkpoint was reported
- what the evaluation protocol was
- how aggregation was performed
- what differs from the original paper or target baseline, if anything

If these questions cannot be answered from saved artifacts, the result is not
fully auditable.

## Stable Reusable Rules

- Save the resolved config, not only the intended config.
- Record seeds explicitly.
- Define checkpoint selection rules before results are compared.
- Keep evaluation protocol stable enough to rerun.
- Preserve run-level evidence, not only final aggregates.
- Ensure aggregate summaries can be traced back to run-level artifacts.

## Required Artifacts

At minimum, preserve:

- resolved config
- experiment manifest
- checkpoint manifest
- logs
- eval outputs
- summary outputs

If any reported claim depends on a specific checkpoint or protocol, that
supporting artifact must also be preserved.

## Common Mistakes

- changing the model-selection rule after results are already collected
- failing to lock or record critical versions
- not preserving the evaluation protocol
- keeping only averaged results without run-level evidence
- mixing incomplete or incomparable runs into final aggregation

## Minimal Checklist

- save resolved config
- save experiment manifest
- save checkpoint manifest
- save logs
- save eval outputs
- record the reported checkpoint choice
- record the seed set
- record the aggregation rule
- record any meaningful deviation from the intended baseline or paper

## Bundled Templates

Use:

- `templates/reproduction-audit-checklist.md`
  - a short audit checklist for configuration, seeds, budget, checkpoint rule,
    evaluation protocol, artifacts, aggregation, and final reporting questions

This skill is often best paired with:

- `metrics-layering-and-eval-design`
  - when reporting depends on explicit model-selection and eval-layer rules
- `hpc-experiment-ops`
  - when the evidence bundle depends on remote runtime artifacts and
    re-aggregation

## Lessons Reused From Current Project

- checkpoint manifests and eval summaries dramatically improve auditability
- fixed evaluation is a better reporting surface than online best alone
- pre-learning baseline belongs in analysis context, not in final reported
  learned-policy evidence
- local re-aggregation is valuable because final reporting should not depend on
  one stale summary file

## Current Project Details Intentionally Excluded

This skill deliberately does not include:

- current reward details
- current success thresholds
- current checkpoint naming conventions
- current cluster-specific job metadata assumptions
- current task-specific reporting language

## Notes On Stack-Bound Advice

If a reproduction rule depends on the stack:

- say so explicitly
- keep the generic audit rule separate from the stack-specific implementation
- do not treat one project's deployment metadata as a universal reporting
  standard
