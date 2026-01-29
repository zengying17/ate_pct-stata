# ate_pct (Stata)

Stata command **`ate_pct`** computes average treatment effects (ATEs) in **percentage points** under subgroup heterogeneity, as developed in:

> Ying Zeng, *“Estimation and Inference on Average Treatment Effect in Percentage Points under Heterogeneity”*.

The command is a post-estimation tool: run a regression model first, then call `ate_pct` using subgroup indicators.

## Contents

- `ate_pct.ado` — Stata command
- `ate_pct.sthlp` — help file
- `ate_pct_example.dta` — example dataset

## Installation

### Option A: Install from GitHub (copy files)
1. Download or clone this repository.
2. Put `ate_pct.ado` and `ate_pct.sthlp` in a folder on your Stata ado-path (e.g. a personal ado folder).
3. In Stata, you can check your ado-path via:
   ```stata
   adopath
   ```

### Option B: Use directly from a local folder
In Stata:
```stata
cd "/path/to/ate_pct-stata"
```
Stata will find `ate_pct.ado` in the current directory when you run `ate_pct`.

## Quick start

Open Stata and run:
```stata
cd "/path/to/ate_pct-stata"
use "ate_pct_example.dta", clear

* Example regression (adjust as needed)
reg lny x gr1 gr2 gr3

* Post-estimation: group indicators must match those in the regression
ate_pct gr1 gr2 gr3
return list
```

See `help ate_pct` for full syntax and options.

## Notes on sampling and variance output

- The `if` qualifier can further restrict the sample used to compute subgroup weights/shares, but coefficients and the variance–covariance matrix are always taken from the preceding estimation (i.e., from `e(b)` and `e(V)` on `e(sample)`).
- `r(V)` is a 3×3 **diagonal** variance matrix corresponding to `r(b)`; off-diagonal covariances are ignored and set to 0 by design.

## Citation

If you use this code in academic work, please cite the paper below:

- Zeng, Ying. *Estimation and Inference on Average Treatment Effect in Percentage Points under Heterogeneity.*

## Contact

Ying Zeng  
School of Economics and Wang Yanan Institute for Studies in Economics (WISE)

Email: zengying17@gmail.com

## Related repository

R implementation: [ate_pct-r](https://github.com/zengying17/ate_pct-r)

