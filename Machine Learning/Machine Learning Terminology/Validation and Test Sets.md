In [[Machine Learning]], if a model is trained with all the data and then evaluated using the same data, we would not be able to tell how well the model performs on data it has not seen. It is very important to understand this when training a model.

To avoid this, you can split the dataset into two parts, the training set and the validation set. This allows for the model to be validated on the validation set to ensure it is generalised.

The situation of splitting the dataset so the model does not see it while training is more subtle than just splitting the data. Realistically there are many versions of a model built through various modeling choices for architecture, learning rates, etc. Many of these choices are referred to as *hyperparameters*. This means that they are parameters of parameters.

A problem arises that even though the training process is looking at predictions on the training data, the same is not true for us. We are looking at predictions on the validation data when exploring hyperparameters. This means that versions of the model are shaped by us having seen the validation data. Just as the training process is in danger of [[overfitting]] for the training data, we are in danger of [[overfitting]] the validation data through trial and error and exploration.
Essentially, since we use the validation data as the measure of success, if we tune to that data then we are repeating the same issue.

The solution to this is to introduce a test set. Just as we hold validation data from the training process, the test set must be held from us. It cannot be used to improve the model but only to evaluate the model at the end of the efforts.

The test data is for the end. You use it to verify the results at the very end to decide if the overall performance is adequate. In tuning parameters, you don't use the test set.