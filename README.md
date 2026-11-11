# Reproducible code for "Structural non-linearity and negative electricity prices"

This repository contains code and data to reproduce the analyses in the paper "..." by Mergane et al. (2026).

## Dependencies
- Python 3.9+
- Packages: numpy, pandas, scipy, scikit-learn, xgboost, hmmlearn, matplotlib, entsoe-py, requests, holidays, joblib, tzdata

Install with: `pip install numpy pandas scipy scikit-learn xgboost hmmlearn matplotlib entsoe-py requests holidays joblib tzdata`

## Usage
1. Request an ENTSO-E API key at https://transparency.entsoe.eu/
2. Set the `ENTSOE_TOKEN` environment variable to your key.
3. Run the notebooks in order:
   - `01_France.ipynb` 
   - `03_Allemagne_DE_LU.ipynb`
   - `04_Espagne_ES.ipynb`

The first run will download data from ENTSO-E (a few minutes per country). Subsequent runs use the cached data.

## Data
The `data/` directory contains raw data downloaded from ENTSO-E for each country. The notebooks download this data automatically, so this directory can be empty initially.

## Results
Key results are displayed in each notebook. Final estimates are exported to `summary_{pays}.json` files.
