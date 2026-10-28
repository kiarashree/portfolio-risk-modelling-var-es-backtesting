
# Portfolio Risk Modelling & Analysis

### Value at Risk | Expected Shortfall | Monte Carlo Simulation | Backtesting

**Academic Group Project | MSc Financial Data Science | UCD Michael Smurfit Graduate Business School | April 2026**

## 1. Business Problem

Financial institutions must estimate potential portfolio losses accurately to support capital allocation and risk governance. However, traditional risk models can underestimate extreme losses when financial returns deviate from normality.

**Core question:** Which risk measurement approaches are most appropriate for equity, bond and diversified portfolios, and how reliably do they perform under backtesting?

## 2. Analytical Process

The group investigated three hypothetical $1 million portfolios: an equally weighted equity portfolio comprising 30 Dow Jones Industrial Average constituents, a bond portfolio represented by the Bloomberg Aggregate Bond Index, and a combined portfolio with 60% equity and 40% bonds.

The analysis used 1,000 aligned trading days of Bloomberg-sourced observations from March 2022 to March 2026.

The methodology included:
- Portfolio construction and log-return analysis
- Parametric, Cornish-Fisher, Historical Simulation and Monte Carlo VaR and Expected Shortfall
- Exponential Spectral Risk Measurement
- Volatility, maximum drawdown and distributional diagnostics
- Rolling-window out-of-sample backtesting using Kupiec and Christoffersen tests
- Model comparison and sensitivity analysis at 95% and 99% confidence levels

## 3. Solution and Recommendations

A single risk model was not appropriate for every portfolio. The study recommended:

| Portfolio | Primary recommended risk measure | Supporting approach |
| --- | --- | --- |
| Equity | Historical Expected Shortfall | Cornish-Fisher VaR for breach monitoring |
| Bond | Parametric Expected Shortfall | Parametric VaR for validation |
| Combined 60/40 | Historical Expected Shortfall | Historical VaR for backtesting |

## 4. Key Results

- At 99% confidence, equity Historical VaR was approximately $28,166, compared with Parametric VaR of $21,964, a difference of approximately 28.24%.
- The combined portfolio's Historical Expected Shortfall was approximately $23,826, compared with approximately $37,161 for the equity-only portfolio.
- Parametric and Monte Carlo models recorded 11 VaR breaches out of 499 equity backtesting observations at 99% confidence, compared with an expected breach rate of 1%.
- Cornish-Fisher VaR passed all reported 99% equity VaR backtesting criteria but performed less reliably at 95% confidence.
- Model selection depended on portfolio characteristics, tail behaviour and confidence level.

## 5. Tools and Methods

**Programming:** Python, Jupyter Notebook

**Financial analytics:** Portfolio Risk Management, VaR, Expected Shortfall, Monte Carlo Simulation, Historical Simulation, Cornish-Fisher Expansion, Spectral Risk Measures

**Validation:** Rolling Backtesting, Kupiec Test, Christoffersen Test, Sensitivity Analysis

**Data source:** Bloomberg Terminal (subject to data licensing and redistribution restrictions)

## 6. Project Team and Contributions

This was a five-person academic group project completed for FIN41360 Portfolio & Risk Management at University College Dublin.

**Team:** Colm O'Sullivan, Hugh O'Hara, David Delaney, Kiara Shree and Aryaman Taneja.

**My contribution — Kiara Shree:** Report writing, analytical interpretation and editing, contributing to the presentation and communication of the group's risk modelling methodology, results and recommendations.

The coding for Parts 1 and 2 was attributed to Colm O'Sullivan and Hugh O'Hara respectively in the original submission. This repository documents collaborative group work rather than claiming sole authorship of the code.

## 7. Reproducibility and Data Access

The original study used Bloomberg-sourced financial data. Raw data are not distributed publicly without appropriate permission. Reproducing the numerical results requires access to the underlying licensed dataset and the dependencies used in the notebook.

## 8. Disclaimer

This repository presents academic research for educational and portfolio demonstration purposes. It is not investment advice.
  
