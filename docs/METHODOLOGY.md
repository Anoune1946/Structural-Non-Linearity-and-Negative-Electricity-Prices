# Methodology notes

## Research question

The project investigates whether nonlinear price dynamics help describe wholesale Day-Ahead electricity prices across different market conditions, especially when the system experiences surplus conditions and negative prices.

## Model families

The country notebooks compare smooth-transition specifications:

- an exponential transition specification;
- a logistic smooth-transition specification (LSTAR-type).

The transition variable is constructed from a balance of supply-demand fundamentals. Selected physical variables are first predicted from lagged information and calendar covariates, and the resulting fitted components enter the transition-variable construction. This is an empirical modelling step; it should not automatically be interpreted as a valid causal instrument.

Lagged prices enter at multiple horizons. The precise lag definitions and information set are implemented in each notebook and must be read together with the target timestamp and the assumed Day-Ahead forecast cut-off.

## Estimation and evaluation

The country notebooks define their own estimation, validation and test windows. They estimate the nonlinear specifications, compute diagnostic and event-frequency summaries, and export result objects. Bootstrap settings are configured in the notebooks.

For a defensible empirical comparison, report at least:

- the market, timezone, sample period and temporal frequency;
- the exact event definition (strictly negative prices versus non-positive prices);
- the date-based train / validation / test split;
- the information available at the assumed forecast time;
- data coverage, missing-data treatment and price cleaning;
- benchmark forecasts and evaluation metrics;
- bootstrap replication count, convergence rate and uncertainty summaries where relevant.

## Interpretation

Estimated transition thresholds are descriptive model features unless an appropriate identification strategy supports a causal interpretation. Cross-market comparisons should account for differences in market design, data coverage, units, timezone conventions and the availability of physical forecasts.
