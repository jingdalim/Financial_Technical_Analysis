# Financial_Technical_Analysis
Comparing returns from  simple buy-and-hold strategy for SingPost stock with simple moving average technical analysis strategy

## Content Page
1. Executive Summary
2. Data cleaning
3. Exploratory Data Analysis
4. Comparing Buy-and-hold and Simple Moving Average Technical Analysis Strategies
5. Dummify Categorical Data
6. Predicting Closing Price using Machine Learning (ML) Models
7. Limitations and Next Steps

## 1. Executive Summary
**Objective**

Comparing returns from simple buy-and-hold strategy for SingPost stock with simple moving average technical analysis strategy.

**Data Source**

Obtained from [Alpha Vantage](https://www.alphavantage.co/). Alpha Vantage provides daily financial market data through APIs.

**To Do**

Step 1: Connect to JSON API

Step 2: Convert JSON data to Pandas DataFrame

Step 3: Engineer new features and visualise stock price information

Step 4: Compare returns from simple buy-and-hold strategy for SingPost stock with simple moving average technical analysis strategy.

Step 5: Dummify categorical data for use in Machine Learning (ML) models

Step 6: Predict Closing Price using Machine Learning (ML) Models

## 2. Data Cleaning

1. Import necessary libraries
2. Connect to JSON API
3. Convert JSON data to Pandas DataFrame
3. Check for null values

## 3. Exploratory Data Analysis

**Fig 1: SingPost Stock Price**

![image](https://user-images.githubusercontent.com/74403956/121787264-ade8ae00-cbf7-11eb-8ce6-0339cd871342.png)

**Fig 2: Singpost Daily Return**

![image](https://user-images.githubusercontent.com/74403956/121787278-c953b900-cbf7-11eb-830f-1e22b213cb48.png)

**Fig 3: 50-day Moving Average vs. Close Price**

![image](https://user-images.githubusercontent.com/74403956/121787284-d375b780-cbf7-11eb-85fa-c482b8fd3bac.png)

**Fig 4: 200-day Moving Average vs. Close Price**

![image](https://user-images.githubusercontent.com/74403956/121787296-e7211e00-cbf7-11eb-8921-d20dd1e26a68.png)

**Fig 5: 50-day Moving Average vs. 200-day Moving Average**

![image](https://user-images.githubusercontent.com/74403956/121787322-03bd5600-cbf8-11eb-832c-618e25a133e8.png)

**Fig 6: Actual versus Predicted Price**

![image](https://user-images.githubusercontent.com/74403956/121787328-0c159100-cbf8-11eb-80dd-40b7f38e34a0.png)


## 4. Comparing Buy-and-hold and Simple Moving Average Technical Analysis Strategies

We wimm implement a buy-and-hold strategy and an SMA strategy (we buy or sell shares depending on the relative positions of the two SMA lines).

A "cross" occurs when two SMA lines cross each other. A golden cross is considered a bullish signal, i.e. favorable signal, and occurss when a short/intermediate-term SMA rises above the long-term SMA.

A death cross is considered a bearish signal, i.e. unfavorable signal, when the short/intermediate term SMA drops below the long-term SMA.

In our case, we buy when the 50-day SMA rises above the 200-day SMA and sell when the case is opposite. 

<img width="656" alt="Screenshot 2021-06-13 at 2 50 06 AM" src="https://user-images.githubusercontent.com/74403956/121787236-872a7780-cbf7-11eb-9e77-bd136e92513d.png">

<img width="994" alt="Screenshot 2021-06-13 at 2 50 51 AM" src="https://user-images.githubusercontent.com/74403956/121787248-9a3d4780-cbf7-11eb-92b1-9a2f8af5a320.png">

The buy-and-hold strategy returned 1.54% (from 65 to 66). The SMA crossover strategy returned 105.4% (from 65 to 133.5). At first glance it appears that the SMA crossover strategy is superior to the buy-and-hold strategy.

## 5. Dummify Categorical Data

Dummify categorical data using .get_dummies(), drop_first = True.

<img width="1007" alt="Screenshot 2021-06-13 at 2 38 03 AM" src="https://user-images.githubusercontent.com/74403956/121787227-77ab2e80-cbf7-11eb-85d0-159330ba6bcd.png">

## 6. Predicting Closing Price using Machine Learning (ML) Models
We will be predicting the closing price using the Linear Regression and Decision Tree models. We will compute the Root-Mean-Squared-Error (RMSE) of the models to determine their accuracy.

The RMSE of the Linear Regression model is 5.705018852367454e-06.

![image](https://user-images.githubusercontent.com/74403956/121787679-133d9e80-cbfa-11eb-855e-6fa38880aee4.png)

The RMSE of the Decision Tree model is 4.6892549800796745e-05.

![image](https://user-images.githubusercontent.com/74403956/121787672-07ea7300-cbfa-11eb-9140-736b96893bc3.png)

## 7. Limitations and Next Steps
At first glance, it appears that the SMA crossover strategy is superior to the buy-and-hold strategy. However, it is important to note that we only tested this on one stock. The variability of SingPost stock is not very high and it is likely that this is a fluke. The next step would be to try this strategy on more volatile stocks and on many more stocks.

Regarding the ML models, it might appear that the models are very accurate. However, we made use of the Daily Opening Price to predict the Daily Closing Price. The SingPost stock is not volatile, which would make it easier to predict the closing price. In addition, this was only tested on one stock. The models will need to be tested on more  volatile stocks. Furthermore, the model is unable to predict the stock price a few days into the future (which honestly is where the money's at). More sophisticated models will be required.

