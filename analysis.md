# 📊 Analysis of DeFi Wallet Credit Scores

This document presents a detailed behavioral analysis of wallets based on the credit scores computed from on-chain transaction activity. The scoring system ranges from **0 to 1000**, and is derived using ratios of key DeFi actions such as deposits, borrows, repayments, and liquidations.

---

## 🎯 Score Distribution (Grouped)

| Credit Score Range | Interpretation                           |
|--------------------|-------------------------------------------|
| 0–100              | Extremely risky or inactive wallets       |
| 100–200            | Very low engagement, likely bots          |
| 200–300            | Low deposit/repay activity                |
| 300–400            | Moderate risk, limited repayment behavior |
| 400–500            | Decent activity but not highly reliable   |
| 500–600            | Average reliability, repay activity seen  |
| 600–700            | Healthy repayment and borrowing behavior  |
| 700–800            | Responsible, low-risk DeFi users          |
| 800–900            | Strong behavior, trustworthy borrowers    |
| 900–1000           | Exceptional wallets with ideal patterns   |

---

## Score Distribution Chart

![Credit Score Distribution](score_distribution.png)

> *Histogram of wallet scores based on their DeFi activity*

---

## Behavioral Observations

### Wallets Scoring 0–200:
- **Activity**: Little to no DeFi engagement
- **Patterns**: No deposits or repayments; mostly idle or automated accounts
- **Risk**: Extremely high-risk or inactive users
- **Examples**: Likely bots or dormant wallets

---

### Wallets Scoring 200–400:
- **Activity**: Some interaction, possibly limited or one-sided
- **Patterns**: Borrow without repayment, or isolated deposit actions
- **Risk**: Moderate to high-risk behavior
- **Indicators**: Possible opportunistic wallets using DeFi unsustainably

---

### 🟡 Wallets Scoring 400–600:
- **Activity**: Regular borrowing and some repayments
- **Patterns**: Moderate risk but not severely penalized
- **Behavior**: Users may be improving, or using DeFi cautiously

---

###  Wallets Scoring 600–800:
- **Activity**: Balanced borrowing and repayment
- **Patterns**: Responsible usage patterns, low liquidation events
- **Behavior**: Considered reliable users of DeFi protocols
- **Use Case**: Good candidates for credit extensions or loyalty rewards

---

###  Wallets Scoring 800–1000:
- **Activity**: High-frequency, reliable engagement
- **Patterns**: Regular deposits, borrowing with consistent repayment, minimal or no liquidation
- **Behavior**: Highly trustworthy
- **Interpretation**: Elite DeFi participants, potentially valuable for whitelisting or governance roles

---

##  Final Remarks

- The model successfully identifies varying tiers of wallet reliability based on transparent on-chain actions.
- The left-skewed nature of the score distribution suggests a **long tail of high-performing users**, but a dense population of lower-engagement wallets.
- This credit scoring framework can be extended or embedded into decentralized lending, access control, or loyalty programs within DeFi ecosystems.

---

*For scoring logic and data processing pipeline, refer to `score_wallets.py` and `README.md`.*
