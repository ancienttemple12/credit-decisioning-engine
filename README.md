# Credit Decisioning Engine (PD + Pricing + Limit Assignment)

End-to-end credit decisioning project using LendingClub-style loan performance data.

## What this repo does
- Builds a leakage-safe Probability of Default (PD) model using origination features
- Applies underwriting rules and generates decline reason codes
- Assigns APR tiers (risk-based pricing)
- Recommends an approved amount (limit/amount assignment)
- Backtests acceptance rate vs bad rate vs expected profit

## Setup
```bash
pip install -r requirements.txt
