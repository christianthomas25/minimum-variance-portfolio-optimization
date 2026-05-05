# Minimum Variance Portfolio Optimization

This project constructs and evaluates an optimized portfolio across four ETFs:

- ACWI — global equities
- AGG — US aggregate bonds
- GLD — gold
- BSV — short-term bonds

The objective is to build a portfolio using only information available before the start of 2023 and evaluate its out-of-sample performance during the full calendar year 2023.

## Methodology

The selected portfolio uses:

- Daily adjusted closing prices from Yahoo Finance
- Training period: 2019-01-01 to 2022-12-28
- Test period: 2023-01-01 to 2023-12-31
- Ledoit-Wolf covariance shrinkage
- Long-only minimum variance optimization
- 40% maximum allocation per ETF
- No rebalancing during 2023
- Risk-free rate assumed to be 0%

The benchmark is an equal-weight Permanent Portfolio with 25% allocated to each ETF.

## Final Portfolio

| Asset | Weight |
|---|---:|
| ACWI | 7.70% |
| AGG | 40.00% |
| GLD | 12.30% |
| BSV | 40.00% |

## 2023 Out-of-Sample Results

| Metric | Minimum Variance 40% Cap | Benchmark |
|---|---:|---:|
| Annual Return | 7.49% | 11.18% |
| Annual Volatility | 5.62% | 6.56% |
| Sharpe Ratio | 1.3324 | 1.7025 |
| Cumulative Return | 7.55% | 11.49% |
| Max Drawdown | -4.63% | -5.54% |

The minimum variance portfolio underperformed the benchmark in return and Sharpe ratio because 2023 was a strong equity year and the optimized portfolio held a relatively low allocation to ACWI. However, the portfolio achieved lower volatility and a smaller maximum drawdown, consistent with the objective of minimum variance optimization.

## Key Takeaways

- Maximum Sharpe optimization is highly sensitive to expected return assumptions.
- Minimum variance optimization avoids direct expected-return forecasting.
- Ledoit-Wolf shrinkage provides a more stable covariance estimate than the raw sample covariance matrix.
- A 40% allocation cap prevents excessive concentration in a single low-volatility asset.
- One year of out-of-sample data is insufficient to draw conclusions about long-run strategy superiority.

## Repository Structure

```
.
├── README.md
├── portfolio_opt_github_MTC.ipynb
├── requirements.txt
├── weights_submission_template.csv
├── report/
│   └── portfolio_opt_report_MTC.pdf
├── outputs/
│   └── figures/
└── data/
```

## Files

- `portfolio_opt_github_MTC.ipynb` — main notebook
- `report/portfolio_opt_report_MTC.pdf` — project report
- `weights_submission_template.csv` — example CSV submission format
- `requirements.txt` — Python dependencies

## Disclaimer

This project is for academic and educational purposes only. It does not constitute investment advice or a recommendation to buy or sell any security.
