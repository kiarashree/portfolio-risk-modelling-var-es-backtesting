
# Portfolio Risk Modelling & Analysis
### Value at Risk | Expected Shortfall | Monte Carlo Simulation | Statistical Backtesting

**MSc Financial Data Science | UCD Michael Smurfit Graduate Business School | April 2026**

**Project Type:** Academic Group Project (5 members)  
**Domain:** Quantitative Finance | Financial Risk Analytics | Portfolio Risk Management  
**Tools:** Python, Jupyter Notebook, Bloomberg Terminal, Excel, Statistical Modelling

---

## 1. Business Problem

Financial institutions must accurately quantify potential portfolio losses to support capital allocation, regulatory reporting and investment risk management.

However, traditional risk measurement techniques often rely on normal-distribution assumptions that may underestimate extreme market losses.

This creates significant challenges for financial institutions when assessing risk during periods of heightened volatility, financial stress and unexpected market shocks.

### Key Research Questions

- How accurately do different risk models estimate potential portfolio losses?
- Do traditional parametric models adequately capture extreme downside risk?
- How does diversification affect risk in equity and fixed-income portfolios?
- Which models provide the most reliable out-of-sample risk forecasts?
- How should financial institutions select appropriate risk measures for different portfolio characteristics?

**Objective:** Evaluate alternative financial risk modelling methodologies and recommend suitable approaches for measuring and monitoring portfolio-level downside risk.

---

## 2. Data & Portfolio Construction

The analysis used Bloomberg-sourced financial market data covering March 2022 to March 2026.

### Dataset Overview

| Component | Description |
|---|---|
| Data Source | Bloomberg Terminal |
| Observation Period | 28 March 2022 – 27 March 2026 |
| Sample Size | 1,000 aligned trading days |
| Equity Universe | 30 Dow Jones Industrial Average constituents |
| Fixed Income Proxy | Bloomberg Aggregate Bond Index (LBUSTRUU) |
| Initial Portfolio Value | $1,000,000 per portfolio |
| Confidence Levels | 95% and 99% |

### Portfolio Construction

Three hypothetical investment portfolios were evaluated:

1. **Equity Portfolio:** Equally weighted allocation across 30 DJIA constituents.
2. **Bond Portfolio:** Fixed-income exposure represented by the Bloomberg Aggregate Bond Index.
3. **Combined Portfolio:** Traditional 60% equity / 40% bond allocation.

Daily logarithmic returns were calculated and aligned across equity and bond trading calendars.

The analysis examined return distributions, skewness, kurtosis, volatility clustering and extreme market movements.

---

## 3. Analytical Process & Methodology

The project followed a structured quantitative risk assessment framework.

### Phase 1 - Data Preparation & Exploratory Analysis

- Processed and aligned historical equity and bond observations.
- Calculated daily logarithmic returns.
- Constructed equally weighted equity and diversified portfolios.
- Analysed return distributions and descriptive statistics.
- Examined normality assumptions using return distributions and Q-Q plots.
- Identified fat tails, excess kurtosis and volatility clustering.

### Phase 2 - Risk Model Development

Four primary methodologies were evaluated for Value at Risk (VaR) and Expected Shortfall (ES).

#### 1. Parametric VaR & Expected Shortfall

Estimated potential losses under normal-distribution assumptions using historical mean returns and volatility.

Purpose:
- Establish a conventional risk measurement benchmark.
- Assess the reliability of Gaussian assumptions.
- Compare model estimates against empirical loss distributions.

#### 2. Cornish-Fisher VaR & Expected Shortfall

Applied skewness and kurtosis adjustments to account for deviations from normality.

Purpose:
- Capture distributional asymmetry and fat-tail behaviour.
- Investigate the impact of higher-order statistical moments.
- Evaluate limitations under extreme kurtosis.

#### 3. Historical Simulation VaR & Expected Shortfall

Estimated portfolio losses directly from historical return observations without imposing a predefined return distribution.

Purpose:
- Capture observed extreme market outcomes.
- Reduce dependence on normality assumptions.
- Evaluate empirical downside risk.

#### 4. Monte Carlo Simulation

Generated 100,000 simulated return scenarios using the estimated equity-bond covariance structure.

Purpose:
- Estimate potential portfolio loss distributions.
- Preserve observed equity-bond correlation.
- Compare simulation-based estimates against parametric benchmarks.

### Phase 3 - Additional Risk Measures

The analysis also included:

- Exponential Spectral Risk Measure
- Daily and annualised portfolio volatility
- Maximum drawdown
- Risk-aversion sensitivity analysis
- Portfolio-level risk comparisons

### Phase 4 - Rolling-Window Backtesting

A rolling estimation framework generated one-day-ahead VaR and ES forecasts.

The backtesting period covered April 2024 to March 2026, with 499 out-of-sample observations per portfolio.

Model reliability was evaluated using:

**Kupiec Unconditional Coverage Test**
- Assessed whether observed VaR breaches were consistent with expected exceedance rates.

**Christoffersen Independence Test**
- Examined whether VaR breaches occurred independently or clustered during market stress.

**Conditional Coverage Test**
- Combined breach-frequency and independence evaluations.

**Expected Shortfall Evaluation**
- Compared forecast ES against realised tail losses.
- Examined prediction bias and mean squared error.

### Phase 5 - Sensitivity & Model Comparison

Risk estimates were evaluated at both 95% and 99% confidence levels.

The analysis compared:
- Distributional assumptions
- Risk forecast accuracy
- VaR exceedance frequencies
- Tail-loss estimation bias
- Volatility sensitivity
- Portfolio diversification effects

---

## 4. Results & Key Findings

### Portfolio Risk Comparison

All values below represent one-day risk estimates for hypothetical $1,000,000 portfolios.

| Risk Metric | Equity | Bonds | Combined 60/40 |
|---|---:|---:|---:|
| Parametric VaR (99%) | $21,964 | $9,018 | $14,346 |
| Historical VaR (99%) | $28,166 | $9,287 | $17,691 |
| Historical ES (99%) | $37,161 | $11,415 | $23,826 |
| Annualised Volatility | 15.17% | 6.20% | 9.92% |
| Maximum Drawdown | -22.21% | -11.58% | -17.13% |

### Finding 1 - Traditional Risk Models Underestimated Equity Tail Risk

For the equity portfolio:

- Parametric VaR (99%): $21,964
- Historical VaR (99%): $28,166
- Difference: $6,202

Historical VaR exceeded Parametric VaR by approximately **28.24%**.

**Business Implication:** Reliance on normal-distribution-based risk estimates may materially understate potential equity losses during extreme market conditions.

### Finding 2 - Diversification Reduced Risk but Did Not Eliminate Tail Exposure

The combined 60/40 portfolio demonstrated lower risk than the standalone equity portfolio.

- Equity Historical ES: $37,161
- Combined Historical ES: $23,826
- Reduction: Approximately 36%

However, simultaneous equity and bond losses during the 2022 market stress period demonstrated that diversification benefits can weaken during adverse market conditions.

**Business Implication:** Portfolio diversification must be evaluated using extreme-loss measures alongside conventional volatility metrics.

### Finding 3 - Model Performance Varied Across Confidence Levels

At 99% confidence, the equity portfolio recorded:

| Risk Model | VaR Breaches | Observations |
|---|---:|---:|
| Parametric | 11 | 499 |
| Cornish-Fisher | 7 | 499 |
| Historical Simulation | 10 | 499 |
| Monte Carlo | 11 | 499 |

Cornish-Fisher VaR passed all reported 99% equity VaR backtesting tests.

However, its performance deteriorated at 95% confidence, demonstrating sensitivity to distributional assumptions and higher-order moments.

**Business Implication:** A model performing well under one confidence level may not remain reliable under another.

### Finding 4 - Model Selection Should Reflect Portfolio Characteristics

The analysis found that no single risk methodology was consistently optimal across all portfolios.

Equity portfolios were more sensitive to fat tails and extreme market movements, while bond portfolio risk estimates exhibited greater convergence across modelling approaches.

**Business Implication:** Financial institutions should adopt portfolio-specific risk measurement and validation strategies.

---

## 5. Solution & Risk Management Recommendations

Based on the empirical analysis and rolling backtesting results, the group recommended the following:

| Portfolio | Primary Risk Measure | Supporting Method |
|---|---|---|
| Equity | Historical Expected Shortfall | Cornish-Fisher VaR |
| Bonds | Parametric Expected Shortfall | Parametric VaR |
| Combined 60/40 | Historical Expected Shortfall | Historical VaR |

### Strategic Recommendations

1. Prioritise Expected Shortfall when assessing the severity of extreme portfolio losses.
2. Use historical risk measures where financial returns exhibit significant deviations from normality.
3. Validate models through ongoing backtesting instead of relying solely on theoretical assumptions.
4. Assess confidence-level sensitivity before selecting risk measurement frameworks.
5. Evaluate portfolio diversification using both volatility and tail-risk measures.

### Overall Conclusion

The study demonstrated that financial risk modelling requires more than estimating potential losses.

Reliable portfolio risk management depends on selecting appropriate methodologies, understanding distributional assumptions and validating model performance against realised market outcomes.

---

## 6. Technical Skills & Methods

**Programming & Data Analysis**
- Python
- Jupyter Notebook
- NumPy
- Pandas
- Financial Data Processing
- Data Visualisation

**Quantitative Finance**
- Portfolio Risk Management
- Value at Risk (VaR)
- Expected Shortfall (ES)
- Monte Carlo Simulation
- Historical Simulation
- Cornish-Fisher Expansion
- Spectral Risk Measures
- Maximum Drawdown

**Statistical Analysis & Model Validation**
- Rolling-Window Backtesting
- Kupiec Unconditional Coverage Test
- Christoffersen Independence Test
- Conditional Coverage Testing
- Sensitivity Analysis
- Distributional Diagnostics
- Model Comparison and Results Verification

**Business & Risk Reporting**
- Analytical Interpretation
- Financial Risk Reporting
- Model Review
- Quality Assurance
- Technical Documentation
- Risk Management Recommendations

---

## 7. My Contributions - Kiara Shree

**Role: Risk Analysis, Code Review, Results Validation & Technical Reporting**

This project was completed collaboratively as part of a five-member MSc Financial Data Science group.

My contributions included:

**Code Review & Methodology Verification**
- Reviewed the Python modelling implementation and checked its alignment with the intended financial risk methodologies.
- Examined the analytical workflow and modelling assumptions used in portfolio risk estimation.

**Results Validation & Quality Assurance**
- Reviewed VaR, Expected Shortfall and backtesting outputs for consistency.
- Checked the alignment between reported numerical findings, visualisations and conclusions.
- Examined differences between modelling approaches to support the interpretation of their results.

**Analytical Interpretation**
- Contributed to interpreting the implications of model assumptions, portfolio diversification and extreme-loss behaviour.
- Supported the communication of findings and portfolio-specific model recommendations.

**Financial Risk Reporting**
- Contributed to drafting, reviewing and editing the research report.
- Helped communicate technical findings in a structured format for a financial risk management audience.

**Note:** The original Part 1 and Part 2 Python implementations were credited to the designated coding contributors. My contributions focused on code review, results verification, analytical interpretation and reporting.

---

## 8. Group Project Attribution

**University:** University College Dublin

**School:** Michael Smurfit Graduate Business School

**Programme:** MSc Financial Data Science

**Module:** FIN41360 - Portfolio & Risk Management

**Project:** Group Assignment 2 - Risk Modelling & Analysis

**Submission:** April 2026

### Group Members

| Contributor | Original Reported Contribution |
|---|---|
| Colm O'Sullivan | Part 1 coding and report writing |
| Hugh O'Hara | Part 2 coding and report writing |
| David Delaney | Report writing and editing |
| Kiara Shree | Report writing and editing; additionally reviewed code and results |
| Aryaman Taneja | Report writing and editing |

This repository presents the group's collaborative academic research. Individual contributions are identified to preserve accurate attribution.

---

## 9. Repository Structure

```text
portfolio-risk-modelling-var-es-backtesting/
|
|-- README.md
|-- RESULTS.md
|-- requirements.txt
|
|-- data/
|   |-- README.md
|   |-- COS PARM.xlsx
|
|-- notebooks/
|   |-- README.md
|   |-- PARM_Assignment2_Parts1and2 V4 (1).ipynb
|
|-- reports/
    |-- README.md
    |-- Project Report.pdf
```

---

## 10. Project Navigation

| Resource | Description |
|---|---|
| [Python Risk Modelling Notebook](notebooks/) | Quantitative modelling, simulation and backtesting |
| [Financial Market Dataset](data/) | Equity and bond market data |
| [Research Report](reports/) | Detailed methodology, results and recommendations |
| [Results & Insights](RESULTS.md) | Executive summary and business implications |

---

## 11. Reproducibility

The original analysis uses Bloomberg-sourced market data and was developed in Python/Jupyter Notebook.

To run the project locally:

1. Clone or download this repository.
2. Install the dependencies listed in `requirements.txt`.
3. Open the Jupyter Notebook in the `notebooks` directory.
4. Ensure the dataset is available in the `data` directory.
5. Execute the analysis cells in sequence.

**Note:** The original dataset is shared with the stated permission. Results reflect the historical sample and assumptions documented in the group report. Successful execution in a fresh environment has not yet been independently verified.

---

## 12. Disclaimer

This repository documents academic research completed for the MSc Financial Data Science programme at UCD Michael Smurfit Graduate Business School.

It is intended for educational, research and professional portfolio demonstration purposes.

The analysis and recommendations do not constitute investment advice.
