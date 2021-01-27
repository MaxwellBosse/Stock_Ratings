# Executive Summary 

### Project Goal
- Use ARIMA and SVM Models in tandem with CANSLIM Framework to aid investors in their Due Dilligence. End goal is a (multi)classification model that takes in a stock and gives it a buy/hold/sell recommendation. 

### Data
- Data was retrieved using AlphaVantage API and by scraping FinViz, an website that has many metrics on most publically listed companies

### Metrics
- The methodology used for this project orginated from William O'Neil who developed a system for selecting growth stocks using a combination of fundamental and technical analysis. This system is known as CANSLIM

- Each letter in the acronym stands for a key factor investors should look for when initiating/adding to a position in a public company. 

-- C stands for Current quarterly earnings. Per share, current earnings should be up at least 25% in the most recent financial quarter, compared to the same quarter the previous year. Additionally, if earnings are accelerating in recent quarters, this is a positive prognostic sign.
-- A stands for Annual earnings growth, which should be up 25% or more over the last three years. Annual returns on equity should be 17% or more
-- N stands for New product or service, which refers to the idea that a company should have continuing development and innovation. This is what allows the stock to emerge from a proper chart pattern and achieve a new price. A notable example of this is Apple's iPhone.
--S stands for Supply and demand. A gauge of a stock's demand can be seen in the trading volume of the stock, particularly during price increases.
-- L stands for Leader or laggard? O'Neil suggests buying "the leading stock in a leading industry." This somewhat qualitative measurement can be more objectively measured by the Relative Price Strength Rating of the stock, designed to measure the price performance of a stock over the past 12 months in comparison to the rest of the market based on the S&P 500 (or the S&P/TSX Composite Index for Canadian stock listings) over a set period of time.
-- I stands for Institutional sponsorship, which refers to the ownership of the stock by mutual funds, banks and other large institutions, particularly in recent quarters. A quantitative measure here is the Accumulation/Distribution Rating, which is a gauge of institutional activity in a particular stock.
-- M stands for Market Direction, which is categorized into three - Market in Confirmed Uptrend, Market Uptrend Under Pressure, and Market in Correction. The S&P 500 and NASDAQ are studied to determine the market direction. During the time of investment, O'Neil prefers investing during times of definite uptrends of these indexes, as three out of four stocks tend to follow the general market direction.


- In addition to the metrics highlighted above, the predictions of both the ARIMA model and SVM model are used in the screener to advise potential investors. 


### Findings
After running multiple tickers through the models it is clear that the volatility in the stock market over the last year from the impact of Covid-19 makes it extremely difficult to have any sort of accuracy in predicting a stock price. The visualizations we can construct from the stock data we pulled + scraped is still helpful in aiding potential investors to idetify stocks with strong support levels and growth potential. 
