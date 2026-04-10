# Contributing

Use this repository for reusable skill content, not for project-specific documentation.

## Good Candidates For This Library

- reusable startup methods
- reusable task-contract design methods
- reusable metrics and evaluation design methods
- reusable HPC workflow guidance
- reusable reproduction and audit guidance
- small templates and checklists that improve direct reuse

## Keep These In Project Docs Instead

- reward details for one task
- success thresholds for one task
- simulator-specific implementation notes
- controller-specific assumptions
- cluster-specific commands and paths
- project-specific compatibility history

## Before Promoting Project Lessons Into A Skill

Check that the content:

- solves one focused reusable problem
- does not depend on one project's reward or success details
- does not depend on one simulator or cluster layout
- clearly states `When To Use` and `When Not To Use`
- explicitly lists intentionally excluded project details
- has minimal templates if templates materially improve reuse

Use `PORTABILITY_CHECKLIST.md` before promoting content that started inside one
project.

## Update Skills vs Update Project Docs

Update the Skill library when:

- the reusable method changed
- a checklist or template materially improves reuse
- a cross-project boundary became clearer

Update only project docs when:

- the project changed but the method did not
- the change is task-specific
- the change is simulator-, controller-, trainer-, or cluster-specific
- the change is about one project's naming history or compatibility surface

## Preferred Flow For Returning Lessons From A Project

1. confirm the lesson is stable inside the project
2. decide whether it is reusable method or project fact
3. run the portability checklist
4. update the Skill library only if the lesson survives that filter

## Portability Standard

A skill is ready to live here when it can be understood without first reading
one project's README and when its stack-bound details are clearly labeled
instead of presented as universal rules.
