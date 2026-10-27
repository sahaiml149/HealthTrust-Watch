# Data

This folder contains dataset documentation and a sample of the Health App Reviews for Privacy & Trust (HARPT) dataset used in the HealthTrust Watch project.

## Phase I Data

`sample_reviews.csv` contains a sample of HARPT reviews retained for Phase I reproducibility.

## Phase II Data

Phase II focuses on reviews of the MyChart healthcare application extracted from the HARPT dataset.

The analysis uses original review text, star ratings, review dates, and application-version information where available.

The full HARPT dataset is maintained separately and is not included in this repository.

To reproduce the Phase II analysis:

1. Obtain the HARPT dataset from its original authorized source.
2. Place the dataset in the local `data/` directory as `HARPT.csv`.
3. Run the Phase II notebook, which filters the dataset to MyChart reviews and performs data-quality checks before analysis.

Existing trust-related annotations are treated as unverified metadata rather than validated complaint labels.

Dataset licensing and redistribution conditions must be respected. The repository's MIT license applies to project code, not automatically to the underlying dataset.
