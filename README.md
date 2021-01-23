# Capstone
Capstone project

Use ARIMA and SVM Models in tandem with CANSLIM Framework to aid investors in their Due Dilligence. 

## Table of Contents
1. [1 - Fetch_Ticker_Data](/1 - Fetch_Ticker_Data.ipynb)
2. [1 - FinViz](./1 - FinViz.ipynb)
3. [1- AlphaVantage_Wrapper](./1- AlphaVantage_Wrapper.ipynb)
4. [2 - ARIMA](./2 - ARIMA.ipynb)
5. [3 - SVM](./3 - SVM.ipynb)
6. [4- CANSLIM](./4- CANSLIM.ipynb)
7. [Executive_Summary](Executive_Summary.md)
8. [Tableau Visualizations](https://public.tableau.com/profile/maxwell.bosse#!/vizhome/DOCU/StockPrice)

## Features in stock_data.csv

|Feature|Type|Origin|Description|
|---|---|---|---|
**1. open**|*float*|AlphaVantage|Open price for the stock. 
**2. high**|*float*|AlphaVantage|Daily high price for stock.
**3. low**|*float*|AlphaVantage|Daily low price for the stock.
**4. close**|*float*|AlphaVantage|Closing price for the stock.
**5. volume**|*float*|AlphaVantage|Daily trading volume for the stock.
**IWO_5d_EMA**|*float*|AlphaVantage|iShares Russell 2000 Growth ETF 5 day exponential moving average.
**IWO_10d_EMA**|*float*|AlphaVantage|iShares Russell 2000 Growth ETF 10 day exponential moving average.
**IWO_150d_EMA**|*float*|AlphaVantage|iShares Russell 2000 Growth ETF 150 day exponential moving average.
**EMA_8**|*float*|AlphaVantage|8 day exponential moving average for the stock.
**EMA_21**|*float*|AlphaVantage|21 day exponential moving average for the stock.
**SMA_50**|*float*|AlphaVantage|50 day simple moving average for the stock.
**SMA_200**|*float*|AlphaVantage|200 day simple moving average for the stock.

## Features in stock_earnings.csv

|Feature|Type|Origin|Description|
|---|---|---|---|
**surprise**|*float*|AlphaVantage|Reported quarterly EPS - estimated quarterly EPS.
**surprisePercentage**|*float*|AlphaVantage|(Reported quarterly EPS/estimated quarterly EPS) *100.
**reported_Quarterly_EPS**|*float*|AlphaVantage|Reported quarterly earnings per share.
**estimated_Quarterly_EPS**|*float*|AlphaVantage|Estimated quarterly earnings per share.
**reported_Annual_EPS**|*float*|AlphaVantage|Reported annual earnings per share.

## Features in CANSLIM.csv

|Feature|Type|Origin|Description|
|---|---|---|---|
**IWO_5d_EMA**|*float*|AlphaVantage|iShares Russell 2000 Growth ETF 5 day exponential moving average for most recent close date.
**IWO_10d_EMA**|*float*|AlphaVantage|iShares Russell 2000 Growth ETF 10 day exponential moving average for most recent close date.
**IWO_150d_EMA**|*float*|AlphaVantage|iShares Russell 2000 Growth ETF 150 day exponential moving average for most recent close date.
**Institutional_Ownership**|*float*|FinViz.com|Institutional Ownership of Stock.
**Institutional_Ownership_3months**|*float*|FinViz|Change in institutional ownership over the last 3 months as a percentage.
**ROE_TTM**|*float*|AlphaVantage|Return on Equity for trailing twelve months.

## Software Packages Required
Numpy, Pandas, Matplotlib, pmdarima, AlphaVantage, Requests

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
- M - Market Direction via IWO EMA 
- I - Got instituional owndership and 3month delta

Need
- N - Polygon
- L - Need to be able to pull industry group and run to compare to stock of interest

