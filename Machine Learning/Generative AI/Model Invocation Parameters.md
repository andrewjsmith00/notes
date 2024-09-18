There are a number of parameters included in invoking [[Foundation Model]] with [[Bedrock]]. These are:

## Temperature
Adjusting the temperature will affect the shape of the probability distribution for the predicted output. This can influence a model to create more random responses.
- Lower value = higher probability choices. More deterministic
- Higher value = lower probability choices. More random


## Top K
The number of most-likely token candidates that the model produces when selecting tokens. Lower value means less options (more likely outputs), higher value means more options (less likely outputs). 

## Top P
The percentage of most-likely candidates that the model considers for the next token. Top P influences the sum of probabilities that is allowed. ie. Top P of 0.9 means that the sum of probabilities of all choices is 0.9
Lower value decreases the size of pool, higher value is larger pool with less likely outputs included.