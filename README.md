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

![](https://github.com/apfreeman/Unit-14-LSTM-Stock-Predictor/blob/main/Images/Prepared_X_fng.PNG?raw=true)

- **Close Model  - Example of Split, Scaled and Reshaped Data**

![](https://github.com/apfreeman/Unit-14-LSTM-Stock-Predictor/blob/main/Images/Prepared_X_close.PNG?raw=true)


### Build and train custom LSTM RNNs

- **Example - FNG Model Summary**

![](https://github.com/apfreeman/Unit-14-LSTM-Stock-Predictor/blob/main/Images/model_sum_fng.PNG?raw=true)


Finally, use the testing data to evaluate each model and compare the performance.

Use the above to answer the following:

- **Which model has a lower loss?**

    **ANSWER:** As demonstrated below the Close price model had a lower loss than the FNG model. FNG - **0.14951150119304657** vs Close - **0.05688522011041641**

- FNG

        5/5 [==============================] - 1s 6ms/step - loss: 0.1495
        0.14951150119304657

- Close

        5/5 [==============================] - 1s 5ms/step - loss: 0.0569
        0.05688522011041641



- **Which model tracks the actual values better over time?**

    - **FNG Model Plot**

    ![](https://github.com/apfreeman/Unit-14-LSTM-Stock-Predictor/blob/main/Images/plot_fng.PNG?raw=true)

    - **Close Model Plot**

    ![](https://github.com/apfreeman/Unit-14-LSTM-Stock-Predictor/blob/main/Images/plot_close.PNG?raw=true)

    **ANSWER:** As demonstrated by the FNG vs Close plots, the Close model tracks the actual values better over time. 

- **Which window size works best for the model?**

    **ANSWER:** The FNG Model was fit with batch sizes of 2,3,5,10 and 20 to evaluate which is the best window size for the model. All loss values are below.   
    - Batch size = 1  - 0.14951150119304657
    - **Batch size = 2  - 0.10420552641153336** 
    - Batch size = 3  - 0.1110898107290268 
    - Batch size = 5  - 0.13134555518627167 
    - Batch size = 10  - 0.1320107877254486
    - Batch size = 20  - 0.1487315595149994 

    The window size that works best for the FNG data model is 2.

    **ANSWER:** The Close Model was fit with batch sizes of 2,3,5,10 and 20 to evaluate which is the best window size for the model. All loss values are below.   
    - Batch size = 1  - 0.05688522011041641
    - Batch size = 2  - 0.02556442655622959 
    - Batch size = 3  - 0.018078893423080444 
    - Batch size = 5  - 0.00849858857691288 
    - **Batch size = 10  - 0.006939881481230259**
    - Batch size = 20  - 0.00687668239697814 

    The window size that works best for the FNG data model is 10, while it is demonstrated that a window size of 20 is slightly better anything after 10 yields diminishing returns and does not represent a significant improvement. As such 10 would be a good choice.

## FNG Evaluation and Plots experimenting with batch and window sizes

- **Batch size = 2**

![](https://github.com/apfreeman/Unit-14-LSTM-Stock-Predictor/blob/main/Images/plot_fng_batchsize_2.PNG?raw=true)

- **Batch size = 3**

![](https://github.com/apfreeman/Unit-14-LSTM-Stock-Predictor/blob/main/Images/plot_fng_batchsize_3.PNG?raw=true)

- **Batch size = 5**

![](https://github.com/apfreeman/Unit-14-LSTM-Stock-Predictor/blob/main/Images/plot_fng_batchsize_5.PNG?raw=true)

- **Batch size = 10**

![](https://github.com/apfreeman/Unit-14-LSTM-Stock-Predictor/blob/main/Images/plot_fng_batchsize_10.PNG?raw=true)

- **Batch size = 20**

![](https://github.com/apfreeman/Unit-14-LSTM-Stock-Predictor/blob/main/Images/plot_fng_batchsize_20.PNG?raw=true)

- **Window size = 1**

![](https://github.com/apfreeman/Unit-14-LSTM-Stock-Predictor/blob/main/Images/plot_fng_windowsize_1.PNG?raw=true)

- **Window size = 5**

![](https://github.com/apfreeman/Unit-14-LSTM-Stock-Predictor/blob/main/Images/plot_fng_windowsize_5.PNG?raw=true)

### Summary of experiements with the batch size and window size

The FNG model and predictions overall are not great for predicting bitcoin price movements using the fear and greed data. 

Analysing the output, the best batch size was determined to be 2 as this produced the lowest loss score. 

On analysing the window size, lowering from 10 to 5 did not yield a significant improvement. Lowering the window size further to 1 produced a slight improvement in the loss score but approached over fitting.  


## Close price Evaluation and Plots experimenting with batch and window sizes

- **Batch size = 2**

![](https://github.com/apfreeman/Unit-14-LSTM-Stock-Predictor/blob/main/Images/plot_close_batchsize_2.PNG?raw=true)

- **Batch size = 3**

![](https://github.com/apfreeman/Unit-14-LSTM-Stock-Predictor/blob/main/Images/plot_close_batchsize_3.PNG?raw=true)

- **Batch size = 5**

![](https://github.com/apfreeman/Unit-14-LSTM-Stock-Predictor/blob/main/Images/plot_close_batchsize_5.PNG?raw=true)

- **Batch size = 10**

![](https://github.com/apfreeman/Unit-14-LSTM-Stock-Predictor/blob/main/Images/plot_close_batchsize_10.PNG?raw=true)

- **Batch size = 20**

![](https://github.com/apfreeman/Unit-14-LSTM-Stock-Predictor/blob/main/Images/plot_close_batchsize_20.PNG?raw=true)

- **Window size = 1**

![](https://github.com/apfreeman/Unit-14-LSTM-Stock-Predictor/blob/main/Images/plot_close_windowsize_1.PNG?raw=true)

- **Window size = 5**

![](https://github.com/apfreeman/Unit-14-LSTM-Stock-Predictor/blob/main/Images/plot_close_windowsize_5.PNG?raw=true)

### Summary of experiments with the batch size and window size

The Close model and predictions overall are fairly good for predicting bitcoin price movements using the close price data. 

Analysing the output, the best batch size was determined to be 10 as this produced a good loss score. Any increase in batch size further did not result in significant improvement. 

On analysing the window size, lowering from 10 to 5 did not yield a significant improvement. Lowering the window size further to 1 produced a significant improvement in the loss score but approached over fitting.  