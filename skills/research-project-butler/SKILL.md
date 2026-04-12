---
name: research-project-butler
description: Use when a long-running research project needs a reusable workflow router for idea capture, task routing, debug triage, experiment review, release planning, reusable-method backflow, and clean session closeout.
---

# Research Project Butler

## Purpose

Use this skill to keep a research project operationally coherent as it grows.

This skill helps prevent:

- ideas getting lost
- active priorities turning into a catch-all inbox
- debug work starting from guesses instead of evidence
- release steps mixing unrelated scope
- reusable lessons staying trapped in one project

This is not a technical implementation skill. It is a workflow router for how
research work is captured, routed, reviewed, and closed out.

## When To Use

Use this skill when:

- a fleeting idea needs to be captured before it disappears
- a new note needs to be routed to the right document type
- a debug session needs a fixed evidence-first starting point
- a batch of runs or experiments has finished and needs review
- local changes need to be split into clean commits
- a new lesson may belong in the reusable skill library instead of project docs
- a session is ending and the next restart point should be made explicit

## When Not To Use

Do not use this skill when:

- the task is only to implement training logic
- the task is only to tune reward, controller, network, or optimizer details
- the task is only to inspect one plot, one log, or one artifact
- another specialized skill already directly covers the technical work

## Operating Modes

### Intake Mode

- Purpose:
  - capture a new idea quickly and classify it before it is lost or misrouted
- Inputs:
  - fleeting idea, follow-up thought, partially formed experiment direction
- Outputs:
  - destination doc type, status, and next routing step
- Common Mistakes:
  - putting every idea directly into active priorities

### Debug Mode

- Purpose:
  - start debugging from evidence instead of explanation
- Inputs:
  - issue summary, available logs, metrics, manifests, or eval outputs
- Outputs:
  - likely layer, first files to inspect, and next diagnostic step
- Common Mistakes:
  - opening viewer or plots before checking structured evidence

### Experiment Review Mode

- Purpose:
  - convert completed runs into tracked conclusions, caveats, and follow-ups
- Inputs:
  - summaries, metrics, eval outputs, plots, and run artifacts
- Outputs:
  - doc update targets, candidate TODO updates, and unresolved questions
- Common Mistakes:
  - writing permanent conclusions from one partial result set

Use `templates/experiment-review-checklist.md` when a run or campaign has
finished and the next step is to decide what should be updated or tracked.

### Release Mode

- Purpose:
  - keep commits, pushes, and repo boundaries clean
- Inputs:
  - local diff, repo status, pending doc updates, and release intent
- Outputs:
  - commit split plan and push-readiness check
- Common Mistakes:
  - mixing reusable-method changes and project-local changes

### Backflow Mode

- Purpose:
  - decide whether a stabilized lesson belongs in project docs or the skill
    library
- Inputs:
  - candidate lesson, supporting evidence, and portability risk
- Outputs:
  - project-fact versus reusable-method decision and target update path
- Common Mistakes:
  - promoting stack-specific details into reusable skills too early

### Session Close Mode

- Purpose:
  - end a session with a clear restart point instead of implicit memory
- Inputs:
  - what changed, what remains open, what was learned
- Outputs:
  - next-step summary, unresolved items, and handoff-ready notes
- Common Mistakes:
  - leaving important conclusions only in chat history

Use `templates/session-close-template.md` when a work session ends and the next
restart point should be explicit.

## Routing Rules

- Active priorities should only hold current work, partially completed work, and
  explicit deferred follow-up.
- Fleeting ideas should first go to an idea backlog or parking-lot style note,
  not directly into active priorities.
- Parameter or behavior conclusions belong in a tuning-log style document, not
  in a general TODO list.
- Session-specific restart notes belong in a handoff or summary surface.
- Current runtime behavior, current stack assumptions, and current outputs
  belong in project docs.
- Only stable, cross-project workflow or method lessons should be promoted into
  the reusable skill library.

## Stable Reusable Rules

- Do not use active priorities as the default inbox for new ideas.
- In debug work, inspect structured evidence before proposing causes.
- Before any release step, confirm which repo is being changed.
- Do not leave important conclusions only in chat or terminal output.
- Keep project facts and reusable methods in separate homes.
- Only move a lesson into the skill library when it is stable across more than
  one immediate situation.

## Bundled Templates

Use:

- `templates/idea-backlog-template.md`
  - to capture fleeting ideas before deciding whether they should be promoted
- `templates/debug-triage-checklist.md`
  - to start a diagnosis from evidence instead of guesswork
- `templates/commit-planning-checklist.md`
  - to split commit scope and protect repo boundaries before push
- `templates/experiment-review-checklist.md`
  - to review a finished run or campaign and route conclusions to the right
    document surfaces
- `templates/session-close-template.md`
  - to close a work session without losing the next restart point

## Related Skills

- `rl-system-bootstrap`
  - use when the project skeleton itself still needs to be designed
- `rl-task-contract-design`
  - use when the task contract is still ambiguous
- `metrics-layering-and-eval-design`
  - use when metrics, evaluation, and model-selection rules need clarification
- `hpc-experiment-ops`
  - use when the issue is specifically about remote experiment execution flow
- `paper-reproduction-audit`
  - use when a result set needs to support reporting, audit, or reproduction

This skill routes work toward those skills. It does not replace them.

## Lessons Reused From Current Project

- TODOs, ideas, and archived conclusions should not live in one undifferentiated
  list.
- Debugging accelerates when file inspection order is explicit.
- Commit quality drops quickly when repo boundaries are not checked deliberately.
- Reusable methods do not migrate themselves; they need an explicit backflow
  step.
- Session closeout matters more once a project spans many partial experiments
  and doc updates.

## Current Project Details Intentionally Excluded

This skill deliberately does not include:

- current reward or success details
- current experiment and campaign names
- current simulator, RL library, or controller assumptions
- current cluster, path, or scheduler conventions
- current branch history, merge state, or local workaround notes

## Open Questions

- whether a dedicated session-close template should be bundled by default
- whether a separate project-side idea backlog document should be treated as a
  strong default instead of an optional pattern
