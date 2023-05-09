A [[Supervised Learning]] algorithm that looks for the closest sample point to the data and returns the most frequent label as the predicted label

For [[Regression]], the $k$ closest points are sampled and then the average value of them all is returned.

It is considered a lazy algorithm as it does not generalise the data. This data is kept in memory.