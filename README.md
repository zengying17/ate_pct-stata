# ate_pct (Stata)

Stata command **`ate_pct`** computes average treatment effects (ATEs) in **percentage points** under subgroup heterogeneity, as developed in:

> Ying Zeng, *“Estimation and Inference on Average Treatment Effect in Percentage Points under Heterogeneity”*.

The command is a post-estimation tool: run a regression model first, then call `ate_pct` using subgroup indicators.

## Contents

- `ate_pct.ado` — Stata command
- `ate_pct.sthlp` — help file
- `ate_pct_example.dta` — example dataset
- `example.do` — example do file illustrating the command using ate_pct_example.dta

## Installation
### Option A: Installation from SSC
In Stata, run:
```
ssc install ate_pct
```

### Option B: Installation from Github
In Stata, run:
```stata
net install ate_pct, from("https://raw.githubusercontent.com/zengying17/ate_pct-stata/main/") replace
```

## Quick start

Open Stata and run:
```stata
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

