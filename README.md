# site-pilot

Sites built by [trust-site](https://github.com/LeanTrustBuilders/referee-site), published at
<https://leantrustbuilders.github.io/site-pilot/>:

- **LeanMachineLearning**, rebuilt every day from [LML](https://github.com/LeanMachineLearning/LML)'s
  `main` (`.github/workflows/lml.yml`): the library from its Mathlib cache and its own modules, its
  dataset by the extractor's action (`LeanTrustBuilders/extractor/extract`, the newest trust-extract
  release for its toolchain), published as the release `lml-dataset-<commit>`, and the site against the
  previous build. `data/lml-ledger.json` is the provenance ledger, which `evidence-core ledger` records
  each build in and which names the previous build; `evidence-store dataset` fetches that build's
  dataset as the baseline.
- **LeanMachineLearning with trust's front end**, from the same build (`trust/`): the dataset is
  extracted with `--upstream-closure term`, written as the index
  [trust-web](https://github.com/LeanTrustBuilders/trust-web) reads (`trust-site trust-index`), and
  shown with our fork of it.
- **alpha-rar** and **colt-2026-83**, the whole library and claims only, rebuilt at every run with the
  current trust-site from their datasets (`demos.txt`: the releases `<name>-dataset-<commit>` of this
  repository, extracted by trust-extract 0.7.3) and their repositories at those commits. alpha-rar's
  dataset was extracted with `import Characterization` replaced by `import TrustAnnotations`, where
  `@[specifies]` and `@[characterization]` now live.

Nothing here computes what the pages say: the extractor writes the datasets, evidence-core decides
statuses, claims, changes and provenance, evidence-store fetches datasets, and trust-site lays pages
out.
