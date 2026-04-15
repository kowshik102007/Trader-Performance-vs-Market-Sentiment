# Hyperliquid Trader Behavior vs Bitcoin Market Sentiment Analysis

## Objective

This project analyzes how Bitcoin market sentiment (Fear / Greed Index) influences trader behavior and profitability on Hyperliquid. The main objective is to identify sentiment-driven trading patterns and derive actionable strategy recommendations that can support smarter trading decisions.

## Dataset Files

This analysis uses two datasets:

1. **fear_greed_index(1).csv**

   * Contains Bitcoin market sentiment data
   * Main columns: `date`, `classification`

2. **historical_data(1).csv**

   * Contains Hyperliquid trade-level historical records
   * Main columns: `Account`, `Timestamp`, `Side`, `Closed PnL`, `Size USD`, `Start Position`

## Methodology

The project was completed in the following steps:

1. **Data Loading and Quality Checks**

   * Loaded both CSV datasets using pandas
   * Checked dataset dimensions
   * Identified missing values and duplicates

2. **Data Preparation**

   * Converted timestamps into datetime format
   * Extracted daily dates from trade timestamps
   * Merged both datasets on date
   * Removed rows without valid sentiment labels

3. **Performance Analysis**

   * Compared average PnL across sentiment regimes
   * Calculated win rate by sentiment
   * Analyzed profitability patterns

4. **Behavioral Analysis**

   * Trade frequency by sentiment
   * Average trade size by sentiment
   * Long vs short bias
   * Trader segmentation

5. **Predictive Modeling (Bonus)**

   * Built a classification model to predict profitable trades
   * Model accuracy achieved: **72%**

## Key Insights

* **Greed** periods show the highest average profitability
* **Extreme Greed** shows the highest win rate
* **Fear** periods show the highest trade frequency
* SELL trades dominate during Greed conditions
* Larger trade sizes are observed during Fear and Extreme Greed

## Strategy Recommendations

### 1. Fear Regime

Use short-term higher-frequency strategies with strict stop-loss controls, as Fear periods show the highest trade activity and strong opportunities.

### 2. Greed Regime

Use profit-booking and SELL-biased mean-reversion strategies, as Greed periods show the highest average PnL.

### 3. Extreme Greed Regime

Reduce position size despite higher win rate, since average profitability is lower than standard Greed periods.

## Setup Instructions

Install required libraries:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

## How to Run

Open Jupyter Notebook and run the notebook cell by cell:

```bash
jupyter notebook
```

Then open the notebook file and execute all cells from top to bottom.

## Final Conclusion

This study demonstrates that Bitcoin market sentiment strongly affects trader behavior and profitability on Hyperliquid. Different sentiment regimes create different trading opportunities, making sentiment a useful regime filter for trading strategy design.
