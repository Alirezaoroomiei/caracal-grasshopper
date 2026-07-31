# Explainability Guide

## What does XGBoost do here?

In Caracal v0.1.0, XGBoost is the primary surrogate prediction model.

It predicts:

- simulation-derived EUI
- simulation-derived Cooling EUI

for supported design inputs inside the approved research domain.

## What does SHAP show?

SHAP answers a local question:

- Why did the XGBoost model produce this prediction for this design?

It does this by showing how each input feature contributed relative to the model base value for that specific case.

### What users should infer from SHAP

- which features had stronger local influence on this prediction
- whether a feature pushed the prediction upward or downward relative to the base value
- how contribution magnitudes compare within this one analyzed case

### What users should not infer from SHAP

- causal proof
- universal design rules outside the approved domain
- guaranteed performance outcomes
- confidence or reliability scores

## What does EBM show?

EBM answers a different question:

- How does an independent interpretable reference model represent learned design-space relationships and interactions within the approved research domain?

### What users should infer from EBM

- how the reference model represents single-feature relationships across the preserved design space
- which pairwise interactions are present in that reference-model view
- where the current design sits relative to those learned patterns

### What users should not infer from EBM

- that EBM is explaining the internal reasoning of XGBoost
- causal proof
- universal behavior for all building problems
- a recommendation engine or optimizer

## SHAP and EBM together

Caracal uses both because they serve different interpretability purposes:

- SHAP = local explanation of the current XGBoost prediction
- EBM = independent interpretable reference model of learned relationships/interactions

They should be read together carefully, not collapsed into the same claim.
