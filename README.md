# StockPricePrediction using Transformers
## prediction of closing price of S&P 500 index

Began with encoding Day/Month/Year sine/cosine to capture temporal connection of days

Scaled other parameters by removing the mean and dividing by std

First approach was a simple LSTM to grasp what the baseline is - MAPE around 18

Created baseline Transformer to see how this architecture performs - MAPE around 17

Experimented with varius hiper parameters of Transformer - turns out architecture doesn't really matter, what matters is length of sliding window

#### Breakthrough - new way of training: Stratified Time Series Split

Need to implement it on my own

Also learned that sMAPE is a good metric for such prediction problems so I also implemented that

Got great results

### Results:
SOTA - MAPE around 1-2

LSTM baseline - MAPE around 17-20

Transformer baseline - val MAPE around 18, but train MAPE was around 30%

Transformer with StratiiedTimeSeriesSplit - MAPE around 5 - great!!!

### TODO:
- experiment with hyperparameters of the best model yet
- use Time2Vec
- add other index data in the input data for prediction
- experiment with other stocks/indces
