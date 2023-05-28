# BITCOIN PRICE FORECASTING
# TIME SERIES APPROACH

 ![image](https://github.com/drykvf/Bitcoin_Pred_022023/assets/121190573/bec33cef-98b2-43ad-b46a-2099fafe8db5)
 

* **This project aims to forecast future bitcoin price based on historical bitcoin price data by time series approach. In time series analysis, time is a crucial variable of the data, because it shows us how the data adjusts over the course of the data points as well as the result.** *

Date		: June 2, 2023

Authors	: Hera K.
 
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

This project is created as a capstone project through a combination of the skills I have learned in the Data Science program at Flatiron School. 
Time series is a specific way of analyzing a sequence. It can show likely changes in the data, like seasonality or cyclic behavior, which provides a better understanding of data variables and helps forecast better. 

# 3.	THE BUSINESS PROBLEM

Bitcoin emerged as a virtual currency to challenge the existing centralized system after 2008 financial crisis. Bitcoin the first and most well-known cryptocurrency was created by a Japanese American man living in California, in 2009 by an individual or group of individuals using the pseudonym Satoshi Nakamoto. 

Bitcoin is created, distributed, traded, and stored using a decentralized ledger system known as a blockchain. Bitcoin and other cryptocurrencies are not currently considered real money by the federal reserve or U.S. banks. However, it’s managed by blockchain technology and verified by all users on the network. 
The main difference between the traditional currency and bitcoins are that traditional currency is a centralized system and bitcoins are decentralized one and peer-peer systems without any intermediary. No single person or group has control—instead, all users collectively retain control.
In a traditional banking system, for a national transaction takes 2-3 working days, and the transaction fees will be high. In the case of international transactions, the transaction fee will be much higher, and it will take 15 days to complete the transaction. In a Cryptocurrency system like bitcoins, there is no transaction fee for both national transaction and globally. The transaction will also take place in seconds or within 24 hours, as a bitcoin system function 24/ 7. Because this blockchain system is a distributed, immutable, and decentralized ledger at its core that consists of a chain of blocks and each block contains a set of data. The blocks are linked together using cryptographic techniques and form a chronological chain of information. Decentralized blockchains are immutable, which means that the data entered is irreversible.  For Bitcoin, transactions are permanently recorded and viewable to anyone.

## A.	Work System of Bitcoin

i.	In short, a centralized digital network is a network in which collective data is processed and stored by a single node. Conversely, a decentralized digital network is a network in which multiple nodes store and process data. A store of value is an asset, currency, or commodity that maintains its value over a long period.  An item would be considered a store of value if its value is either stable or increases over time but doesn't depreciate. Bitcoin is proving to be a legitimate store of value is its scarcity.

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

To come up with a long-lasting solution, the world needs innovative and robust perspective for global system. Increasing demand worldwide makes Bitcoin much more attractive, though it looks like untrusty and jeopardous venture for now. Bitcoin prices are tried to be predicted by investors or majority. Bitcoin is aspiring critical up-and-coming for future as it ensures an analytical, favorable, strategic system emerging in digitalized world. To forecast bitcoin future prices will guide for more entrepreneurs in finance world, it will be enabled to invest wisely.
 ![image](https://github.com/drykvf/Bitcoin_Pred_022023/assets/121190573/ff7b0b13-667f-475e-bd4d-b20926187919)
 
# 4.	THE DATA

I have bitcoin dataset from Bitcoin yahoo finance source, the dataset consists of date, opening, closing prices of bitcoin, high and low price as well, adjusted closing price, volume from September 2014 to May 2023.
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

i.	I call my csv file with parse_date method, it changes the given string from a datetime to the desired format into the dataframe. Then I implement EDA (Exploratory Data analysis)

ii.	I check duplicated columns, null/ missing info, general dataframe and columns information. 

iii.	I visualize significant points to explore the data more interpretably for modelling. 

iv.	I check my data stationary thanks to the p-value by Dickey Fuller test result, then I implement ACF, PACF plots before modelling and to determine which terms are needed, what kind of model I would use. (The details and graphs are available in method and model parts).



