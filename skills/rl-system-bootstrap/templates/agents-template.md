# AGENTS Template

## Working Style

- analyze the main entrypoint and config surface before making changes
- prefer concise, high-signal updates

## Change Principles

- make the smallest change that solves the problem
- avoid unrelated refactors
- keep interfaces and semantics explicit

## High-Risk Boundaries

- task semantics
- metrics and evaluation
- checkpoint and model-selection logic
- deployment and artifact paths

## Validation Rule

- do the cheapest meaningful validation first
- state clearly what was not validated

## Delivery / Reporting Rule

- say what changed
- say why it changed
- say what was verified
- say what still needs confirmation

## Artifact Hygiene

- keep runtime artifacts separate from source
- avoid mixing generated outputs into tracked code surfaces
