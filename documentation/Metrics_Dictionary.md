# Operations Metrics Dictionary

**Project:**  Payments Operations Intelligence  
**Author:** Fadwa Hassan  
**Date:** May 2026  
**Version:** 1.0

## Core KPIs

| Metric Name               | Formula                                    | Description                                     | Data Source    | Refresh Frequency | Limitations                |
| ------------------------- | ------------------------------------------ | ----------------------------------------------- | -------------- | ----------------- | -------------------------- |
| Acceptance Rate           | Successful Tx / Total Tx                   | % of transactions that succeed                  | Transactions   | Daily             | -                          |
| Chargeback / Fraud Rate   | Fraud Tx / Total Tx                        | Risk indicator (should be < 0.5%)               | Transactions   | Daily             | Delayed reporting possible |
| Total Transaction Volume  | SUM(amount)                                | Total money processed                           | Transactions   | Daily             | -                          |
| Avg Transaction Amount    | AVG(amount)                                | Average size of transaction                     | Transactions   | Daily             | -                          |
| Active Merchants          | Merchants with ≥1 tx in last 30 days       | How many merchants are still using the platform | Merchant Stats | Daily             | Definition can vary        |
| Merchant Cohort Retention | % of cohort still transacting after N days | Long-term merchant survival                     | Cohort Table   | Monthly           | -                          |
| New Merchants per Day     | Count of first-time merchants              | Onboarding performance                          | Cohort Table   | Daily             | -                          |

## Segmentation Logic

- **Active Merchant**: At least 1 successful transaction in last 30 days
- **High Value Merchant**: Total volume > 75th percentile
- **Cohort**: Grouped by first transaction day (cohort_day)
