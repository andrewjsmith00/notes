These are not normally distributed and can have high [[Kurtosis]].

You can use the average daily returns to calculate the average yearly return by using the following formula:
```python
mean_return_annualised = ((1 + mean_return_daily) ** 252) -1
```

252 is the average number of trading days in a year