# FAQ

## Is Caracal an EnergyPlus replacement?

No. Caracal is a bounded research software workflow for simulation-derived early-stage prediction in an approved research domain.

## Does Caracal need Python installed on my system?

No for normal use. The verified release package uses a bundled local runtime.

## Does Caracal need internet access?

No for normal use.

## Can Caracal predict any building?

No. Caracal v0.1.0 is restricted to its approved supported research-grid domain and fixed research framing.

## Can Caracal optimize my design?

No. It does not automatically find the best design or run optimization.

## What does SHAP show?

SHAP shows the local contribution of each input feature to the current XGBoost prediction relative to the model base value.

## What does EBM show?

EBM shows how an independent interpretable reference model represents learned relationships and interactions across the approved design space.

## Why is my design unsupported?

Your values may not match the approved supported-grid points exactly, even if they are numerically within the broader min/max range.

## Which Rhino versions are supported?

Evidence currently supports only conservative wording:

- Rhino 8 required
- `.NET 8 / NetCore` required
- independently tested on Rhino 8 SR33 `8.33.26188.13001`

Do not interpret current evidence as support for all Rhino 8 versions.

## Is Caracal open source?

No for v0.1.0. Source code remains private.

## What is public in v0.1.0?

The public release is the binary package and its documentation/media under `Caracal Binary License — Research & Evaluation Release v0.1.0`. Source code is private.

## Can I use Caracal commercially?

Not without prior written permission. Commercial/professional use requires permission from Alireza Oroomiei.

## Can I cite Caracal?

Yes. A citation draft is prepared through `CITATION.cff` and `docs/CITATION.md`. DOI information is not assigned in this draft package.
