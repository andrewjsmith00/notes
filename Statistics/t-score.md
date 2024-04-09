The t-score is calculated when comparing two different populations (ie. do people who started programming as a child earn more than those who started as adults). This replaces [[z-score]]s in these tests.

The t-score is calculated as:
$$
\frac{(\bar{x}_{child} - \bar{x}_{adult})}{\sqrt{\frac{s^2_{child}}{n_{child}}+\frac{s^2_{adult}}{n_{adult}}}}
$$


Once it is calculated, we can retrieve the [[p-value]] by using:
```python
from scipy.stats import t

1-t.cdf(t_score, degrees_of_freedom)
```

Where `degrees_of_freedom` is the number of independent samples in our dataset