# LSTM-for-Cryptocurrency-price-forecast
In this project, I use Deep Learning, namely a RNN made of LSTM units to predict the bitcoin market price based on 5 input features

Dataset attained from: https://coinmarketcap.com/

The Kaggle version of the dataset in csv format: https://www.kaggle.com/mczielinski/bitcoin-historical-data

Brief description of data:
Usually in RNNs the data is 3 dimensional i.e. [data_examples (i.e. samples), valued_per_time_step (i.e. inputs),time_steps( the sequence length)]

Usually for stock prediction, there are 5 features present: open, close, low, high and volume price. The goal is to predict the future price i.e. the future 'close' price. Hence, the input vector_size = 5.

Generally; stock prices are a time series of N length, and I need to feed in the data using a sliding window of fixed size w, everytime I move the window to the right by size w (to prevent overlap)

Additionally, I will have to normalise the data, since stock indexes increases in time, and the thus the data in train will not be the same as the test which negates the generalisation! 
i.e. most values in test set are likely to be out of the scale of the train set and thus model has to predict numbers it has never seen before! 
this will result in a poor prediction. 
therefore to sove this issue, I normalise the prices in each sliding window and the task becomed predicting the relative change rates instead of the absolute values.
