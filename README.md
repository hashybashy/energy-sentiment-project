# energy-sentiment-project
Cross-sectional long/short backtest on XOM and CVX using simulated sentiment signals, including portfolio and per-stock cumulative return plots
Short description: I created this project as a beginner-friendly demonstration of a sentiment-driven long/short trading strategy applied to two energy stocks (Exxon — XOM, Chevron — CVX). The main idea I explored is: each day, I rank stocks by sentiment and go long the most positive, short the most negative. All price and return data I used are real (from Yahoo Finance), but the sentiment is intentionally synthetic (randomly generated) so I could practice the full pipeline without needing an API key or complicated NLP preprocessing, but I will work on a more complex version in the future!

The approach is to use signals (things that tell me what to buy or sell) built from text like news, tweets, or analyst reports, but in this project specifically I used news. This project shows the whole pipeline: price data ➜ signal ➜ trading decision ➜ performance chart. I kept the signal simple and easy to understand so I could focus on learning the mechanics without worrying about messy NLP data.

How I interpret the results
The strategy’s performance is not meaningful as an investment because the sentiment is random
I look at both portfolio and per-stock plots to see where gains/losses come from
With only two stocks, the strategy is effectively a daily pair trade (long one, short the other). Adding more tickers would make it more realistic

What the graphs show:
Portfolio Cumulative Return Graph:
Shows how my combined strategy would have performed over time if I followed my rules.
Each day, I look at all the stocks, pick one to go long and one to go short, and calculate the average profit or loss.
The line moves up if the strategy makes money that day and down if it loses money.
The final value shows the total cumulative profit/loss over the period.
Think of it as the “big picture” of the strategy’s performance.
Individual Stocks Cumulative Return Graph:
Shows how each stock contributes separately to the strategy’s profit/loss.
For each stock, I take the position I held that day (long or short) and multiply by the next day’s return.
Then I add this up over time to get a cumulative return for each stock.
This helps me see which stock helped or hurt my portfolio on different days.
Analogy:
Portfolio graph = overall bank account from trading this strategy.
Individual stock graph = each “piggy bank” showing how much it added or subtracted.

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
