# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 5: Social Media Driven Stock Picks


<br>

## Content Directory:
- [Background](#Background)
- [Exploratory Data Analysis](#Exploratory-Data-Analysis)
- [Data Preprocessing](#Data-Preprocessing)
- [Modeling](#Modeling)
- [Key Recommendations](#Key-Recommendations)

<br>


## Background
The COVID19 pandemic acted as a catalyst that allow of rthe huge influx of retail investors into the market. This then snowballed into the meme stock phenomenon where the retail investors are able to organized themselves and drive up the price of certain stocks (which are now dubbed as meme stocks). The most famous case that most people heard of is the case of GME where a community of retail investors from this subreddit called r/wallstreetbets were able to coordinate a short squeeze and drive a hedge fund, Melvin Capital into massive losses. Melvin Capital has since then been closed down. 

This shows that the retail investors are big enough that they have power to a certain extent to influence the market. Insitution investors can now no longer ignore their retail investors counterpart and would have to take into account the sentiment of the retail investors when making investment decisions.

Reference Website
- [Deloitte Article]https://www2.deloitte.com/us/en/pages/financial-services/articles/the-future-of-retail-brokerage.html
)
- [World Economic Forum](https://www.weforum.org/agenda/2022/10/a-fresh-look-at-how-to-empower-retail-investors/
)

<br>


## Problem Statement
How can one determine what stocks to pick based on what is being discussed a lot by retail investors, and make a forecast on the most discussed stocks to determine whether that particular stock should be invested in.

	(1) Obtain data from social media regarding the most discussed stocks by retail investors

    (2) Build a forecasting model to predict the stocks' future performance 

	(2) Determine whether the particular stock is worth investing into 
<br>


<br>

## Project Deliverables
This project is centered around the following objectives:

1. Obtain the data needed from social media, which in this case reddit, where there are subreddits like r/wallstreetbets and r/investing that retail investors often frequent to discuss investment strategies.
2. Based on the data collected, to determine the top 4 most discussed stocks in both the subreddits listed above.
3. Forecast the future performance of the discovered stocks.
4. Provide a recommendation based on the forecast result of whether one should buy or sell each of the stocks.

<br>

---

## Datasets:
Posts data was scraped from reddit to analyze which stocks that are being discussed the most in each subreddit of r/wallstreetbets and r/investing. The historical data of each of those stocks were then obtained from Nasdaq's website which contains stock price of each from 26th July 2013 to 25th July 2023.

1.  [`wallstreetbets_top_test`]: The data that was scraped from r/wallstreetbets

2. [`investing_top_test`]: The data that was scraped from r/wallstreetbets

3. [`gme_historical.csv`]: Historical data of Gamestop's stock price 

4. [`amc_historical.csv`]: Historical data of AMC's stock price 

5. [`tsla_historical.csv`]: Historical data of Tesla's stock price 

6. [`meta_historical.csv`]: Historical data of Meta's stock price 

7. [`gm_historical.csv`]: Historical data of General Motor's stock price 

8. [`uber_historical.csv`]: Historical data of Uber's stock price 

9. [`riot_historical.csv`]: Historical data of Riot platform's stock price 

10. [`amd_historical.csv`]: Historical data of AMD's stock price 


<br>

## Data Dictionary: Features listed below are the only features that are utilized in this work
| Feature                   | Type    | Dataset                       | Description                                 |   
|---------------------------|---------|-------------------------------|---------------------------------------------|
| Title                     | object  | 1 & 2                         | Title of the reddit post                    |   
| Post text                 | object  | 1 & 2                         | Text body of the reddit post                |   
| Date                      | object  | 3 - 10                        | Date of the stock price entry               |   
| Close/Last                | object  | 3 - 10                        | Last price at which a stock is traded during that trading day|   
| Volume                    | object  | 3 - 10                        |total number of shares or contracts exchanged between buyers and sellers of a stock during trading hours on a given day      |  
| High                      | object  | 3 - 10                        | The highest closing price of a stock over the past 52 weeks, adjusted for any stock splits, or the highest intraday price of a stock in the most recent (or current) trading session.|   
| Low                       | object  | 3 - 10                        |the lowest price a share has cost according to trade outcomes in a single trading period.  |   
| VWAP                      | object  | 3 - 10                        |The volume-weighted average price (VWAP) is a technical analysis indicator used on intraday charts that resets at the start of every new trading session|     
 



---

<br>
<br>

## Data Preprocessing

Data cleaning was performed to both the scraped reddit data and the historical stock price data, checks such as checking for null values, checking for duplicates, removing some symbols in the certain cells, changing the data type to the appropriate ones to fascillitate the modelling process.



## Modeling

Following the data preprocessing stage, the preprocessed dataset was fed into various models such as Regression models, Random Forest, ARIMA, Naive Forecaster, fbprophet, etc. The model that performs the best in terms of r-squared and MAPE (Mean Absolute Percentage Error) was then selected as the final model that is used for the forecast of the stock price.


<br>
<br>

## Summary of Final Model Perforamance

| **Stock**  | **R2** | **MAPE** |
|------------|--------|----------|
| GME        | 0.98   | 2.01%    |
| AMC        | 0.98   | 2.36%    |
| TSLA       | 0.97   | 2.91%    |
| META       | 0.72   | 3.86%    |
| GM         | 0.92   | 1.05%    |
| UBER       | 0.99   | 0.18%    |
| RIOT       | 0.90   | 4.4%     |
| AMD        | 0.96   | 2.28%    |


<br>



---

<br>


## Key Recommendations

Recommendations were provided in accordance to the forecast result of each stock.

---
## Reference
(1) Wall Street Journal <br>
https://www.wsj.com/articles/melvin-plotkin-gamestop-losses-memestock-11643381321

(2) Financial Times <br> 
https://www.ft.com/content/dcd86860-09ed-420e-a5cc-d6d281863c03

(3) Reuters
<br> https://www.reuters.com/technology/year-gamestop-champion-roaring-kitty-is-quiet-yet-much-richer-2022-02-02/


