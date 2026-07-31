# Troubleshooting

## The plugin does not appear in Grasshopper

Check the following first:

- the full Caracal package folder is still intact
- the `Runtime` folder is present
- Grasshopper is loading the intended folder
- Rhino has been restarted after placing the package

Also verify that Rhino is running under `.NET 8 / NetCore`.

## Rhino / Grasshopper finds the GHA but Caracal does not load

### Verified cause

During independent-machine QA, Caracal failed to load when Rhino was running under `.NET Framework / NetFX`.

Observed failure class:

- `System.IO.FileNotFoundException`

Observed missing assembly:

- `System.Runtime, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a`

### Verified fix

1. In Rhino, run `SetDotNetRuntime`.
2. Choose `NetCore`.
3. Restart Rhino.

## My input is unsupported

Caracal v0.1.0 works only on approved supported research-grid points.

Common cause:

- one or more inputs are not exactly on the approved grid, even if they are numerically within the overall min/max range

See `SUPPORTED_DOMAIN.md`.

## Nothing happens when I connect Analysis

Check the `Run` input on Caracal Analysis.

- if `Run` is `False`, no full analysis is requested

## The package structure looks incomplete

Caracal should be kept as a complete package folder.

Problems can occur if:

- the `Runtime` folder is missing
- the `.gha` file is moved away from the packaged runtime structure
- only part of the package is copied

## Should I install system Python?

No.

Normal Caracal execution for v0.1.0 is designed to use the packaged local runtime. The verified release evidence does not require users to install system Python.
