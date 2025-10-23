# energy-sentiment-project
Cross-sectional long/short backtest on XOM and CVX using simulated sentiment signals, including portfolio and per-stock cumulative return plots
Short description: I created this project as a beginner-friendly demonstration of a sentiment-driven long/short trading strategy applied to two energy stocks (Exxon — XOM, Chevron — CVX). The main idea I explored is: each day, I rank stocks by sentiment and go long the most positive, short the most negative. All price and return data I used are real (from Yahoo Finance), but the sentiment is intentionally synthetic (randomly generated) so I could practice the full pipeline without needing an API key or complicated NLP preprocessing, but I will work on a more complex version in the future!

The approach is to use signals (things that tell me what to buy or sell) built from text like news, tweets, or analyst reports, but in this project specifically I used news. This project shows the whole pipeline: price data ➜ signal ➜ trading decision ➜ performance chart. I kept the signal simple and easy to understand so I could focus on learning the mechanics without worrying about messy NLP data.

How I interpret the results
The strategy’s performance is not meaningful as an investment because the sentiment is random
I look at both portfolio and per-stock plots to see where gains/losses come from
With only two stocks, the strategy is effectively a daily pair trade (long one, short the other). Adding more tickers would make it more realistic

Possible improvements:
Add transaction costs and execution logic
Replace synthetic sentiment with real NLP-derived sentiment
Expand to more stocks or ETFs
Implement risk adjustments: position sizing, max drawdown, Sharpe, etc
Add tests for missing data handling and alignment

Glossary:
Adjusted Close: Price adjusted for splits and dividends. I use this for accurate historical returns.
Return: Percentage change in price from one day to the next. I use next-day returns to simulate a strategy acting on today’s signal and realizing tomorrow’s return
Sentiment signal: A numeric score that would normally come from text indicating positive/negative feelings about a stock. In this project, it’s fake
Cross-sectional ranking: Ranking multiple stocks each day and choosing positions based on relative rank
Long / Short: Long = buy (benefit if price rises). Short = sell/short (benefit if price falls)
