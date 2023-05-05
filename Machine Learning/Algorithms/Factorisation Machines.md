Factorisation machines is a [[Supervised Learning]] algorithm for [[Binary Classification]] and [[Regression]]. This can be used with sparse datasets

> Sparse datasets means where there are gaps in the data

## Limitations
- [[SageMaker]]'s version of Factorisation Machines will only analyse relationships of two pairs of features at a time.
- CSV inputs are not supported
- Does not work for [[Multi Class Classification]]
- Needs a lot of data to make up for sparse inputs. Anywhere between 10,000 and 10,000,000
- CPUs > GPUs
- Doesn't perform well on dense data