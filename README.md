# Cryptocurrencies-Volatility-Prediction-RNN-LSTM-BiLSTM

The notebook of this repository contains python codes for prediction of cryptocurrencies volatility with RNN, LSTM, and BiLSTM models.
In quantitative finance, volatility refers to the conditional variance of the underlying asset returns, and it is a fundamental variable in risk management. 
Therefore, forecasting the volatility of cryptocurrencies is an important and challenging task. 
However, volatility is an unobservable variable, and it is not measurable. As standard deviation indicates how much a
cryptocurrency has varied during a certain period, we used this feature as a proxy for volatility. Therefore, Historical
Volatility at time t (HVt) was calculated as standard deviations of the price returns. The window of 30 days (~ one month od transactions) was used to calculate HVt.

![image](https://user-images.githubusercontent.com/46126394/193378292-a82046d4-12de-4cec-8882-628d799bb6a8.png)

5 most traded cryptocurrencies that have at least 4 years of data from 02/2018 to 02/2022 were selected to be used in experiments ("Bitcoin", "Ethereum", "XRP", "Cardano", "Binance Coin"). Data was collected from "investing.com" using the get API from the investpy library.
Each dataset was divided into two parts as training and testing sets based on the ratios of 80% and 20%. Besides, the last 20% of the training set was used for the purpose of hyper-parameter tuning. The goal is to use the last 6 day's data to predict historical volatility of next dat. In other words, given 𝐻𝑉𝑡−6, …, 𝐻𝑉𝑡−1, each model learns to predict the value of 𝐻𝑉𝑡. 
The most important hyper-parameters of the models were tuned using grid search method on the validation set. Consequently, each model's structures varied from one cryptocurrency to another as each model yields a specific set of optimal hyper-parameters for each cryptocurrency. 
The best configuration of each model for each cryptocurrency was evaluated on the relevant test set. 
The RMSE results and plots of "predicted Vs. Real" can be found inside the notebook. 
While the RNN was found to be the best model for three of the cryptocurrencies, the best models for the Binance_coin and XRP are BiLSTM and LSTM respectively. 
