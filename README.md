# LSTM Stock Predictor

![deep-learning.jpg](Images/deep-learning.jpg)

Due to the volatility of cryptocurrency speculation, investors will often try to incorporate sentiment from social media and news articles to help guide their trading strategies. One such indicator is the [Crypto Fear and Greed Index (FNG)](https://alternative.me/crypto/fear-and-greed-index/) which attempts to use a variety of data sources to produce a daily FNG value for cryptocurrency. You have been asked to help build and evaluate deep learning models using both the FNG values and simple closing prices to determine if the FNG indicator provides a better signal for cryptocurrencies than the normal closing price data.

In this assignment, I will use deep learning recurrent neural networks to model bitcoin closing prices. One model will use the FNG indicators to predict the closing price while the second model will use a window of closing prices to predict the nth closing price.

I have completed the following:

1. [Prepare the data for training and testing](#prepare-the-data-for-training-and-testing)
2. [Build and train custom LSTM RNNs](#build-and-train-custom-lstm-rnns)
3. [Evaluate the performance of each model](#evaluate-the-performance-of-each-model)

- - -


## Instructions

### Prepare the data for training and testing

- **FNG Model  - Example of Split, Scaled and Reshaped Data**

![](https://github.com/apfreeman/unit13-challenge/blob/main/Images/Prepared_X_fng.PNG?raw=true)

- **Close Model  - Example of Split, Scaled and Reshaped Data**

![](https://github.com/apfreeman/unit13-challenge/blob/main/Images/Prepared_X_close.PNG?raw=true)


### Build and train custom LSTM RNNs

- **Example - FNG Model Summary**

![](https://github.com/apfreeman/unit13-challenge/blob/main/Images/model_sum_fng.PNG?raw=true)


Finally, use the testing data to evaluate each model and compare the performance.

Use the above to answer the following:

- **Which model has a lower loss?**

**ANSWER:**: As demonstrated below the Close price model had a lower loss then the FNG model. FNG - **0.14951150119304657** vs Close - **0.05688522011041641**

- FNG

        5/5 [==============================] - 1s 6ms/step - loss: 0.1495
        0.14951150119304657

- Close

        5/5 [==============================] - 1s 5ms/step - loss: 0.0569
        0.05688522011041641



- **Which model tracks the actual values better over time?**

- **FNG Model Plot**

![](https://github.com/apfreeman/unit13-challenge/blob/main/Images/plot_fng.PNG?raw=true)

- **Close Model Plot**

![](https://github.com/apfreeman/unit13-challenge/blob/main/Images/plot_close.PNG?raw=true)

**ANSWER:**: As demonstrated by the FNG vs Close plots, the Close model tracks the actual values better over time. 

- **Which window size works best for the model?**



