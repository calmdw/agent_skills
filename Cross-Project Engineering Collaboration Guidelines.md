# Cross-Project Engineering Collaboration Guidelines

This document captures engineering habits and collaboration rules that are not tied to the peg-in-hole domain and can be reused in other projects.

## 1. Analysis Stage
- Confirm the active repository path, branch, worktree state, and entrypoint before making changes.
- Identify system boundaries and module owners before proposing edits.
- Distinguish long-term rules, current implementation details, and historical leftovers before generalizing patterns.

## 2. Design Stage
- Prefer the smallest change that solves the problem before considering broader refactors.
- State which behaviors must remain unchanged and which behaviors are expected to change.
- Distinguish primary decision metrics from diagnostic metrics and avoid mixing them.

## 3. Implementation Stage
- Keep changes local to the modules that own the behavior.
- Prefer configuration, clear interfaces, or data-layer separation over hard-coded special cases.
- Keep training, evaluation, aggregation, deployment, and reporting concerns separated when possible.

## 4. Validation Stage
- Run the cheapest meaningful validation first, then escalate to more expensive checks if needed.
- Validate not only that code runs, but that outputs, file locations, and artifact semantics are correct.
- Explicitly record what was validated and what was not validated.

## 5. Delivery Stage
- Final delivery should state what changed, why it changed, how it was validated, and what risks or follow-ups remain.
- When behavior semantics change, update the relevant documentation instead of leaving the context only in chat or commit messages.
- Keep generated artifacts separate from source code to preserve a clean repository surface.
