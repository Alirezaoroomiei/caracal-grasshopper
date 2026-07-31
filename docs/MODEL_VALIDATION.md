# Model Validation

This document separates model-validation evidence from software QA.

- Model validation asks how the preserved models performed against the research dataset and reproduction evidence.
- Software QA asks whether the packaged plugin/runtime behaved correctly in the verified release campaign.

These are related but not the same claim.

## XGBoost validation

Authoritative source used here:

- `05_evidence/ML_ARTIFACT_FREEZE_REPORT.md`

Canonical metrics recorded for the frozen MVP artifact package:

| Target | R² | RMSE | MAE | Training rows |
|---|---:|---:|---:|---:|
| EUI | 0.999941 | 0.108404 | 0.082113 | 15360 |
| Cooling EUI | 0.999955 | 0.093264 | 0.069522 | 15360 |

Notes:

- These values are model-validation metrics against the preserved simulation-derived dataset.
- They do not prove real-building accuracy.
- They do not justify use outside the approved research context.

## EBM validation

Authoritative source used here:

- `05_evidence/RC4_STAGE_A1B_INTERPRET_VERSION_REPRODUCTION_EXPERIMENT.md`

Verified authoritative/reproduced 80/20 metrics:

| Target | Authoritative R² | Reproduced R² | Authoritative RMSE | Reproduced RMSE | Authoritative MAE | Reproduced MAE |
|---|---:|---:|---:|---:|---:|---:|
| EUI | 0.994252 | 0.9942519436206232 | 1.070987 | 1.0709874544819828 | 0.750584 | 0.7505837999079676 |
| Cooling EUI | 0.996426 | 0.9964259058120083 | 0.830267 | 0.8302668517675343 | 0.580828 | 0.580827755540203 |

Additional verified note from the same evidence set:

- reproduction compatibility was established for preserved evidence using `interpret-core 0.7.8`
- this does not prove that `0.7.8` was the original historical thesis environment version

## Model validation is not software QA

Even strong model metrics do not mean:

- the plugin is production-approved
- the outputs represent measured performance
- the software is valid for arbitrary buildings or climates
- the software is an optimization or decision-automation tool

Software QA for the release package is documented separately in the RC5 evidence set.
