# Installation

## Verified host requirements

- Windows
- Rhino 8
- Rhino host runtime set to `.NET 8 / NetCore`

Independent-machine validation evidence for this release campaign:

- Rhino 8 SR33
- Version `8.33.26188.13001`

Current build reference baseline:

- Grasshopper SDK `8.22.25217.12451`

Conservative compatibility boundary:

- Rhino 8 is required
- `.NET 8 / NetCore` is required
- compatibility with older Rhino 8 releases below the referenced SDK baseline is not supported by current evidence
- do not interpret current evidence as support for all Rhino 8 versions

## Package-based installation

Caracal v0.1.0 is prepared as a manual package-folder release.

Live repository:

- `https://github.com/Alirezaoroomiei/caracal-grasshopper`

Published v0.1.0 release:

- `https://github.com/Alirezaoroomiei/caracal-grasshopper/releases/tag/v0.1.0`

### Package integrity rules

1. Keep the entire Caracal package intact.
2. Do not separate the `.gha` file from the `Runtime` and package files.
3. Place the package in a user-selected permanent local folder.
4. Do not assume Yak or Rhino Package Manager installation for this release.

### Recommended loading flow

1. Choose a permanent local folder for the full Caracal package.
2. Keep the package contents together exactly as released.
3. If Windows marked the files as downloaded from another machine or archive source, perform a conservative unblock check on the package files where appropriate before first load.
4. In Grasshopper, add the selected package folder through the normal Grasshopper Developer Settings / folder-loading mechanism appropriate to your manual local package workflow.
5. Restart Rhino and Grasshopper.
6. Confirm that `Caracal > Core` appears.
7. Confirm Rhino is running under `.NET 8 / NetCore`.

## Verified runtime behavior

Normal execution does not require:

- system Python
- internet access
- the Caracal development workspace
- a separate InterpretML installation
- Visual Studio
- .NET SDK

## Critical Rhino runtime requirement

Caracal requires Rhino to run under `.NET 8 / NetCore`.

### Verified failure mode under NetFX

If Rhino is explicitly running under `.NET Framework / NetFX`, Caracal may fail during GHA assembly load with a `System.IO.FileNotFoundException` referencing:

- `System.Runtime, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a`

This was observed during independent-machine QA and was resolved without changing Caracal binaries.

### Verified fix

In Rhino, run:

- `SetDotNetRuntime`

Then:

- choose `NetCore`
- restart Rhino

After switching Rhino to `.NET 8 / NetCore` and restarting Rhino, Caracal loaded successfully in the independent-machine QA campaign.

## First verification check after loading

In Grasshopper, confirm:

- `Caracal` tab visible
- `Core` panel visible
- components visible:
  - Caracal Design Inputs
  - Caracal Analysis
  - Caracal Result
  - Caracal Compare

## Quick functional test

Use the documented supported test case in `QUICK_START.md` or open the manually created native-validated example:

- `examples/Caracal_Quick_Start.gh`

Then confirm:

- Analysis Status = `completed`
- Domain Status = `supported_grid_point`

## If the plugin does not appear

Check:

- the full package folder is still intact
- the `Runtime` folder is present
- Rhino is running under `.NET 8 / NetCore`
- Grasshopper is loading the intended local package folder
- files were not blocked by Windows download-protection behavior

More troubleshooting guidance is in `TROUBLESHOOTING.md`.
