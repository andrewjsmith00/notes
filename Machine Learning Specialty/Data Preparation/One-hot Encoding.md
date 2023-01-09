Where you transform nominal categorical features and create new binary columns for each observation.

For example, in a column where there are three categories, you create a column with 1 if it is that category and 0 for the categories it is not. 

This can exponentially increase your dataset size depending on the number of categories. Alternatively you can use grouping by similarity to create fewer overall categories or you can map rare values to 'other'