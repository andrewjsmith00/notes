The market cap is the sum of all publicly traded stocks of a company.

To calculate the market cap weight of a stock `i`, you can use:

```python
w_mcap[i] = (m_cap[i]) / np.sum(m_cap)
```


You can use the market cap weights to assign weights to the stocks in your [[Financial Portfolio]]. When large companies are doing well, these types of portfolios tend to outperform because the largest weights are assigned to the largest companies.