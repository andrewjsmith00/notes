A method of [[Feature Engineering]] to transform numbers so [[Machine Learning Algorithms]] can understand them better.

Commonly done with:

## Feature Scaling
Change all values so they are on the same scale:
### Normalisation
Method of feature scaling where you set the smallest value to 0, largest to 1 and then you scale all other values along this.

This is done with the formula:
$$
x' = \frac{x - min(x)}{max(x)-min(x)}
$$
Most common and easiest technique to scale values. Outliers can cause problems though.


### Standardisation
Standardisation puts the average on 0 and uses the $z$-score to scale the values. This is done via the following
$$
z = \frac{x-\bar{x}}{\sigma}
$$
This will smooth out values and resolve issues with outliers.

## Binning
Changes numeric values into groups or bins of similar values.

We can use binning when we know a value does not have a linear role in the output of the prediction. An example of a feature that is good is a person's age. Since 50 & 51 may not present much of a difference, we can apply binning to scale the features.

Binning can cause irregular bins (non-uniform)

### Quantile binning
Quantile binning aims to assign the same number of features into each bin. This is done by changing the bin ranges to cause for equal number of objects per bin.