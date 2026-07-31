# Component Reference

This section documents the public component ports for Caracal v0.1.0 without changing names or behavior.

## Caracal Design Inputs

### Inputs

| Port | Nickname | Type | Purpose |
|---|---|---|---|
| Aspect Ratio | feature nickname in component | Number | Required numeric design input |
| Orientation | feature nickname in component | Number | Required numeric design input |
| WWR | feature nickname in component | Number | Required numeric design input |
| Glass U-factor | feature nickname in component | Number | Required numeric design input |
| SHGC | feature nickname in component | Number | Required numeric design input |
| Lighting Power Density | feature nickname in component | Number | Required numeric design input |
| External Wall Insulation Thickness | feature nickname in component | Number | Required numeric design input |

### Outputs

| Port | Nickname | Type | Notes |
|---|---|---|---|
| Design Input Object | DIO | Generic | Available only when Pre-check Status is `ready` |
| Pre-check Status | Status | Text | `ready`, `incomplete`, or `invalid` |
| Messages | Msg | Text list | Current input messages |

## Caracal Analysis

### Inputs

| Port | Nickname | Type | Purpose |
|---|---|---|---|
| Design Input Object | DIO | Generic | Versioned object from Caracal Design Inputs |
| Run | Run | Boolean | Set `True` to request analysis |

### Outputs

| Port | Nickname | Type | Notes |
|---|---|---|---|
| Result Object | Result | Generic | Complete result only when analysis succeeds fully |
| Analysis Status | Status | Text | `no_input`, `ready`, `running`, `completed`, `blocked`, `failed` |
| Domain Status | Domain | Text | Domain classification; prediction only for `supported_grid_point` |
| Messages | Msg | Text list | Input, domain, analysis, or failure messages |
| Diagnostics | Diag | Generic | Advanced technical details |

## Caracal Result

### Inputs

| Port | Nickname | Type | Purpose |
|---|---|---|---|
| Result Object | Result | Generic | Completed Caracal Result Object |

### Outputs

| Port | Nickname | Type | Level | Notes |
|---|---|---|---|---|
| Simulation-derived EUI | EUI | Number | Basic | XGBoost estimate, not measured consumption |
| Simulation-derived Cooling EUI | CEUI | Number | Basic | XGBoost estimate, not load sizing or measured consumption |
| Explanation Summary | Explain | Text list | Basic | Highest-magnitude model contributions |
| Domain Status | Domain | Text | Basic | Displayed Result must be `supported_grid_point` |
| Model Information | Model | Text list | Basic | Model IDs, versions, candidate status |
| Scope Summary | Scope | Text list | Basic | Fixed-context summary |
| Messages | Msg | Text list | Basic | Scientific and controlled messages |
| Input Snapshot | Inputs | Generic | Advanced | Exact read-only input snapshot |
| EUI SHAP Contributions | EUI SHAP | Generic list | Advanced | All seven EUI SHAP contribution records |
| Cooling EUI SHAP Contributions | Cooling SHAP | Generic list | Advanced | All seven Cooling EUI SHAP contribution records |
| Result Details | Details | Generic | Advanced | Identity, versions, provenance, model/explainer details |

## Caracal Compare

### Inputs

| Port | Nickname | Type | Purpose |
|---|---|---|---|
| Result A | A | Generic | Option A |
| Result B | B | Generic | Option B |

### Outputs

| Port | Nickname | Type | Level | Notes |
|---|---|---|---|---|
| Option A EUI | A EUI | Number | Basic | Full-precision EUI from Option A |
| Option B EUI | B EUI | Number | Basic | Full-precision EUI from Option B |
| Delta EUI | Δ EUI | Number | Basic | Option B minus Option A when compatible |
| Option A Cooling EUI | A CEUI | Number | Basic | Full-precision Cooling EUI from Option A |
| Option B Cooling EUI | B CEUI | Number | Basic | Full-precision Cooling EUI from Option B |
| Delta Cooling EUI | Δ CEUI | Number | Basic | Option B minus Option A when compatible |
| Compatibility Status | Compat | Text | Basic | `compatible`, `incompatible`, or `incomplete` |
| Comparison Summary | Summary | Text list | Basic | Neutral summary with no ranking |
| Messages | Msg | Text list | Basic | Connection, compatibility, candidate, or comparison messages |
| Option A Input Snapshot | A Inputs | Generic | Advanced | Read-only input snapshot |
| Option B Input Snapshot | B Inputs | Generic | Advanced | Read-only input snapshot |
| Changed Inputs | Changes | Generic list | Advanced | Fields that differ between A and B |
| Comparison Details | Details | Generic | Advanced | Pair identity, schema, mismatch, and Delta-availability details |
