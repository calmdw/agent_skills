# Task Contract Template

## Task Goal

- What outcome should count as solving the task?

## Episode Semantics

- What marks episode start?
- What marks episode end?
- How are timeout and success different?

## Reset Semantics

- What must reset guarantee?
- Which initial conditions must be valid?

## Randomization Semantics

- What may be randomized?
- What must remain stable across randomized episodes?

## Success Semantics

- What is the primary success condition?
- Is there any hold or persistence requirement?

## Reward Role

- Is reward only shaping/diagnostic?
- If not, what parts are allowed to influence final selection?

## Fixed Evaluation Role

- What should evaluation hold constant?
- Which metric should be the primary evaluation output?

## Pre-Learning Policy

- Is pre-learning data retained?
- What is it used for?
- What is it explicitly not allowed to affect?
