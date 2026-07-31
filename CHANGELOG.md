# Changelog

## v0.1.0

First planned public draft release of Caracal as experimental research software.

### Included public-facing capabilities

- four Grasshopper components:
  - Caracal Design Inputs
  - Caracal Analysis
  - Caracal Result
  - Caracal Compare
- simulation-derived EUI prediction
- simulation-derived Cooling EUI prediction
- local SHAP explanation for both targets
- EBM relationship and interaction views through the Result workflow
- neutral comparison workflow using Delta B−A
- packaged local/offline runtime

### Verified runtime characteristics

- no system Python required for normal operation
- no internet dependency for normal operation
- no development workspace dependency for normal operation

### Compatibility boundary

- Windows required
- Rhino 8 required
- `.NET 8 / NetCore` Rhino host runtime required
- independently tested on Rhino 8 SR33 `8.33.26188.13001`

### Important limitations

- supported-grid research domain only
- not a production-approved tool
- not an optimizer
- not a measured-energy predictor
- not a substitute for detailed project-specific simulation
