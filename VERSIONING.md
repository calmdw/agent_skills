# Versioning

Use simple git tags for stable library releases.

## Why Version This Library

- new projects should be able to say which reusable skill baseline they copied
- version tags make it clear which skills and templates were considered stable
  at the time of import
- versions also make later local project snapshots easier to reason about

## Current Baseline

The current library should be treated as:

- `v0.1.0`

Meaning:

- first usable personal skill library baseline
- stable enough to reuse across projects
- not yet heavily field-validated across many real downstream projects

## Version Progression Rules

### Patch

Use patch releases such as `v0.1.1` when the change is small and does not alter
the role of a skill.

Typical patch changes:

- wording fixes
- cross-reference fixes
- small template cleanup
- minor library-doc clarification

### Minor

Use minor releases such as `v0.2.0` when the reusable library meaningfully
grows or changes shape.

Typical minor changes:

- a new formal skill
- a new high-value bundled template
- a meaningful workflow change inside an existing skill
- a clearer reusable boundary that affects downstream use

### Major

Only consider a major release such as `v1.0.0` when:

- the library has been used successfully across multiple real projects
- the main skill roles are stable
- the template set is stable enough that large structural changes are no longer
  expected
- the library is no longer best described as an early reusable baseline

## How New Projects Should Reference Versions

When a project imports skills from this library, record:

- which tag or commit was used
- which skill directories were copied
- whether any project-local edits were made after import

Relationship to project-side `.codex/skills/`:

- the copied `.codex/skills/` content is a local snapshot
- this repository remains the upstream source of truth
- local snapshots should be refreshed only when the project actually needs a
  newer upstream skill or template

## First Release Recommendation

The current recommendation is:

- tag the present library state as `v0.1.0`

Why now:

- the library already has a stable repository structure
- the core reusable skills are present
- bundled templates now exist for direct reuse
- the source-of-truth boundary with project docs is clear

Why not `v1.0.0` yet:

- the library is reusable now, but not yet strongly field-validated across many
  downstream projects
- more real-use feedback is still expected to refine templates and boundaries

Do not cut a new version for every project-specific lesson. Keep project facts
in project docs.
