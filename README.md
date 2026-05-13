# Medicaid Expansion Causal Impact Study

## Overview
Difference-in-Differences (DiD) analysis estimating the causal effect of the 2014 
Affordable Care Act Medicaid expansion on state-level uninsured rates across 50 states. 
Data sourced from the County Health Rankings (CHR) Trends dataset. The analysis applies 
a rigorous validation framework, including an event study, a placebo test, and robustness 
heck to support the causal interpretation.

## What I Did
- Constructed a 50-state panel dataset from CHR Trends data, aggregating county-level 
  uninsured counts to state-year uninsured rates from 2010 to 2022
- Defined treatment as states that expanded Medicaid by January 1, 2014, based on 
  Kaiser Family Foundation (KFF) expansion status
- Fit a DiD model with state and year fixed effects using TWFE estimation, clustering 
  standard errors at the state level
- Estimated approximately a 1.1 percentage point reduction in uninsured rates among 
  expansion states relative to non-expansion states
- Verified the parallel trends assumption using an event study with 2013 as the 
  reference year, confirming pre-2014 coefficients were near zero
- Conducted a placebo test using a fake 2012 policy date, which produced no 
  significant effect, supporting the causal interpretation
- Ran a robustness check restricting to a tighter 2011-2017 window, where the 
  estimated reduction strengthened to approximately 1.2 percentage points

## Tools & Methods
R, R Markdown, fixest, ggplot2, dplyr, Difference-in-Differences, Two-Way Fixed 
Effects (TWFE), Event Study, Placebo Test, Clustered Standard Errors

## Files
- `medicaid_did.Rmd` - Full analysis code
- `medicaid_did.html` - Knitted output with results and visualizations
