Hello! This repo contains the file that I coded when following along the cousre "Algorithmic Trading - Machine Learning & Quant Strategies Course with Python" by FreeCodeCamp.

**Purely research project for educational purposes**

<u>SUMMARY</u>
Project 1: Unsupervised Learning Trading Strategy
Project 2: Twitter Sentiment Trading Strategy
Project 3: Intraday Strategy using GARCH model

<u>ML in Trading?</u>
For Supervised Learning:
- Signal Generation through prediction. E.g. Buy/Sell signals, based on predicted returns or direction
- Risk management through prediction. E.g. Determining position sizing and SL levels to have more optimized risks

For Unsupervised Learning:
- Extract insights from the data. E.g. Discover patterns, relationships, structures

<u>Workflow Process</u>
1) Collect and prepare data
2) Develop hypothesis for strategy
3) Coding the model
4) Backtest strategy


<u>Project 1: Unsupervised Learning Trading Strategy</u>
What is UL in Trading?

- Using ML techniques to analyze financial data and discover patterns, relationships, structures within the data without any labeled or predefined target variable. Unlike supervised learning, where the model is trained to make predictions, unsupervised learning focuses on extracting insights from data.

How UL is applied in trading:
-Clustering
-Dimensionality Reduction
-Anomaly Detection
-Market Regime Detection
-Portfolio Optimization

Steps involved:
1: Download S&P500 stocks prices data
2: Calculate different technical indicators and features for each stock
3: Aggregate on monthly level and filter for each month only top 150 most liquid stocks
4: Calculate monthly returns for different time-horizons to add to features
5: Download Fama-French Factors and calculate rolling factor betas for each stock.
6: For each month fit a K-means clustering model to group similar assets based on their features.
7: For each month select assets based on the cluster and forma portfolio based on Efficient Frontier max sharpe ratio portfolio optimization
8: Visualize portfolio returns and compare to S&P500 returns

Limitation: We are using the most recent S&P500 stocks list, which means that there may be a survivorship bias in this list; in reality, you have to use survivorship free data.

<u>Project 2: Twitter Sentiment Investing Strategy</u>
Focus on analzying how people feel about certain stocks, industries or the overall market. Asssumes public sentiment can impact stock prices and markets. If many people are positive about a particular company on Twitter, it might indicate potential for that company's stock to perform well.

Steps involved:
1: Load NASDAQ stocks twitter sentiment data
2: Calculate a quantitative feature of the engagement ratio in Twitter of each stock.
3: Every month rank all stocks and construct and equal-weight portfolio
4: Compare it against NASDAQ performance

<u>Project 3: Intraday Strategy using GARCH Model</u>
Buy and sell financial assets within the same trading day to profit from short-term price movements. Intraday traders use TA, real-time data, risk management techniques to make quick decisions, aiming to capitalize on market volatility

Steps involved:
1: Load simulated daily data and simulated 5-minute data
2: Define function to fit GARCH model and predict 1-day ahead volatility in a rolling window
3: Calculate prediction premium and form a daily signal from it
4: Merge with intraday data and calculate intraday indicators to form the intraday signal
5: General position entry and hold until EOD
6: Calculate final strategy returns

