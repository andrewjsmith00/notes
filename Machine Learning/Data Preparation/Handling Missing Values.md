Removing incomplete, incorrectly formatted, irrelevant or duplicate data. 

Missing data can be represented in many ways (null, NaN, etc.)

There are a few ways to handle missing data. However first the question of why it is missed should be asked. Some relationships for why this is occurring is possible.

There are a few definitions for why data may be missing:

## Missing at Random (MAR)
This means that the reason for a value to be missing is not related to the missing value but is related to some other data

## Missing Completely at Random (MCAR)
The reason that a value is missing has nothing to do with the value itself or the value of anything else.

## Missing not at Random (MNAR)
Two reasons that the value is missing are:
- What the value is meant to be
- Dependent on some other value


If you can define why data is missing, you can use specific techniques to fill in the gap. In filling missing values, you want to create the least amount of impact or bias in your data in doing so. Replacing data is called imputation.


## Handling Missing Values

### [[Supervised learning]]
Looks at other values in features and predicts the missing values. It is the most difficult but can have the best results.

### Mean
Get the average. Quick but can be dodgy

### Median
Gets the middle value

### Mode
Gets the most common value

### Dropping rows
Get rid of rows with missing values. This is the easiest but can dramatically change the dataset.