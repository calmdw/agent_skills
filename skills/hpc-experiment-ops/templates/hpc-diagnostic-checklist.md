# HPC Diagnostic Checklist Template

## Runtime Validation

- [ ] code is synced to the intended workspace
- [ ] runtime/container version is the intended one
- [ ] resolved config is the intended one

## GPU Validation

- [ ] host compute node sees GPU
- [ ] container/runtime sees GPU
- [ ] trainer log confirms CUDA usage

## Smoke Run

- [ ] one small run completes or reaches stable startup
- [ ] logs are inspected before submitting the full campaign

## Early Log Inspection

- [ ] device usage is correct
- [ ] no immediate fallback or crash
- [ ] checkpoint/eval cadence looks reasonable

## Files To Pull For Diagnosis

- [ ] scheduler log
- [ ] resolved config
- [ ] checkpoint manifest
- [ ] eval summary and eval metrics
- [ ] debug summary and episode metrics

## Local Re-Aggregation

- [ ] downloaded artifacts are sufficient to rebuild summaries locally
- [ ] aggregation is rerun if summaries look stale or suspicious
