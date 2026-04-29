# 🎰 Apriori Lottery Fusion

A research project combining **Monte Carlo simulation**, **XGBoost regression/classification**, **Apriori association rules**, and **O-Information synergy detection** to analyze Powerball and Mega Millions historical draw patterns.

## 🚀 Quick Start (Google Colab T4)

Open `Initial Research/Lottery_Apriori_Emergence_v2.ipynb` in Colab and run cells 1–6 in order.

## 📓 Notebook: 6 Cells

| Cell | Purpose |
|------|----------------------------------------------|
| 1 | Install packages |
| 2 | Data ingestion (data.ny.gov) + feature engineering (114 features) |
| 3 | Apriori rules + O-Information synergy beam |
| 4 | XGBoost white-ball regressors + special-ball classifier + 200k MC simulation |
| 5 | Fusion (MC 50% + XGBoost 30% + Apriori 20%) + walk-forward validation |
| 6 | Accuracy report + save JSON/CSV |

## 🏆 Latest Results (2026-04-29)

| Game | Ticket | Special Ball |
|------|--------|--------------|
| **Powerball** | 18 · 31 · 32 · 33 · 36 | PB: **3** |
| **Mega Millions** | 7 · 16 · 32 · 35 · 40 | MB: **12** |

## 📊 Validation

| Game | Avg Hits/Draw | Random Baseline | Edge |
|------|:---:|:---:|:---:|
| Powerball | 0.430 | 0.362 | **+18.7%** |
| Mega Millions | 0.380 | 0.357 | **+6.4%** |

## ⚠️ Disclaimer

Lottery draws are **independently and uniformly random**. No model can beat chance over a large future sample. This project is for **educational and entertainment purposes only**. The measured edge reflects historical frequency patterns in training data, not true future predictive power.

## 🔬 Methods

- **Monte Carlo**: 200,000 frequency-weighted simulations per game
- **XGBoost**: 500-tree regressor per white ball + 400-tree classifier for special ball (T4 GPU)
- **Apriori**: Association rules at min_support=0.03, lift≥1.0
- **O-Information**: Synergy beam search (orders 2–4) detecting emergent multiplets
- **Feature set**: 114 features — lags, deltas, modular arithmetic, rolling Hurst proxy, pairwise sums/diffs/products
