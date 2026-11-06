# OLS Diagnostics: When the Standard Error Is Lying

## Objective
I tested when classical OLS standard errors misstate uncertainty, and checked whether residual plots, formal tests, influence measures, and heteroskedasticity-robust (HC3) standard errors catch the problem.

## Methodology
- Simulated data with errors whose spread grows with x, then fitted one regression and computed both classical and HC3 standard errors for the slope.
- Ran 400 simulated samples and recorded how often the classical and robust 95% confidence intervals covered the true slope, with Monte Carlo standard errors for each coverage rate.
- Read four residual plots alongside the Breusch-Pagan test (heteroskedasticity) and the Jarque-Bera test (normality of residuals).
- Deleted one row out of 600 and measured how far the slope moved, in units of its own standard error, and how much the standard error changed.
- Fitted a regression on the California Housing dataset and compared the HC3 and classical standard errors on AveRooms.
- Wrote a function, `hc3_se()`, to compute HC3 standard errors directly, and used it on AveRooms with all districts and again after removing the 965 districts at the 5.0 price ceiling.
- *(Extension)* Computed Cook's distance for every district and measured the share carried by the top five.
- *(Challenge)* Built a regression that passed every diagnostic but was still wrong.

## Key Findings
- **Same slope, different uncertainty:** On the simulated data, both methods gave a slope of [YOUR VALUE]. The classical standard error was [YOUR VALUE] and the HC3 standard error was [YOUR VALUE].
- **Coverage:** Across 400 samples, the classical 95% interval covered the true slope in [YOUR VALUE] of them, and the robust interval in [YOUR VALUE] (Monte Carlo standard errors: [YOUR VALUE] and [YOUR VALUE]).
- **One row out of 600:** Deleting a single row moved the slope by [YOUR VALUE] of its own standard error, and the standard error fell by [YOUR VALUE].
- **California Housing:** The HC3 standard error on AveRooms was [YOUR VALUE] times the classical one.
- **Price ceiling:** Using `hc3_se()`, the HC3 standard error on AveRooms was [YOUR VALUE] with all districts and [YOUR VALUE] without the 965 districts at the 5.0 ceiling.
- *(Extension)* Five districts carried [YOUR VALUE] of the total Cook's distance.
- *(Challenge)* [YOUR RESULT]
