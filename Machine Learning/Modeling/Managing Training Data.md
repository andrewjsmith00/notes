In order for a model to generalise when performing [[Model Training]], we don't want to give the model all of the training data when training. Instead we can hold some back to validate the model and see if it is generalising or if it is just memorising results.
You can segment out around 20-30% of the data to be used as testing data. The testing data would be similar to the training data in it's makeup and should be distributed similarly to the training data.

The goal when managing your data is that you want the data to be well represented in the data provided.

## Steps
1. Randomise the data first
2. Then split it into the data sets. 


[[Time Series Data]] does not work well for randomisation. Instead you are better off having a segment of the data split off (ie. a few months in a row)