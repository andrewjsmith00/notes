The p-value is the probability of the hypothesis used to determine whether to accept or reject the null hypothesis in [[Hypothesis Testing]]. 

We can calculate the p-value using the [[z-score]] via:
```python
from scipy.stats import norm

# right tail test. remove the 1- to use left tail
1 - norm.cdf(zscore, loc=0, scale=1)
```
