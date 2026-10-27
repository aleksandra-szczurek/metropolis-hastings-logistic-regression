# Metropolis-Hastings Algorithm for Bayesian Logistic Regression

**Group project** – Bayesian Computing Methods, University of Perugia (Feb–Jun 2026)

## Problem

The posterior distribution of a logistic regression has **no closed form**, so it cannot be sampled directly. This project implements a **Metropolis-Hastings MCMC algorithm from scratch** in R to approximate it.

## What was done

- Reusable MH sampler with a symmetric multivariate Normal proposal (20,000 iterations, 25% burn-in)
- **Proposal tuning:** with k = 50 the acceptance rate was too high and mixing poor; with k = 4 the acceptance rate moved into the optimal 0.2–0.3 range and the **ESS rose above 1,000** for all parameters
- **Robustness:** chains started from the prior and from an extreme point (5, 5, 5) converge to the same posterior
- **Sample size:** with n = 550 instead of 100, estimates move much closer to the true values
- **Diagnostics:** trace plots, autocorrelation functions, effective sample size and R/ESS ratios

## Contents

- `metropolis_hastings_logistic.qmd` – fully reproducible Quarto document (simulated data, no external files needed)

## Tools

R · Quarto · mvtnorm · LaplacesDemon
