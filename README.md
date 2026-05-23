# Crypto Market Microstructure Research
An empirical study of crypto order book imbalance, short-horizon return prediction, regime persistence, and execution feasibility using Binance order book data.

# **1. Research Motivation**

This project investigates whether short-horizon order book imbalance contains statistically meaningful predictive information about future mid-price movements and market state persistence in crypto markets.

Rather than relying on global correlations, the research focuses on conditional market regimes, persistence dynamics, and execution feasibility under transaction costs.

# **2. Research Questions**
- Does order book imbalance predict short-horizon future returns?
- Does volatility affect imbalance persistence?
- How long does imbalance memory survive?
- Are observed patterns statistically significant or random noise?
- Can statistical edge survive realistic transaction costs?

# **3. Data**
|  | Research Data Set  | Testing Data Set |
| -------- | ------------- | ------------- |
| Exchange | Binance | Binance |
| Asset | BTCUSDT Perpetual | BTCUSDT Perpetual |
| Frequency | 5-second order book snapshots | 5-second order book snapshots |
| Duration | ~3 hours | ~6 hours |
| Observations | 2000+ snapshots | 4000+ snapshots |
| Data Source | ccxt API | ccxt API |

# **4. Feature Engineering**

### **Mid Price**


## $Mid Price = \frac{P_{bids}*Q_{bids}+P_{asks}*Q_{asks}}{Q_{bids}+Q_{asks}}$

### Order Book Imbalance
## $Imbalance Score = \frac{BidDepth_{t}-AskDepth_{t}}{BidDepth{t}+AskDepth_{t}}$

*Values near +1 indicate dominant bid-side pressure, while values near -1 indicate dominant ask-side pressure.*

### Forward Return

## $Return_{t+h} = \frac{MidPrice_{t+h} - MidPrice_t}{MidPrice_t}$


# **Rolling Autocorrelation**

### Rolling Memory

Rolling autocorrelation was used to estimate short-horizon persistence of imbalance states.

No need complicated formula here.

# **5. Methodology**

This section makes it feel research-level.

Structure it clearly.

# **Regime Segmentation**

The imbalance signal was discretized into five conditional regimes:

- Extreme Sell [-1.0, -0.6]
- Weak Sell [-0.6, -0.2]
- Neutral [-0.2, 0.2]
- Weak Buy [0.2, 0.6]
- Extreme Buy [0.6, 1.0]

# **Volatility Conditioning**

Market states were further segmented into high-volatility and low-volatility environments to examine persistence breakdown during turbulent conditions.

# **Alpha Decay**

Autocorrelation decay profiles were computed to estimate signal memory and execution horizons.

# **Statistical Validation**

The following statistical methods were applied:

- Wilcoxon Signed-Rank Test
- Mutual Information Analysis
- Bootstrap Resampling

# **6. Key Findings**

THIS is the most important section.

Put charts here.

Use image markdown normally.

# **Example**

## Conditional Return Structure
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")

Extreme imbalance states showed monotonic directional drift in future short-horizon returns.

Then insert chart.

Then:

## Volatility vs Persistence

Volatility spikes were associated with collapsing autocorrelation and reduced market memory.

Then scatter chart.

Then:

## Alpha Decay

Signal persistence decayed significantly after approximately 20 seconds.

Then decay chart.

# **7. Statistical Results**

Short and clean.

# **Example**

## Statistical Validation

### Wilcoxon Signed-Rank Test

P-value:

\[

4.73 \times 10^{-11}

\]

Result:

The directional drift is statistically significant and unlikely to be caused by random sampling noise.

### Mutual Information

- Imbalance → Future Return: 0.0742
- Volatility → Future Return: 0.2872

# **8. Backtest & Execution Reality**

THIS is your strongest section psychologically.

Because it shows maturity.

## Trading Feasibility

Although statistically significant directional structure was detected, the strategy failed after realistic transaction costs.

### Results

- Gross PnL: +6.18%
- Net PnL After Fees: -94.26%
- Profitability Probability (Bootstrap): 0.00%

This demonstrates an important microstructure reality:

*> Statistical predictability does not necessarily imply executable alpha after fees and turnover.*

This is VERY GOOD.

# **9. Limitations**

Very important.

Makes you sound intelligent.

## Limitations

- Limited observation window
- Single exchange analysis
- No queue position modelling
- No slippage modelling
- No latency-aware execution engine
- No cross-exchange liquidity analysis

# **10. Future Work**

Short section.

## Future Work

- Multi-exchange synchronization
- Latency-aware execution simulation
- Queue position modelling
- Adaptive regime-switching models
- Reinforcement learning execution policies
