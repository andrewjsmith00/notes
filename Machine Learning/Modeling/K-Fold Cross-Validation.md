K-Fold Cross-Validation is a method of [[Managing Training Data]] for training a model.

*K* is a constant number in this scenario. You use it to specify how many times you *fold* the data. You train the model *K* times with each time using a different segment of the dataset for training and testing. 

At the end, you compare the error rates from each round to see if the error rates are equal. Ideally each round should be approximately equal.