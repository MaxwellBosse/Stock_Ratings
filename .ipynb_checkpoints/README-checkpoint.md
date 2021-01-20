# Capstone
Capstone project

Problem Statement #1 - Create a multi-class classification model that takes in a stock as an input and provides the user with a buy, hold or sell recommendation based on the technical analysis, fund ownership, financials etc. 
- Could also utilize user input to group users by risk profile (which would alter the recommendation)
- Could create web app for this (Patrick suggested Django as an option to explore)

Risks - Could be difficult to incorporate every ticker into this project so may have to choose a sector/number of sectors. 

Based Recommendations on CAN SLIM 
- C stands for Current quarterly earnings. Per share, current earnings should be up at least 25% in the most recent financial quarter, compared to the same quarter the previous year. Additionally, if earnings are accelerating in recent quarters, this is a positive prognostic sign.
-- AlphaVantage - Earnings API - EPS YoY for current Q
-- AlphaVantage - Earning API - EPS accelerating (binary)


- A stands for Annual earnings growth, which should be up 25% or more over the last three years. Annual returns on equity should be 17% or more
-- AlphaVantage - Earnings API - Annual EPS from current year/current year -3 >1.25 - 
-- Annual ROE - need data souce

- N stands for New product or service, which refers to the idea that a company should have continuing development and innovation. This is what allows the stock to emerge from a proper chart pattern and achieve a new price. A notable example of this is Apple's iPhone.
-- Scrape most recent 10-K for "new product"/"new products" etc. and return count
-- Use Polygon.io API to access news headlines for ticker - use transformers to assess sentiment or to find "New Product"

- S stands for Supply and demand. A gauge of a stock's demand can be seen in the trading volume of the stock, particularly during price increases.
-- AlphaVantage 

- L stands for Leader or laggard? O'Neil suggests buying "the leading stock in a leading industry." This somewhat qualitative measurement can be more objectively measured by the Relative Price Strength Rating of the stock, designed to measure the price performance of a stock over the past 12 months in comparison to the rest of the market based on the S&P 500 (or the S&P/TSX Composite Index for Canadian stock listings) over a set period of time.


- I stands for Institutional sponsorship, which refers to the ownership of the stock by mutual funds, banks and other large institutions, particularly in recent quarters. A quantitative measure here is the Accumulation/Distribution Rating, which is a gauge of institutional activity in a particular stock.


- M stands for Market Direction, which is categorized into three - Market in Confirmed Uptrend, Market Uptrend Under Pressure, and Market in Correction. The S&P 500 and NASDAQ are studied to determine the market direction. During the time of investment, O'Neil prefers investing during times of definite uptrends of these indexes, as three out of four stocks tend to follow the general market direction.

Pulling

Completed 
- C - having quarterly and annual earnings pull
- A - annual EPS in earnings, ROE in Fundamental 
- S - Daily trading volume
- 

Need
- N - Polygon
- L - Need to be able to pull industry group and run to compare to stock of interest
- I - Need to be able to pull fund ownership of large institutions by quarter
- M - Look up market direction definitions