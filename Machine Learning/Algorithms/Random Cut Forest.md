This is an [[Anomaly Detection]] algorithm which detects anomalous data points in a set. This can help identify data points that are beyond normal (more than 3 [[Standard Deviation]]s) that could mess up training.

This works with n-dimensional inputs.

RCF will give an anomaly score to data points. Higher scores are indication of anomalies. It scales will with number of features, dataset size and such.