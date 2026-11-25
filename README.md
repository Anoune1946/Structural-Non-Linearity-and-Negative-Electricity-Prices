# Structural Non-Linearity and Negative Electricity Prices

**Research project | European wholesale electricity markets**

This repository contains code and notebooks for investigating structural nonlinearities in wholesale electricity prices, with a focus on negative-price episodes and cross-country empirical analysis.

The work is motivated by the growing variability of electricity prices in markets with increasing renewable penetration, limited flexibility and changing supply-demand conditions.

## Research questions

- How do electricity prices behave across different market conditions?
- Are negative-price episodes associated with distinct nonlinear dynamics?
- How robust are the empirical findings across European markets?
- How can statistical models provide interpretable insights into price formation?

## Empirical scope

The notebooks currently target the following market areas:

- France
- Germany / Luxembourg
- Spain

The analyses use Day-Ahead market data obtained through the ENTSO-E Transparency Platform. Data acquisition and local caching are handled by the notebooks/scripts.

## Reproducibility

### Requirements

Python 3.9 or later. The original environment uses packages including:

`numpy`, `pandas`, `scipy`, `scikit-learn`, `xgboost`, `hmmlearn`, `matplotlib`, `entsoe-py`, `requests`, `holidays`, `joblib`, and `tzdata`.

Install dependencies:

```bash
pip install numpy pandas scipy scikit-learn xgboost hmmlearn matplotlib entsoe-py requests holidays joblib tzdata
```

### Data access

1. Obtain an API token from the [ENTSO-E Transparency Platform](https://transparency.entsoe.eu/).
2. Set the token as an environment variable (do not commit credentials):

```bash
export ENTSOE_TOKEN="your_token"
```

On Windows PowerShell:

```powershell
$env:ENTSOE_TOKEN = "your_token"
```

3. Run the notebooks in the intended order:

- `01_France.ipynb`
- `03_Allemagne_DE_LU.ipynb`
- `04_Espagne_ES.ipynb`

The first execution retrieves data; subsequent runs can use locally cached files, depending on the notebook configuration.

## Data and responsible release

Market data are retrieved from ENTSO-E. Check the relevant platform terms before redistributing downloaded data. Do not commit API tokens, private datasets or confidential company information.

## Limitations and status

This is an ongoing research repository. Notebooks and results may evolve as the methodology and data checks are refined. The repository should not be interpreted as a published paper or a production forecasting system unless a specific release states otherwise.

## Author

**Anoune Mergane** — PhD researcher in applied mathematics (CIFRE), working on stochastic modelling, statistical inference and electricity-market applications.

[GitHub profile](https://github.com/Anoune1946)
