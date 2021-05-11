# Stock Price Time Series Prediction Based on ARIMA Model 

Note: Assignment2 uses LSTM, which is deep learning method to predict Maotai stock price; Assignment3 still uses the Maotai database, but applies the ARIMA Model to do the prediction.

## 1. ADF Unit Root Test:

(1) Result: 2.621 >> t-value

(2) First-Order Difference:

Result: -11.1266 < t-value  ->  _**Reject Null Hypothesis; Unit Root does not exist**_

## 2. ARIMA Fitted:

```
train_results = sm.tsa.arma_order_select_ic(ts1, ic=['aic', 'bic'], trend='nc', max_ar=8, max_ma=8) 
train_results.aic_min_order #建立AIC值最小的模型 
```

Result: AIC (8, 8)

Therefore, ARIMA(8,1,8)

```fig = model.plot_predict(5,4000)```

![image](https://user-images.githubusercontent.com/78721777/117769816-c36c6000-b266-11eb-9e10-91e98f85d599.png)

## 3. Model Evaluation:

score: 0.9992795964853614;

It is much more approach to 1, which we think this is an enough good model
