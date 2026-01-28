# ate_pct (Stata)

Stata command **`ate_pct`** computes average treatment effects (ATEs) in **percentage points** under subgroup heterogeneity, as developed in:

> Ying Zeng, *“Estimation and Inference on Average Treatment Effect in Percentage Points”*.

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
