A fundamental building block for many [[Asset Pricing Model]]s and [[Factor Model]]s in finance.


It can be calculated as:
```python
expected_return_p - risk_free_rate
```
Where p is the expected return of a [[Financial Portfolio]] or stock


or

```python
beta_p * (expected_return_m - risk_free_Rate)
```

Where `beta_p` is the [[Portfolio Exposure]] to a broad market portfolio and `expected_return_m` is the expected return of a broad market portfolio.


You can calculate beta with:
$$
\beta_P = \frac{Cov(R_P,R_B)}{Var(R_B)}
$$

where:
$Cov(R_P,R_B)$ is the [[Correlation and Co-Variance]] of the portfolio P and benchmark B
$Var(R_B)$ is the variance of the benchmark.


You can use beta as a variable in linear regression where you compare the portfolio returns against the market returns.


Beta is essentially a measure of performance against the market. For example, with a beta of 0.97, for every 1% gain, the portfolio is expected to rise 0.97%.

When 