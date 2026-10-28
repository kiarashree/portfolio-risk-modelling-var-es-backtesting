
# Portfolio Risk Modelling — Results & Insights

## Executive Summary

This group project investigated whether conventional risk
models adequately capture extreme losses across equity,
bond and diversified investment portfolios.

The analysis found that model accuracy depends on the
underlying return distribution and portfolio composition.

## 1. Portfolio Risk Comparison

The analysis evaluated three hypothetical portfolios,
each with a starting value of $1,000,000.

| Risk Metric | Equity | Bonds | 60/40 Portfolio |
|---|---:|---:|---:|
| Historical VaR (99%) | $28,166 | $9,287 | $17,691 |
| Historical ES (99%) | $37,161 | $11,415 | $23,826 |
| Annualised Volatility | 15.17% | 6.20% | 9.92% |
| Maximum Drawdown | -22.21% | -11.58% | -17.13% |

### Business Insight

Diversification reduced overall volatility and
estimated tail losses, but did not eliminate
exposure to extreme market events.

## 2. Model Risk — Parametric vs Historical VaR

| Portfolio | Parametric VaR (99%) | Historical VaR (99%) |
|---|---:|---:|
| Equity | $21,964 | $28,166 |
| Bonds | $9,018 | $9,287 |
| Combined | $14,346 | $17,691 |

### Business Insight

For the equity portfolio, Historical VaR exceeded
Parametric VaR by approximately 28.24%.

This demonstrates how normal-distribution assumptions
can underestimate empirical tail-risk estimates.

## 3. Backtesting Performance

At the 99% confidence level, the study evaluated
499 out-of-sample observations per portfolio.

Key findings:

- Equity Parametric VaR: 11 breaches
- Equity Monte Carlo VaR: 11 breaches
- Equity Cornish-Fisher VaR: 7 breaches
- Equity Historical VaR: 10 breaches

Cornish-Fisher VaR passed the reported equity
backtesting criteria at 99% confidence.

However, its performance deteriorated at 95%,
highlighting sensitivity to model assumptions.

## 4. Recommended Risk Management Approach

| Portfolio | Recommended Primary Metric |
|---|---|
| Equity | Historical Expected Shortfall |
| Bonds | Parametric Expected Shortfall |
| Combined 60/40 | Historical Expected Shortfall |

## 5. Final Business Recommendation

Financial institutions should avoid applying
a single risk methodology uniformly across
portfolios.

Risk model selection should account for:

- Return distribution characteristics
- Skewness and kurtosis
- Extreme-loss behaviour
- Portfolio diversification
- Backtesting performance
- Confidence-level sensitivity

Expected Shortfall should be prioritised when
assessing the severity of potential tail losses.

---

**Project:** FIN41360 Portfolio & Risk Management

**Institution:** UCD Michael Smurfit Graduate Business School

**Project Type:** Five-member academic group project

**Note:** Figures are based on the group's original
research report and are presented for educational purposes.
