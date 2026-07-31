# Limitations

Caracal v0.1.0 is intentionally bounded. The following limitations should be treated as part of the software definition, not as minor caveats.

## Simulation-derived outputs

Caracal reports simulation-derived EUI and Cooling EUI estimates. These are not measured building outcomes.

## Fixed research context

The software operates within a fixed research context preserved from the approved evidence base. It should not be generalized automatically to unrelated contexts.

## Fixed typology / climate / workflow boundary

Public documentation for v0.1.0 should treat Caracal as valid only within its approved research framing and supported-grid workflow.

## Supported-grid restriction

Caracal v0.1.0 only operates on approved supported research-grid points.

- unsupported values fail closed
- in-range off-grid values are still unsupported
- there is no silent snapping

## No measured-building validation claim

The current evidence does not support claiming that Caracal predicts actual measured building energy use.

## No optimization claim

Caracal does not optimize designs and does not automatically identify a best design.

## No causal interpretation

SHAP and EBM outputs should not be read as proof of causal relationships.

## No guaranteed energy savings

Caracal does not provide a guarantee of energy savings, compliance, or final project performance.

## No universal applicability

Caracal should not be described as a universal building-energy model or as valid for all buildings, climates, and project conditions.

## Ideal Air Loads context

Public documentation should preserve the software’s simulation-derived framing and should not expand it into HVAC equipment sizing, operational utility billing, or measured-performance claims.

## EBM is not an explanation of XGBoost

EBM is an independent interpretable reference model for learned design-space relationships and interactions. It is not the mechanism by which XGBoost is explained.
