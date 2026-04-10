# Versioning

Use simple git tags for stable library releases.

## Recommended Rule

- tag the library when the reusable method meaningfully changes
- keep patch updates for wording, clarity, and template fixes
- keep minor updates for new stable skills or meaningful workflow improvements

## Suggested Shape

- `v0.1`
- `v0.2`
- `v0.3`

## What Projects Should Record

When a project imports skills from this library, record:

- which tag or commit was used
- which skill directories were copied
- whether any project-local edits were made after import

## When To Cut A New Version

Create a new tagged version when:

- a new skill becomes stable enough for reuse
- a skill's core workflow changes
- bundled templates change in a way that affects downstream use

Do not create a new version for every project-specific lesson. Keep project facts in project docs.
