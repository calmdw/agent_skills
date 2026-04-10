# Bootstrap Checklist Template

- [ ] define the task contract
- [ ] define simulator/env/controller/backend boundaries
- [ ] create one main run entrypoint
- [ ] create an explicit config schema
- [ ] make one minimal env reset/step path work
- [ ] make one minimal controller or action path work
- [ ] make one minimal training backend path work
- [ ] emit structured episode metrics
- [ ] save resolved config
- [ ] define checkpoint roles
- [ ] add fixed evaluation
- [ ] confirm run artifacts can be downloaded and re-aggregated

## Stop Condition

Do not scale experiments until:

- one short training run finishes
- one fixed evaluation finishes
- the run artifacts are inspectable afterward
