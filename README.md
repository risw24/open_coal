# Open Coal Price Forecast

This is my academic project in Data Mining Course (June 2022) in Faculty of Computer Science University of Indonesia. I do this project with my partner Hilmy Akbar. This forecasting is using Time Series Analysis with ARIMA model and do some other explnatory analysis.

## 1. Input
We get open coal price from https://markets.businessinsider.com/commodities/coal-price. From the data, we using data from 1 Jan 2021 - 1 Jan 2022 to make forecasting model to predict open coal price after that.
## 2. Data Analysis
![alt text](https://github.com/risw24/open_coal/blob/master/image/Open%20Coal%20Graph.png?raw=true)
Open coal price increased in October - November because coal is used by Europeans to face winter. So, when the demand is increased, the open coal price is increased too.
Beside that, there is no seasonalities in this graph because there is no seasonally repeating pattern.

![alt text](https://github.com/risw24/open_coal/blob/master/image/Open%20Coal%20with%20mean%20std.png?raw=true)
The mean and standard deviation in this graph is constant and it indicate this graph is stationar.
It also strengthened with ADF test. The result is p-value <0.05. It indicate the stationary of this graph is correct.

## 3. Forecast Model and Evaluation
Because this data is stationar and does'nt have seasonality, the forecast model is using ARIMA model
### Model 1 : ARIMA using all data to predict

![alt text](https://github.com/risw24/open_coal/blob/master/image/model%201.png?raw=true)

![alt text](https://github.com/risw24/open_coal/blob/master/image/model%201%20forecasting.png?raw=true)
Evaluation :
<br/>
MAE : 45.8<br/>
RMSE: 58.1
<br/>
It can be concluded that the average difference in results is 45.8 with a not so large error marked by the RMSE value.
<br/>
Estimated results until January - February the open coal price is between 50 - 100
### Model 2 : Out-of-Time Cross validation (Training = 70%)
![alt text](https://github.com/risw24/open_coal/blob/master/image/model%202.png?raw=true)

![alt text](https://github.com/risw24/open_coal/blob/master/image/model%202%20forecasting.png?raw=true)
Evaluation :
<br/>
MAE : 98.2<br/>
RMSE: 107.0
<br/>
It can be concluded that the average difference in results is 98.2 with a very large error marked by a large RMSE value.
<br/>
The result of the open coal price forecast for January - February 2022 is slightly above the price of 50.
### Model 3: Out-of-Time Cross validation (Training = 85%)
![alt text](https://github.com/risw24/open_coal/blob/master/image/model%203.png?raw=true)

![alt text](https://github.com/risw24/open_coal/blob/master/image/model%203%20forecasting.png?raw=true)
Evaluation :
<br/>
MAE : 54.2<br/>
RMSE: 62.2
<br/>
It can be concluded that the average difference in results is 54.3 with a not so large error indicated by the RMSE value.
<br/>
The estimated results of the open coal price during January - February 2022 range from 50 - 100.
## 4. Conclusion
The best model obtained is Model 1, which does not apply Cross Validation because of the high level of accuracy, namely MAE: 45.8.
<br/>
This is also supported by the Time Series chart of Open Coal Prices where in October and November increase drasticaly. So if we use Cross Validation that uses data for that month, it will produce a fairly large error.
