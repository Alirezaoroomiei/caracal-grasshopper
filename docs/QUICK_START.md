# Quick Start

This quick start walks through one verified supported-grid example.

A manually created, native-validated Grasshopper definition is also available:

- `examples/Caracal_Quick_Start.gh`

This definition was manually created and native-validated with the accepted Caracal candidate in the RC6-B1 acceptance stage.

## Example input set

Enter these values in Caracal Design Inputs:

- Aspect Ratio = `2.0`
- Orientation = `45`
- WWR = `0.65`
- Glass U-factor = `1.0`
- SHGC = `0.60`
- Lighting Power Density = `6`
- External Wall Insulation Thickness = `0.03`

## Basic workflow

1. Place a `Caracal Design Inputs` component.
2. Enter the seven values above.
3. Connect its `DIO` output to `Caracal Analysis`.
4. Set `Run = True` on `Caracal Analysis`.
5. Connect the `Result Object` output to `Caracal Result`.

## Expected analysis state

For this supported case, the verified expected status is:

- Analysis Status = `completed`
- Domain Status = `supported_grid_point`

## What you will see in Caracal Result

### Prediction

Caracal Result displays two simulation-derived energy indicators:

- Simulation-derived EUI
- Simulation-derived Cooling EUI

These are surrogate-model estimates for the fixed research context, not measured building data.

### SHAP

Caracal also shows local SHAP explanation outputs for both targets.

In simple terms, SHAP answers:

- which inputs pushed this prediction higher or lower relative to the model base value?

It is a local explanation of the XGBoost prediction for this design.

### EBM relationships

The Result workflow also includes EBM relationship views. These show how an independent interpretable reference model represents learned patterns across the approved design space.

### EBM interactions

The EBM interaction views help reveal pairwise interaction patterns learned by that reference model within the preserved research domain.

## Compare workflow

To compare two options:

1. Create two supported designs.
2. Run both through Caracal Analysis.
3. Send both completed Result Objects into `Caracal Compare`.

For a manually created, native-validated comparison example, use:

- `examples/Caracal_Compare_Example.gh`

Caracal Compare reports:

- Option A EUI / Cooling EUI
- Option B EUI / Cooling EUI
- Delta B−A for both targets when the pair is compatible

It does not rank options or choose a best design for you.

## If your design is unsupported

Caracal v0.1.0 only operates on approved supported research-grid points.

If your values are not exactly on those approved grid points, the workflow can fail closed instead of silently snapping values. See `SUPPORTED_DOMAIN.md`.
