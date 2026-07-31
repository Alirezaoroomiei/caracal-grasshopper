# User Guide

## Caracal Design Inputs

### Purpose

Collects the seven required design values and creates a versioned Caracal Design Input Object.

### Inputs

- Aspect Ratio
- Orientation
- WWR
- Glass U-factor
- SHGC
- Lighting Power Density
- External Wall Insulation Thickness

### Outputs

- Design Input Object (`DIO`)
- Pre-check Status
- Messages

### Typical workflow

Use this component first. When all seven values are present, numeric, and finite, it prepares the input object for Caracal Analysis.

### Status / messages

- `ready`
- `incomplete`
- `invalid`

This status is a pre-check only. It is not the domain-status decision.

### Limitations

- checks only missing, non-numeric, and non-finite input conditions
- does not decide whether the design is on the approved research grid

### Common errors

- missing value
- non-numeric value
- invalid numeric state

## Caracal Analysis

### Purpose

Verifies the Design Input Object, determines its domain classification, and runs the full analysis when allowed.

### Inputs

- Design Input Object (`DIO`)
- Run (`True`/`False`)

### Outputs

- Result Object
- Analysis Status
- Domain Status
- Messages
- Diagnostics

### Typical workflow

Connect the `DIO` output from Caracal Design Inputs and set `Run = True` to request analysis.

### Status / messages

Analysis Status may report:

- `no_input`
- `ready`
- `running`
- `completed`
- `blocked`
- `failed`

Domain Status identifies whether the input is eligible for supported prediction.

### Limitations

- predictions and explainability outputs are available only when the domain is `supported_grid_point`
- failure states do not preserve a prior Result Object as a valid completed result

### Common errors

- no input connected
- unsupported-grid input
- package/runtime loading issue
- analysis not run because `Run` is false

## Caracal Result

### Purpose

Displays one completed Caracal Result Object and exposes prediction, explanation, scope, and detail outputs.

### Inputs

- Result Object

### Outputs

- Simulation-derived EUI
- Simulation-derived Cooling EUI
- Explanation Summary
- Domain Status
- Model Information
- Scope Summary
- Messages
- Input Snapshot
- EUI SHAP Contributions
- Cooling EUI SHAP Contributions
- Result Details

### Typical workflow

Connect the completed Result Object from Caracal Analysis and inspect both the numerical outputs and the explanation/reference-model views.

For a manually created, native-validated end-to-end example, open:

- `examples/Caracal_Quick_Start.gh`

### Status / messages

The Result component surfaces:

- candidate-status notice
- scientific limitation text
- detailed-simulation referral
- controlled validation/result messages

### Limitations

- accepts only a completed compatible Result Object
- output values remain bounded to the fixed research context
- EBM views are reference-model views, not causal proof and not an explanation of XGBoost

### Common errors

- Result Object missing
- incomplete or invalid Result Object
- unsupported-domain result

## Caracal Compare

### Purpose

Compares two completed Result Objects and reports neutral numerical differences.

### Inputs

- Result A
- Result B

### Outputs

- Option A EUI
- Option B EUI
- Delta EUI
- Option A Cooling EUI
- Option B Cooling EUI
- Delta Cooling EUI
- Compatibility Status
- Comparison Summary
- Messages
- Option A Input Snapshot
- Option B Input Snapshot
- Changed Inputs
- Comparison Details

### Typical workflow

Use after both options have already been analyzed successfully.

For a manually created, native-validated comparison example, open:

- `examples/Caracal_Compare_Example.gh`

### Status / messages

Compatibility Status may report:

- `compatible`
- `incompatible`
- `incomplete`

### Limitations

- Delta values are only available when the pair is compatible
- no ranking, scoring, or recommendation is applied

### Common errors

- one or both Result Objects incomplete
- incompatible result pair
- comparing objects that do not meet the required schema/identity checks
