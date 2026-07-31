# Scientific Method

## Research origin

Caracal originated from Master's thesis research conducted at the School of Architecture, Iran University of Science and Technology.

## Dataset basis

Caracal v0.1.0 uses a simulation-derived dataset prepared for a fixed research context. The public software should therefore be interpreted within that same bounded context.

## Surrogate modeling

Instead of running a new full detailed simulation for every design iteration, Caracal uses a surrogate-model workflow for two targets:

- EUI
- Cooling EUI

## XGBoost prediction

XGBoost is the primary surrogate prediction model used to estimate the two simulation-derived outputs for supported design inputs.

## SHAP local explanation

SHAP provides local explanation of each XGBoost prediction. In practical terms, it helps show which input features pushed the predicted value upward or downward relative to the model base value for the current design.

## EBM reference model

Caracal also includes an independent interpretable reference model based on EBM outputs preserved for the approved research domain. This model is used to expose learned design-space relationships and interactions in a way that is readable to users.

EBM is not used here as an explanation of XGBoost.

## Fixed research context

The software is intentionally bounded to a fixed research context and approved supported research-grid points. This is why unsupported inputs fail closed rather than being silently accepted.

## Interpretation boundary

Caracal should be used as a bounded research/design-exploration tool. Its outputs should not be treated as:

- measured building performance
- proof of causal relationships
- universal predictions for arbitrary buildings, climates, or workflows
- a replacement for detailed project-specific simulation
