# FinancialCrisis
Exploring the effects of the financial crisis on some of the largest banks in America.  

## Summary  
In this project, using a combination of data visualization and statistical models, we will analyze the returns and stock prices of some of the largest banks in America leading up to, and following the financial crisis. The banks which we will take a look at are:
* Bank of America (BAC)
* CitiGroup (C)
* Goldman Sachs (GS)
* JPMorgan (JPM)
* Morgan Stanley (MS)
* Wells Fargo (WFC)  

We will use Python (Google Colab) for our analysis. A .py & .ipynb file will be available. To get the data, we use the data function in the pandas_datareader library to scrap the data from Yahoo Finance. We get stock High, Low, Open, Close & Volume for each bank.    

## EDA  
We first take a look at the returns. The return is defined as percent difference of the stock's closing price. The peak for the stocks was around 0, which was expected, and it seems that the correlation among each bank was positive. However, when we break down the returns, we see there is a high volatility in the years 2009 & 2009, but then over time the volatility decreases again. We also look for the lowest and highest stock prices of the banks. We see that four of the banks had their lowest stock price on the same day!  

By plotting the closing prices of the banks, we find that they all crash approximately at the same time, however some banks like CitiGroup and Goldman Sachs, crash a lot harder than the rest. They all recover at their own pace. We decompose the 'Observed' closing price of each bank into three components; 'Trend', 'Seasonal' & 'Residual'. This helps us see the general trend the stock is following and we also see the seasonal pattern. However, we note that for some of the stocks, the 'Seasonal' is almost negligible as the 'Residual' values are much greater.  

We also take a look at a 7 day and 30 day moving average for the stocks, to better see the trend as this smooths out the curve. However, even with the smoothing effect, the crash is still very noticible from late 2008 to early 2009. Finally, we construct a heatmap of the correlation of closing prices for each bank. We notice that most of these values are positive (with some extremely high correlations like Morgan Stanley with Bank of America or CitiGroup with Bank of America), which leads us to believe that if one of the bank is up on the day, then most of the other banks are also up. This is also further shown in the first plot we create, as the returns for the banks generally follow a positive trend.