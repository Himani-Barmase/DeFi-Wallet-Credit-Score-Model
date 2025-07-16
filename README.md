
# DeFi Wallet Credit Score Model

This project implements a credit scoring system for DeFi (Decentralized Finance) wallets based on their historical on-chain transaction behavior.


- **Source**: [user-wallet-transactions.zip](https://github.com/Himani-Barmase/DeFi-Wallet-Credit-Score-Model/raw/main/user-wallet-transactions.zip)
- **Format**: JSON
- **Fields**: 
  - `userWallet`: Wallet address
  - `action`: On-chain transaction type (e.g., deposit, borrow, repay, liquidationcall)

 Methodology

### Step 1: Data Extraction
- Downloads a zipped JSON file from GitHub and extracts it.

### Step 2: Data Cleaning
- Retains only the `wallet` and `action` columns.
- Converts data into a format suitable for aggregation.

### Step 3: Feature Engineering
- Creates a pivot table to count the frequency of each action per wallet.
- Derives behavioral features:
  - `deposit_to_borrow_ratio`
  - `repay_to_borrow_ratio`
  - `liquidation_ratio`
  - `repay_score`

### Step 4: Scoring Logic
- Computes a credit score out of 1000 using the following formula:

```python
score = (
    0.25 * deposit_to_borrow_ratio +
    0.25 * repay_to_borrow_ratio +
    0.25 * (1 - liquidation_ratio) +
    0.25 * repay_score
) * 1000
