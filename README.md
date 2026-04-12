# Personal Skill Library

This repository is the upstream home for reusable Codex skills.

It stores cross-project methods, checklists, and templates that can be copied
into new projects. It is not the runtime documentation for any one project.

## What Belongs Here

- reusable engineering methods
- reusable workflow guidance
- reusable templates and checklists
- stable rules that apply across projects

## What Does Not Belong Here

- task-specific reward formulas
- task-specific success thresholds
- simulator-specific implementation hacks
- cluster-specific paths, usernames, or partitions
- one project's compatibility history
- one project's current runtime facts

## How To Use In A New Project

1. Choose only the skill directories you need under `skills/`.
2. Copy only those directories into the new project's `.codex/skills/`.
3. Do not copy an entire old project or an entire old `.codex/` blindly.
4. Write a project-specific `AGENTS.md` for that project.
5. Record which skill-library tag or commit the project imported.
6. Keep project facts and stack-specific details in the new project's docs.

## Current Library Shape

This repository currently carries:

- reusable formal skills under `skills/`
- bundled templates inside those skill directories
- repository-level docs that explain ordering, scope, portability, and
  maintenance
- cross-cutting workflow skills such as `research-project-butler`, which route
  project work without replacing technical skills

Use `SKILL_INDEX.md` for the recommended order and the role of each skill.

## Source Of Truth Boundary

- This repository is the source of truth for reusable skill content.
- Each project remains the source of truth for its own runtime behavior, task
  facts, and deployment details.
