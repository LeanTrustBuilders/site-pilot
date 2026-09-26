# site-pilot

Sites built by [trust-site](https://github.com/LeanTrustBuilders/referee-site), published at
<https://leantrustbuilders.github.io/site-pilot/>:

- **LeanMachineLearning**, rebuilt every day from [LML](https://github.com/LeanMachineLearning/LML)'s
  `main` (`.github/workflows/lml.yml`): the library from its Mathlib cache, its dataset by the newest
  [trust-extract](https://github.com/LeanTrustBuilders/extractor) release for its toolchain, and the
  site against the previous build. `data/lml-ledger.json` is the provenance ledger the workflow keeps;
  each build's dataset is the release `lml-dataset-<commit>`.
- **LeanMachineLearning with trust's front end**, from the same build (`trust/`): the dataset is
  extracted with `--upstream-closure term`, written as the index
  [trust-web](https://github.com/LeanTrustBuilders/trust-web) reads (`trust-site trust-index`), and
  shown with our fork of it.
- **alpha-rar** and **colt-2026-83**, the whole library and claims only, built once (`demos/`). alpha-rar
  was built with `import Characterization` replaced by `import TrustAnnotations`, where `@[specifies]`
  and `@[characterization]` now live.
