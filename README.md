# Bitcoin Sentiment vs. Trader Performance Analysis

> **Primetrade.ai Data Science Assignment**  
> Exploring the relationship between Bitcoin market sentiment (Fear & Greed Index) and real trader performance data from Hyperliquid.

---

##Project Overview

This project investigates how market sentiment — measured by the **Bitcoin Fear & Greed Index** — influences trader behaviour and performance on the **Hyperliquid** decentralised exchange.

By merging ~211,000 trade records with daily sentiment classifications, we uncover hidden patterns in:
- Profitability across sentiment regimes
- Long vs. Short positioning shifts
- Trade sizing and volume behaviour
- Top-performer vs. underperformer strategies
- Actionable trading strategy insights

---

## Repository Structure

```
trader_and_sentiment_analysis/
│
├── trader_and_sentiment_analysis.ipynb   # Main analysis notebook
├── fear_greed_index.csv                  # Bitcoin Fear & Greed Index (daily)
├── historical_data.csv                   # Hyperliquid trader history (~211K trades)
├── Trader_Sentiment_Report.docx          # Written insights report
└── README.md                             # This file
```

---

## Datasets

### 1. Bitcoin Fear & Greed Index (`fear_greed_index.csv`)
| Column | Description |
|---|---|
| `date` | Date of the sentiment reading |
| `value` | Numeric score (0–100) |
| `classification` | Label: `Extreme Fear`, `Fear`, `Neutral`, `Greed`, `Extreme Greed` |

### 2. Hyperliquid Historical Trader Data (`historical_data.csv`)
| Column | Description |
|---|---|
| `Account` | Trader wallet address |
| `Coin` | Asset traded |
| `Execution Price` | Fill price |
| `Size Tokens` | Trade size in tokens |
| `Size USD` | Trade size in USD |
| `Side` | BUY / SELL |
| `Direction` | Open Long / Open Short / Buy / Sell |
| `Closed PnL` | Realised profit or loss |
| `Fee` | Trading fee paid |
| `Timestamp IST` | Trade timestamp (IST) |

> **Match rate:** 99.997% of trades were successfully matched to a sentiment day.

---

## Key Findings

| Metric | Best Sentiment | Worst Sentiment |
|---|---|---|
| Avg PnL per Trade | **Extreme Greed** ($130.21) | Extreme Fear ($71.03) |
| Win Rate | **Extreme Greed** (89.17%) | Extreme Fear (76.22%) |
| Total Volume | **Fear** ($483M) | Extreme Greed ($124M) |
| Avg Trade Size | **Fear** ($7,816) | Extreme Greed ($3,112) |

### Notable Insights

- **Traders go contrarian in Greed:** During Greed/Extreme Greed, ~55% of position opens are **Short**, while during Extreme Fear, ~69% are **Long**.
- **Fear drives volume:** Traders are most active (by count and size) during Fear periods — possibly bargain hunting.
- **Extreme Greed is most profitable:** Despite lower volume, trades in Extreme Greed periods yield the highest average PnL and win rate.
- **29 of 32 accounts** are net profitable over the full period.
- **16 of 24 accounts** perform better during Greed than Fear (when comparing avg per-trade PnL).
- **Fee drag is consistent** at ~0.019–0.022% of notional across all sentiment regimes.

---

## Strategy Recommendations

1. **Ride the Greed wave:** Enter long positions during Greed phases for statistically higher PnL and win rates.
2. **Reduce size in Fear:** Traders tend to over-size in Fear — smaller, more disciplined sizing may improve risk-adjusted returns.
3. **Contrarian shorts in Extreme Greed:** The majority of profitable traders go Short in Extreme Greed — consider this as a hedge signal.
4. **Use FG as a filter, not a trigger:** Sentiment is a regime indicator, not a precise entry signal. Combine with price action.

---

## Running the Notebook

### Prerequisites

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### Steps

```bash
# Clone the repo
git clone https://github.com/Raghav02911/trading_and_sentiment_analysis.git
cd trading_and_sentiment_analysis

# Launch Jupyter
jupyter notebook trader_and_sentiment_analysis.ipynb
```

> **Note:** Update `UPLOAD_DIR` and `OUT_DIR` in the first cell to point to the folder where your CSVs are located if running locally (not on Colab).

---

## Tech Stack

| Tool | Purpose |
|---|---|
| Python 3.x | Core language |
| Pandas | Data manipulation |
| NumPy | Numerical operations |
| Matplotlib | Visualisations |
| Seaborn | Statistical plots |
| Jupyter Notebook | Interactive analysis |

---

## Author

**Raghav**  
Submitted as part of the **Primetrade.ai Data Science Hiring Assignment**

---

## 📄 License

This project is for evaluation purposes only.
