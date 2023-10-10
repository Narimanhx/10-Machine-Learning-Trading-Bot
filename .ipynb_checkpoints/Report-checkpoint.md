## Establish a Baseline Performance

For the OHLCV dataset provided, the SMA technique was used for training the model with a short window equal to 4 and a long window equal to 100. Then, was used the support vector machine (SVM) learning method to fit the training data and make predictions based on the testing data.

![Classification Report](images/report_window_4_100.png)



![Actual Return VS Strategy Return](images/return_window_4_100.png)

Observing the graph, it is possible to visualize that the Strategy return  had a higher cumulative return over the Actual return


## Tune the Baseline Trading Algorithm


### Step 1: Tune the training algorithm by adjusting the size of the training dataset. 

The dataframe was sliced into 5 months instead of the initial 3 months, showing a strong difference in the return on the strategy.

![Classification Report](images/report_window_4_100-5_months.png)



![Actual Return VS Strategy Return](images/return_window_4_100-5_months.png)

Increasing the training window caused the impact where the trade improved in the areas of similar occurrences, however it caused a significant decline when the trade changed direction.
On the other hand, reducing the training window caused a constant negative impact on the return of the strategy.

### Step 2: Tune the trading algorithm by adjusting the SMA input features. 

![Classification Report](images/report_window_4_110-5_months.png)



![Actual Return VS Strategy Return](images/return_window_4_110-5_months.png)

Keeping the trade size at 5 months and increasing the long window to 110 achieved an improvement in the recall, however the return of the strategy was extremely inferior.
Further changes up or down the window also showed unpleasant results.

### Step 3: Choose the set of parameters that best improved the trading algorithm returns. 


![Classification Report](images/report_window_4_110.png)



![Actual Return VS Strategy Return](images/return_window_4_110.png)

By keeping the size training at 3 months and changing the long window to 110, it was possible to obtain a small increase in the return of the strategy. Other changes, both upwards and downwards, achieved a decline in the return of the strategy.