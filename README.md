# trial-task 1
# Blockhouse Trial Task — Order Flow Imbalance Features

This repository contains the implementation of various Order Flow Imbalance (OFI) features.

---

## Contents

- `first_25000_rows.csv` — Provided market data sample (AAPL)
- `ofi_features(1).py` — Standalone script version
---

## Features Implemented

### 1. Best-Level OFI
Captures directional imbalance at the top of the order book using:
OFI = ΔBidSize × 1{ΔBidPrice > 0} − ΔAskSize × 1{ΔAskPrice < 0}

### 2. Multi-Level OFI
Extends the above across the top 10 book levels to capture broader market depth.

### 3. Integrated OFI (PCA)
Applies Principal Component Analysis (PCA) to compress the 10-level OFI vector into a single signal that retains the strongest imbalance component.

### 4. Simulated Cross-Asset OFI
Since the dataset includes only AAPL, we simulated cross-impact by shifting OFI over time and testing its predictive power via Lasso regression. As expected, R² was near zero.
