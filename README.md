# SMA-Crossover-w-RSI-Bollinger-Bands
This project combines technical indicators to identify entry and exit points in the SPY (S&P 500 ETF). This strategy uses a simple moving average, Bollinger Bands, and RSI with ATR for risk management. 

Main Idea: Prices following a mean reverting pattern when they become oversold during a bull market. By following multiple technical indicators, we can identify accurate risk-reward opportunities. 

Technical Indicators
1. Simple Moving Average (SMA) Crossover
   Measures: Trend direction and strength
   Parameters:
   SMA50: 50 day moving average (short-term trend)
   SMA200: 200 day moving average (long-term trend)
   Signal:
   Golden Cross (SMA50 > SMA200): Bullish uptrend
   Death Cross (SMA50 < SMA200): Bearish downtrend

2. Bollinger Bands
   Measures: Price volatility
   Parameters:
   Period: 20 days
   Components:
   Upper Band: Middle + (2 * Std Dev) = Overbought
   Middle Band: 20-day SMA = Mean Price
   Lower Band: Middle - (2 * Std Dev) = Oversold
   Signal:
   Price at lower band = Cheap (Buy)
   Price at upper band = Expensive (Don't buy)
   When volatility pushes prices to extremes, mean reversion probability increases.
   
3. Relative Strength Index (RSI)
   Measures: Momentum
   Parameters:
   Period: 14 days
   Calculation:
   RSI = 100 - (100 / (1 + RS))
   RS = Average Gain / Average Loss (Over 14 days)
   Zones:
   RSI > 70 = Overbought
   RSI 30-70 = Normal
   RSI < 40: Oversold
   Current Threshold: RSI < 40 (Moderately oversold)
   Extreme momentum in one direction will not last forever, leading to mean reversion. RSI quantifies this exhuastion.

Entry Conditions:

1. Trend Filter (SMA Crossover): 50-day SMA > 200-day SMA (Golden Cross)
2. Mean Reversion (Bollinger Bands): Price <= Lower Bollinger Band
3. Momentum (RSI): RSI < 40 (Oversold)

Exit Conditions:

1. Profit Target: RSI > 65 (overbought)
2. Stop Loss: Price falls 2x ATR below entry price
3. Time Stop: Position held for 30 days

Equity Curve
   
   <img width="760" height="606" alt="image" src="https://github.com/user-attachments/assets/d833bf7f-6fb5-4ebd-aaeb-beea65696aa7" />

The equity curve is a visual plot that shows cumulative profit/loss over time. This strategy has proven to work as it has gone significantly higher than the break-even line. With a 62% win rate and a 1.29% average return per trade, the strategy shows some gains. Cumulative returns are normalized to starting capital of 1.0.

Limitations:

May underperform in strong bull markets where prices don't fall to the lower Bollinger Band, resulting in miss trades. The Golden Cross avoids bear market trades, however this could cause the strategy to sit idle and miss certain opportunities. 

Getting Started

Clone the repository
Run the script to fetch live data from yfinance
Adjust parameters for technical indicators as needed
Analyze equity returns graph to evalulate strategy viability
