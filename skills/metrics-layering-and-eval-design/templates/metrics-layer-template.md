# Metrics Layer Template

## Primary Metric

- What is the main task-quality metric?

## Secondary Metrics

- What metrics support comparison but do not define final selection?

## Diagnostics

- What metrics explain behavior or failure modes?

## Run-Level Training Metrics

- What should be recorded during training?
- What questions should these metrics answer?

## Run-Level Fixed Evaluation

- What should be evaluated on saved checkpoints?
- What is the fixed evaluation protocol?

## Campaign-Level Training Aggregation

- What training summaries should be compared across runs/seeds?

## Campaign-Level Evaluation Aggregation

- What evaluation summaries should be compared across runs/seeds?

## Pre-Learning Baseline

- Is pre-learning data retained?
- What is it used for?
- What is it not allowed to affect?

## Model-Selection Rule

- Which surface selects the reportable checkpoint?
- Which surfaces are diagnostic only?
