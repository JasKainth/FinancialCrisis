# FinancialCrisis
Exploring the effects of the financial crisis on some of the largest banks in America.  

## Summary  
In this project, using a combination of data visualization and statistical models, we will analyze the returns and stock prices of some of the largest banks in America leading up to and following the financial crisis. The banks which we will take a look at are:
* Bank of America ([BAC](https://ca.finance.yahoo.com/quote/BAC/))
* CitiGroup ([C](https://ca.finance.yahoo.com/quote/C/))
* Goldman Sachs ([GS](https://ca.finance.yahoo.com/quote/GS/))
* JPMorgan ([JPM](https://ca.finance.yahoo.com/quote/JPM/))
* Morgan Stanley ([MS](https://ca.finance.yahoo.com/quote/MS/))
* Wells Fargo ([WFC](https://ca.finance.yahoo.com/quote/WFC/))  

We will use Python (Google Colab) for our analysis (.py & .ipynb file is available). To get the data, we use the data function in the pandas_datareader library to scrape the data from [Yahoo Finance](https://finance.yahoo.com/). We retrieve stock High, Low, Open, Close & Volume for each bank.    

## EDA  
We first take a look at the returns. The return is defined as the percent difference in the stock's closing price. The peak for each stock is around 0 and, it seems that the correlation among each bank was positive. However, when we break down the returns, we see there is high volatility in the years 2008 & 2009, but then over time, the volatility decreases again. While searching for the maximum and minimum values of the stocks, we find that four of the banks had their lowest stock price on the same day!  

By plotting the closing prices of the banks, we find that they all crash approximately at the same time. Some banks like CitiGroup and Goldman Sachs crash a lot harder than the rest and, they all recover at their own pace. We decompose the 'Observed' closing price of each bank into three components: 'Trend', 'Seasonal' & 'Residual'. This helps us see the general trend the stock is following and we also see the seasonal pattern. However, we note that for some of the stocks, the 'Seasonal' is almost negligible as the 'Residual' values are much greater.  

We also take a look at a 7-day and 30-day moving average for the stocks. These plots help us better visualize the trend as it smooths out the curve. However, even with the smoothing effect, the crash is still very noticeable from late 2008 to early 2009. Finally, we construct a heatmap of the correlation of closing prices for each bank. We notice that most of these values are positive (with some high correlations like Morgan Stanley with Bank of America or CitiGroup with Bank of America), which leads us to believe that if one of the banks is up on the day, then most of the other banks are also up. This is also further shown in the first plot we create, as the returns for the banks generally follow a positive trend.  

## Statistical Analysis  

### [ARIMA Model](https://www.statsmodels.org/stable/generated/statsmodels.tsa.statespace.sarimax.SARIMAX.html?)  

For the first model which we create, we use an AutoRegressive Integrated Moving Average. This helps us predict time series models using moving averages. We tune the parameters of the model using an AIC test. For each bank, we train the model using the data from 2006 to 2017 (inclusive) and create a model to forecast the 2018 & 2019 stock prices. 


## Time_Series.pdf  
In this paper, we will explore Time-Series Regression. Rather than just creating a variety of time series models and trying to fit them on the bank stocks' data, we will delve into the theory of Time Series - breaking down the models to their mathematical forms and explaining the parameters and their effects to the models. 

## Acknowledgements  
For this entire paper, I used the textbook [*Time Series Analysis and
Its Applications With R Examples*](https://www.springer.com/gp/book/9783319524511) for a deeper understanding of time series and their applications. It is a wonderful textbook that introduces the concepts in a digestible manner while also using plots to further help with the intuition behind many models.   
Also, for fitting the ARIMA model and tuning the hyperparameters, I used the following websites:  
* https://machinelearningmastery.com/arima-for-time-series-forecasting-with-python/
* https://machinelearningmastery.com/grid-search-arima-hyperparameters-with-python/
