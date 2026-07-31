# Supported Domain

Caracal v0.1.0 operates only on approved supported research-grid points.

## Canonical supported values

### Aspect Ratio

- `1.0`
- `1.5`
- `2.0`
- `2.5`

### Orientation

- `0`
- `45`
- `90`
- `135`

### WWR

- `0.20`
- `0.35`
- `0.50`
- `0.65`

### Glass U-factor

- `1.0`
- `1.4`
- `1.8`
- `3.0`
- `5.7`

### SHGC

- `0.25`
- `0.35`
- `0.45`
- `0.60`

### Lighting Power Density

- `4`
- `6`
- `8`

### External Wall Insulation Thickness

- `0.01`
- `0.03`
- `0.06`
- `0.09`

## What `supported_grid_point` means

`supported_grid_point` means the design input matches an approved research-grid combination that Caracal v0.1.0 is allowed to analyze.

Only then can the full Result workflow produce:

- EUI prediction
- Cooling EUI prediction
- SHAP outputs
- EBM relationship/interactions content

## In-range off-grid behavior

A value can be numerically inside the overall min/max envelope and still be unsupported.

Example:

- `WWR = 0.42`

This is in range numerically, but it is not one of the approved supported-grid values. In RC5 independent-machine QA, this unsupported-domain behavior was verified to fail closed.

## Outside-domain behavior

Values outside the approved domain are also unsupported.

Caracal v0.1.0 does not broaden the domain automatically.

## No silent snapping

Caracal v0.1.0 does not silently snap unsupported values to the nearest approved grid point.

That means:

- no hidden rounding to the nearest approved case
- no automatic interpolation approval
- no silent substitution of a nearby supported design

## Why this boundary matters

Caracal is scoped to a fixed validated research domain. The supported-grid rule is part of that scientific boundary, not just a UI constraint.

## What Caracal does not provide here

- no confidence score
- no reliability score
- no universal applicability claim beyond the approved research domain
