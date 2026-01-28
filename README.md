## Project Overview

This project implements an end-to-end credit decisioning engine using
LendingClub-style consumer loan data. The objective is to demonstrate how
predicted default risk can be translated into practical lending decisions,
rather than focusing solely on model accuracy.

The workflow mirrors a real-world consumer lending setup. A leakage-safe
Probability of Default (PD) model is trained using origination-time features
only and evaluated using standard credit risk metrics. The resulting PD scores
are then mapped into risk bands and used to drive approval decisions,
risk-based pricing, and credit limit assignment under an explicit risk
appetite.

Decisions are evaluated counterfactually against observed loan outcomes to
highlight the trade-offs inherent in credit risk management. The project
intentionally prioritises transparency and interpretability, reflecting how
baseline models and policy frameworks are commonly deployed in production
credit environments.

### Key components
- **PD modelling** using logistic regression and time-based train/test splits
- **Risk banding** via quantile-based bucketing for stable policy evaluation
- **Approval logic** based on configurable PD thresholds
- **Risk-based pricing** and **approved amount assignment**
- **Portfolio-level evaluation** using observed default outcomes

This repository is designed as a practical demonstration of credit
decisioning concepts rather than a production system, and provides a
foundation that could be extended with expected loss, profitability, or
borrower take-up modelling.

## Repository walkthrough

The project is organised as a sequence of notebooks that mirror a typical
credit decisioning workflow:

1. **`01_build_target_and_clean.ipynb`**  
   Data cleaning, target definition, and feature preparation using
   origination-time information only.

2. **`02_train_pd_model.ipynb`**  
   Training and evaluation of a leakage-safe Probability of Default (PD)
   model using a time-based train/test split. Model performance is assessed
   using AUC and KS.

3. **`03_credit_decisioning_engine.ipynb`**  
   Translation of PD scores into lending decisions via risk banding,
   approval rules, risk-based pricing, and credit limit assignment.
   Portfolio-level outcomes are evaluated against observed defaults.

Readers are encouraged to start with Notebook 03 for a high-level view of
the decisioning logic, and refer to Notebooks 01 and 02 for modelling and
data preparation details.
- [Notebook 01 – Data prep](notebooks/01_build_target_and_clean.ipynb)
- [Notebook 02 – PD model](notebooks/02_train_pd_model.ipynb)
- [Notebook 03 – Decisioning engine](notebooks/03_credit_decisioning_engine.ipynb)




## Setup
```bash
pip install -r requirements.txt
