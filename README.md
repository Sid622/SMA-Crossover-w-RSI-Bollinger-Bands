# SMA-Crossover-w-RSI-Bollinger-Bands
This project implements a strategy that combines three indicators: SMA Crossover, Bollinger Bands, and RSI to identify optimal buying opportunities in equity markets.
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
   RSI < 30: Oversold
   Current Threshold: RSI < 40 (Moderately oversold)
   Extreme momentum in one direction will not last forever, leading to mean reversion. RSI quantifies this exhuastion. 
   
