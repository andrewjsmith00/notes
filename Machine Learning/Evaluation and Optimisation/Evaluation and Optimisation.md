This step comes after [[Model Training]] in the [[Machine Learning]] lifecycle.

## Concepts
We want generalisation, not memorisation so we need to know when we are [[Overfitting]]. 

## Steps
There are 3 steps:
1. What metric are we looking at?
2. Review the metrics during or after
3. Tune the hyperparameters, data, evaluation strategy or algorithm to improve results


## Validation
### Offline
Validation done using test sets of data. Can do this via [[Validation and Test Sets]] or [[K-Fold Cross-Validation]]

### Online validation
Validating with real-world conditions. Ie. [[Canary Deployments]] or [[A/B Testing]]