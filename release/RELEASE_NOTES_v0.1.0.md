# Release Notes — v0.1.0

## Summary

Caracal v0.1.0 is the first planned public draft release of Caracal as experimental research software for explainable energy prediction in early-stage architectural design.

## What is included

- Caracal Design Inputs
- Caracal Analysis
- Caracal Result
- Caracal Compare
- simulation-derived EUI prediction
- simulation-derived Cooling EUI prediction
- local SHAP explanation outputs for both targets
- EBM relationship and interaction views in the Result workflow
- local/offline packaged runtime

## Workflow supported in v0.1.0

Design Inputs → Analysis → Result → Compare

## Compatibility

- Windows required
- Rhino 8 required
- `.NET 8 / NetCore` Rhino host runtime required
- independently tested on Rhino 8 SR33 `8.33.26188.13001`
- current build references Grasshopper SDK `8.22.25217.12451`

If Rhino is running under `.NET Framework / NetFX`, Caracal may fail to load because the plugin requires `System.Runtime 8.0`.

## Known limitations

- supported research-grid points only
- no silent snapping of unsupported values
- no optimization workflow
- no measured-building performance claim
- no universal applicability claim
- EBM is not an explanation of XGBoost

## Release status

- Public version: `v0.1.0`
- Primary terminology: `Experimental research software`
- Secondary terminology where context permits: `Public MVP`
- Binding status remains `Approved for Integration Development — Candidate Only`
- Production Promotion = `NOT APPROVED`
