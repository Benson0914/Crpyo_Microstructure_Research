# Crypto Market Microstructure Research

Then 2-3 lines:

An empirical study of crypto order book imbalance, short-horizon return prediction, regime persistence, and execution feasibility using Binance order book data.

# **1. Research Motivation**

Short paragraph.

Example:

This project investigates whether short-horizon order book imbalance contains statistically meaningful predictive information about future mid-price movements in crypto markets.

Rather than relying on global correlations, the research focuses on conditional market regimes, persistence dynamics, and execution feasibility under transaction costs.

Professional and clean.

# **2. Research Questions**

VERY IMPORTANT SECTION.

Use bullets.

## Research Questions

- Does order book imbalance predict short-horizon future returns?
- Does volatility affect imbalance persistence?
- How long does imbalance memory survive?
- Are observed patterns statistically significant or random noise?
- Can statistical edge survive realistic transaction costs?

This instantly makes project look serious.

# **3. Data**

Example:

## Data

- Exchange: Binance
- Asset: BTCUSDT Perpetual
- Frequency: 5-second order book snapshots
- Duration: ~6 hours
- Observations: 4000+ snapshots
- Data Source: ccxt API

# **4. Feature Engineering**

THIS SECTION IS IMPORTANT.

Now introduce formulas.

YES you should include formulas.

This makes it feel quantitative.

# **Mid Price**

### Mid Price

\[

MidPrice*_t = \frac{BestBid_*t + BestAsk*_t}{2}*

*\]*

# **Imbalance Score**

VERY IMPORTANT.

### Order Book Imbalance

\[

Imbalance*_t =*

*\frac{BidDepth_*t - AskDepth*_t}*

*{BidDepth_*t + AskDepth*_t}*

*\]*

*Values near +1 indicate dominant bid-side pressure, while values near -1 indicate dominant ask-side pressure.*

VERY GOOD.

# **Future Return**

### Forward Return

\[

Return*_{t+h} =*

*\frac{MidPrice_*{t+h} - MidPrice*_t}*

*{MidPrice_*t}

\]

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
