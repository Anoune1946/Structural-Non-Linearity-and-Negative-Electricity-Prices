# Reproducibility and current limitations

This file records practical issues found during the repository review. It is intended to prevent readers from mistaking a research notebook for a fully packaged and independently reproducible software release.

## Before running

1. Use a clean Python environment and install `requirements.txt`.
2. Configure `ENTSOE_TOKEN` when using the ENTSO-E source.
3. Inspect the market-specific constants at the top of the notebook.
4. Confirm the target dates, time zone, forecast information set and event threshold.
5. Run the notebook from a working directory where its local cache and output files can be written.

## Notebook-specific notes

### France — `01_France.ipynb`

- The notebook reads `C:/Users/P279390/Documents/Production et Prix en France/historique_2015_2024.csv`. This path is specific to one Windows environment and must be replaced with a portable path or a user-selected file.
- The notebook contains its own earlier modelling workflow and should not be assumed to be identical to the Germany/Luxembourg and Spain implementations.
- It interpolates missing hourly values and replaces prices above 1,000 €/MWh with a rolling median. These choices materially affect high-price observations and need an explicit methodological justification before research results are finalised.

### Germany / Luxembourg — `03_Allemagne_DE_LU.ipynb`

- The default source is ENTSO-E; an Energy-Charts alternative is also present.
- The current configuration uses data from 2019–2024 and a 2024 test period.
- Review the audit verdict and coverage tables before interpreting the model output.

### Spain — `04_Espagne_ES.ipynb`

- The default source is ENTSO-E; an Energy-Charts alternative is also present, with source availability to be checked.
- The current configuration uses data from 2019–2025 and a 2025 test period.
- The event threshold is configured separately from the Germany/Luxembourg notebook; preserve this distinction when comparing results.

## Information-set audit

The notebooks contain a `leak_free` configuration flag and comments about Day-Ahead availability. A flag alone is not a proof that every feature is known at the forecast origin. For every lag and physical variable, document the timestamp at which the value becomes available and compare it with the forecast cut-off. In particular, check the interpretation of the last-price lag.

## Figures and result files

The country notebooks call diagnostic plotting and summary-export routines. The generated files are local outputs; they are not all committed as final figures in the current repository. A public release should contain a curated `docs/figures/` directory and a result table produced from a clean, recorded run.

## Remaining reproducibility work

- replace the machine-specific France path;
- record a tested Python/package environment (for example, a lock file or `pip freeze` snapshot);
- separate reusable functions from notebook cells;
- add automated tests for temporal alignment, daylight-saving transitions, missing-data handling and model prediction;
- document the provenance and redistribution terms of each committed CSV file;
- rerun the notebooks from a clean environment and archive verified figures, summaries and run metadata.
