> # BITCOIN PRICE FORECASTING
> ## TIME SERIES APPROACH

 ![image](https://github.com/drykvf/Bitcoin_Pred_022023/assets/121190573/bec33cef-98b2-43ad-b46a-2099fafe8db5)
 

***This project aims to forecast future bitcoin price based on historical bitcoin price data by time series approach. In time series analysis, time is a crucial variable of the data, because it shows us how the data adjusts over the course of the data points as well as the result.***

Date		: June 2, 2023

Authors	: [Hera K.](https://www.linkedin.com/in/hera-k-80b05322a/)
 
# 1.	TABLE OF CONTENTS
 
•	Introduction 

•	The Business Problem

	  Work System of Bitcoin

	  History of Bitcoin

	  Difference Between Crypto & Currency

•	The Data 

	  Data Preparation

•	Methods & Model

•	Evaluation

•	Furthermore

•	Repository Structure

# 2.	INTRODUCTION

This project is created through a combination of the skills I have learned in the Data Science program at Flatiron School. 
Time series is a specific way of analyzing a sequence. It can show likely changes in the data, like seasonality or cyclic behavior, which provides a better understanding of data variables and helps forecast better. 


# 3.	THE BUSINESS PROBLEM

Bitcoin emerged as a virtual currency to challenge the existing centralized system after 2008 financial crisis. Bitcoin the first and most well-known cryptocurrency was created by a Japanese American man living in California, in 2009 by an individual or group of individuals using the pseudonym Satoshi Nakamoto. 

Bitcoin is created, distributed, traded, and stored using a decentralized ledger system known as a blockchain. Bitcoin and other cryptocurrencies are not currently considered real money by the federal reserve or U.S. banks. However, it’s managed by blockchain technology and verified by all users on the network. 
The main difference between the traditional currency and bitcoins are that traditional currency is a centralized system and bitcoins are decentralized one and peer-peer systems without any intermediary. No single person or group has control—instead, all users collectively retain control.
In a traditional banking system, for a national transaction takes 2-3 working days, and the transaction fees will be high. In the case of international transactions, the transaction fee will be much higher, and it will take 15 days to complete the transaction. In a Cryptocurrency system like bitcoins, there is no transaction fee for both national transaction and globally. The transaction will also take place in seconds or within 24 hours, as a bitcoin system function 24/ 7. Because this blockchain system is a distributed, immutable, and decentralized ledger at its core that consists of a chain of blocks and each block contains a set of data. The blocks are linked together using cryptographic techniques and form a chronological chain of information. Decentralized blockchains are immutable, which means that the data entered is irreversible.  For Bitcoin, transactions are permanently recorded and viewable to anyone.


## A.	Work System of Bitcoin

i.	i.	In short, a centralized digital network is a network in which collective data is processed and stored by a single node. Conversely, a decentralized digital network is a network in which multiple nodes store and process data. A store of value is an asset, currency, or commodity that maintains its value over a long period.  An item would be considered a store of value if its value is either stable or increases over time but doesn't depreciate. Bitcoin is proving to be a legitimate store of value is its scarcity.
ii.	Cash is issued by a government, cryptocurrency is not. Crypto isn't controlled by an individual, institution, or any other authority.

## B.	History of Bitcoin

i.	Highlighted outstanding events chrolonogically.

	2008 – Invented by Satoshi Nakamoto

	2009 – The bitcoin began its use a open-source

	2011 – The largest decrease occurred as a percentage of the coin’s value

	2013 – BTC is $ 1 in globe market

	2017 – A rise in prices, bitcoins were worth ±$998

	2021 – El Salvador was the first country who adopted BTC as legal tender 

	2023 – Tesla sold 75 % of its BTC holdings changed the market

## C.	Difference Between Crypto & Currency

i.	The most important difference is centralized- decentralized system as mentioned above particularly. Difference of their storage determines the value of asset.

ii.	Bitcoin is limitless and centered globally, cash is dependent on government’s policy or other lots of factors.

iii.	Cash system has brought about significant obstacles resulting from pandemic crisis, then global economic downturn, economy has been almost over.

i.	The most important difference is centralized- decentralized system as mentioned above particularly. Difference of their storage determines the value of asset.
ii.	Bitcoin is centered globally; cash is dependent on government’s policy or other lots of factors.
iii.	Cash system has brought about significant obstacles resulting from pandemic crisis, then global economic downturn, economy has been almost over.

To come up with a long-lasting solution, the world needs innovative and robust perspective for global system. Increasing demand worldwide makes Bitcoin much more attractive, though it looks like untrusty and jeopardous venture for now. Bitcoin prices are tried to be predicted by investors or majority. Bitcoin is aspiring critical up-and-coming for future as it ensures an analytical, favorable, strategic system emerging in digitalized world. it will be enabled to invest wisely.

 ![image](https://github.com/drykvf/Bitcoin_Pred_022023/assets/121190573/794ddc98-5642-4d3f-9028-d7bb471fc429)


# 4.	THE DATA

I have bitcoin dataset from Bitcoin yahoo finance source, the dataset consists of date, opening, closing prices of bitcoin, high and low price as well, adjusted closing price, volume from September 2014 to May 2023.
Now, as a source, I capture the dataset as Historical Data, csv file from yahoo finance website.
Yahoo Finance ( https://finance.yahoo.com/quote/BTC-USD/ )
I have four targets: open, close, low and high prices. Columns in my dataframe are explained as below. Bitcoin price operates 24 hours a day nonstop. All entries emphasize daily prices for this dataset.

**Date:** Index in our time series that specifies the date associated with the price. (USD)

**Open Price:** The first price of BTC was purchased on the trading day (USD)

**Close Price:** The last price of BTC was purchased at the end of trading day (USD)

**High:** The maximum price of BTC was purchased on trading day (USD)

**Low:** The minimum price of BTC was purchased on the trading day (USD)

**Adjusted Closing Price:** Stock exchanges witness buying and selling of millions of shares every minute. When the exchanges close, the last trading price of the stock is recorded as the closing price of the share. Data is adjusted using appropriate split and dividend multipliers, adhering to Center for Research in Security Prices (CRSP) standards (USD)

**Volume:** The sum of actual trades made during the trading day (USD)

•	All Time High $68,789.63 USD.         in 2021-11-10

•	Max Volume 350,967,941.479 USD in 2021-02-26

## A.	Data Preparation

i.i.	I retrieve my csv file with parse_date method, it changes the given string from a datetime to the desired format into the dataframe. Then I implement EDA (Exploratory Data analysis)

ii.	I check duplicated columns, null/ missing info, general dataframe and columns information. 

iii.	I visualize significant points to explore the data more interpretably for modelling. 

iv.	I check my data stationary thanks to the p-value by Dickey Fuller test result, then I implement ACF, PACF plots before modelling and to determine which terms are needed, what kind of model I would use. (The details and graphs are available in method and model parts).

I check whether my data is stationary or not via ACF, PACF graphs and Dickey Fuller Test. 
ACF is an Autocorrelation Function is that the correlation between the observation at the current time spot and the observations at previous time spots. Its plot provides answers about if the observed time series white noise or random, makes us to decide if I need to use MA term (q) in my model. 

PACF is a Partial Autocorrelation Function is a statistically technique to assess the direct link between an observation at a given lag and its preceding delays. That means it subtracts the impact of the further delays between two-time series to assess the correlation between their values at a certain lag. It helps to decide for AR term (p). 

The augmented Dickey-Fuller test is an extension of the standard Dickey-Fuller test, which also checks for both stationarity and non-stationarity in the time series. My closing price is obviously non-stationary, it should be differenced for the best forecasting. To make stationary it; there is some couple ways. I can make stationary by differencing method (as mentioned above figures), or I use differencing method thanks to the ARIMA and SARIMAX Integrated term model.

The below figures belong to 1st differenced of close_ts (close_diff = differenced close_ts; closing time series price). It looks stationary according to the Dickey Fuller test result as well. My p-value is 8.043183725372062e-16 less than alpha (threshold), that means my differenced close_ts data is stationary.

<img width="394" alt="image" src="https://github.com/drykvf/Bitcoin_Pred_022023/assets/121190573/c0fa7240-be52-40f7-ba2d-7773ff505fe6">


1st Differenced Close Price Time Series - ACF & PACF!

![ACF   PACF](https://github.com/drykvf/Bitcoin_Pred_022023/assets/121190573/cb3390d4-5dfc-4c0f-9c97-fc59db63bc45)


Furthermore, it displays a blue area in the ACF and PACF plots, which depicts the 95% confidence interval and is in indicator for the significance threshold. That means, anything within the blue area is statistically close to zero and anything outside the blue area is statistically non-zero.

<img width="432" alt="image" src="https://github.com/drykvf/Bitcoin_Pred_022023/assets/121190573/8e119b15-2936-4442-b45b-874e74dcf006">


# 5.	METHODS & MODELS

Time series method as a forecast is useful tool for decision-making.  Time is a crucial variable of the data because main working principle of forecast includes projections showing how one variable affects another one over time.  As well as that helps people to evaluate the options and select the best one, prepare for contingencies to take appropriate actions.

I focus on daily price at first glance, because daily open and close price causes to get profit. I don’t need to resample it because it is already my daily closing price is provided in my original dataset. Because of instability in my dataset, I can apparently see trend, seasonality on my visualization. 

I use naïve basic model. Then I go further with ARIMA (Autoregressive Integrated Moving Average model and SARIMAX (Seasonal Autoregressive Integrated Moving Average) method for daily closing price. 

# 6.	DAILY CLOSING PRICE MODELS 

## A.	NAÏVE MODEL

i.	The naïve approach is an estimating technique in which the last period's actuals are used as this period's forecast, without adjusting them or attempting to establish causal factors. It is used only for comparison with the forecasts generated by the better (sophisticated) techniques. Because it concerns what happened in the previous period and predicts the same thing will happen. 

<img width="432" alt="image" src="https://github.com/drykvf/Bitcoin_Pred_022023/assets/121190573/cf473c38-c713-464c-a45d-1de13fb51160">

RMSE test error: 17854

The naïve model forecast graph is displayed above, it is not pretty much god prediction to interpret. Naive method isn’t suited for datasets with high variability. My root mean squared error is very high. 
I should try different methods and parameters for better prediction. 

## B.	ARIMA MODEL

ARIMA model is useful in the cases where the time series is non-stationary. And the differencing is required to make the time series stationary. Most often, it happens when the data is non-stationary the predictions, we get from the ARIMA model are worse or not that accurate. I will use ARIMA model because of the non-stationary data, I need to specify AR and MA terms for my model.
ARIMA models are denoted with the notation seasonal parameter as well as ARIMA(p, d, q). These three parameters emphasize seasonality, trend, and noise in data.

•	The 1st parameter corresponds to the lagging (past values - AR term),
•	The 2nd corresponds to differencing (this is what makes non-stationary data stationary- differencing/ integration order),
•	The 3rd parameter corresponds to the white noise (for modeling shock events- MA term- moving average lags).


<img width="432" alt="image" src="https://github.com/drykvf/Bitcoin_Pred_022023/assets/121190573/fbcdc3d5-a3a8-4315-838e-2c946619ce23">


As seen above figure, the lowest train RMSE is 740, lowest AIC is 43073; although both AIC and RMSE train score is very high.  Let's plot and see all predictions comparing to my train and test data.


<img width="432" alt="image" src="https://github.com/drykvf/Bitcoin_Pred_022023/assets/121190573/f2a933f8-f6f8-4285-b088-cf201f0a3b4e">

I will forecast the BTC price for Prediction 3. Because it has the lowest RMSE and AIC among the other models. Let's score my test RMSE.

 ARIMA MODEL - ar_3 FORECAST!
 
 <img width="432" alt="image" src="https://github.com/drykvf/Bitcoin_Pred_022023/assets/121190573/c489138b-b3b2-4e50-8dba-ecd46de34541">

Train RMSE:740

Test RMSE: 17673.253151608238.

It is obviously extreme score my test error. As seen above forecast graph and error scores, ARIMA models don't work well. It explains that the model is not working well for daily prediction. 

# 7.	MONTHLY CLOSING PRICE MODELS 

## A.	Resampling Closing Price Monthly

I use the same method for ‘Monthly Closing Price’. I resample my daily closing price as ‘Monthly’. It is non-stationary because of outlier or booming BTC price in 2021 abruptly

<img width="432" alt="image" src="https://github.com/drykvf/Bitcoin_Pred_022023/assets/121190573/1ef48154-3eab-4c2b-acd3-31a15e2075e0">


**BTC Monthly Closing Price**

<img width="432" alt="image" src="https://github.com/drykvf/Bitcoin_Pred_022023/assets/121190573/4271608c-6427-41cb-8f35-bd5d99686183">

I decompose my monthly closing time series into distinct components such as trend, seasonality, and noise.
The below diagnostic plot is not perfect, I can see that the range of trend and residual is pretty much different range, I can say that trend is having variation between 20K to 40K, and most of the time residual is having the variation around until 2021, it has an extreme range after 2021.

<img width="432" alt="image" src="https://github.com/drykvf/Bitcoin_Pred_022023/assets/121190573/e61027ad-7005-40c6-80b6-4aecef8b6f8f">


   **Decomposition Monthly**

![Decomposition Monthly BTC](https://github.com/drykvf/Bitcoin_Pred_022023/assets/121190573/3a4be8e8-1b32-4adf-a769-4786be2c77b4)


## B.	SARIMAX MODEL based on MONTHLY CLOSING PRICE

SARIMAX, Seasonal Autoregressive Integrated Moving Average commonly used as a method for time series forecasting. SARIMAX models have same parameters with ARIMA (p,d,q), in addition to that they differentiate with the notation seasonality and eXogenous factors than ARIMA. SARIMAX is a seasonal equivalent model like SARIMA and Auto ARIMA.
Some parameters combinations between 0-3 range for p, d, q ais created for Seasonal ARIMA. According to monthly closing price the best minimum AIC score to find the most optimal parameter combination among them for the best performance model. 

The lowest AIC score:  10.0
Parameter: ARIMA (1, 0, 1) x (0, 1, 2, 12) 12  
This is the lowest combination, but this doesn’t work, because of singular matrix.

The second lowest AIC score: 1078.75
Parameter: ARIMA (2, 2, 2) x (2, 2, 1, 12) 12 
I use these parameters for my SARIMAX model, SAR_2 below.

<img width="432" alt="image" src="https://github.com/drykvf/Bitcoin_Pred_022023/assets/121190573/c63f44b1-7ae1-4fa3-81b2-ac157c4757ad">


**SAR_2 MODEL**

<img width="432" alt="image" src="https://github.com/drykvf/Bitcoin_Pred_022023/assets/121190573/010acf3d-6f81-45a8-86dc-94fd00153063">


RMSE Train error: 3404.50 ( Expected Root Mean Squared Error )
AIC SAR model : 1078.75  ( Akaike Information Criteria)
RMSE Test error: 3379.18  (Forecast Root Mean Squared Error) 

<img width="432" alt="image" src="https://github.com/drykvf/Bitcoin_Pred_022023/assets/121190573/720fabc2-1706-427b-a70a-b9782e2b98a2">

I will compare predicted BTC price to real BTC prices of the time series, to explore the accuracy of my forecasts. Then I will set forecasts to start 2021-12-31 to the end of the data
Actual data: close price monthly
Prediction: 2021-12-31 and further

<img width="432" alt="image" src="https://github.com/drykvf/Bitcoin_Pred_022023/assets/121190573/cefb81a2-fd45-40a5-acb4-f27bfcd26e07">

The above line graph displays that the Actual values is compared to the rolling forecast prediction. My forecast aligns with the actual values well. It shows a downward trend starts at the last of 2021, after 2023 it starts to be upward. In above graph, it is obviously seen the forecasting line is almost lying on the given values for this model. I don't even require the differencing method. Using this model now, I can predict the future values too.

AIC SAR model: 1078.75 ( Akaike Information Criteria)
RMSE Train error: 3404.50 (Expected Root Mean Squared Error)
RMSE Test error: 3379.18 (Forecast Root Mean Squared Error) 

Forecast for 2024- 1 Yearly BTC Price (USD)

![Forecast 2024 BTC](https://github.com/drykvf/Bitcoin_Pred_022023/assets/121190573/ae1d4e03-e377-48cc-b0c0-058cff72a123)


Forecast 3 Yearly BTC Price (USD)

![Forecast 3 Yearly BTC](https://github.com/drykvf/Bitcoin_Pred_022023/assets/121190573/489252b2-a506-4a02-9ea6-d6003aa890ff)


Forecast 8 Yearly BTC Price (USD)

![Forecast 8 Yearly BTC](https://github.com/drykvf/Bitcoin_Pred_022023/assets/121190573/1889f23a-3791-49b7-912b-4f9bd6efaa38)


# 8.	EVALUATION
A high-quality forecast features the accurate, timely, clear & understandable, relevant specifications.
Accurate is important, enough to get a good evaluation for determination about plans or how we can take a position.
A good forecast gives the information when needed, so it is a timely result, gives idea when the situation will occur.
I report both the RMSE and AIC score in my project to compare and evaluate my models. 



























