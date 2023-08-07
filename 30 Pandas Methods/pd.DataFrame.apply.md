# `pandas.DataFrame.apply()`

The `pandas.DataFrame.apply()` method is used to apply a function along the axis of a DataFrame. It allows you to perform custom operations on the **elements**, **rows**, or **columns** of a DataFrame. The general syntax of `apply()` is as follows:

```python
DataFrame.apply(
    func,
    axis=0,
    raw=False,
    result_type=None,
    args=(),
    **kwds
)
```
Let's discuss each of the important arguments:

`func:` The function to be applied. It can be a built-in Python function, a lambda function, or any user-defined function.

`axis:` The axis along which the function should be applied. It can take the following values:

- `0 or 'index' (default):` Apply the function to each column (i.e., along the rows).
- `1 or 'columns':` Apply the function to each row (i.e., along the columns).

`raw:` If True, the function will receive the raw NumPy array instead of a Series. Default is False.

`result_type:` Specifies the type of the result. It can take the following values:

- `None (default):` The result will be a Series if the function returns a scalar or a DataFrame if the function returns a Series.
- `'reduce':` Results will be reduced to a Series when possible.

`args:` A tuple of extra arguments to be passed to the function.

`**kwds:` Additional keyword arguments to be passed to the function.

The apply() method returns the result of applying the function to the DataFrame along the specified axis.

## Here are some examples of how to use the apply() method:

### #1: Applying a Function to Each Column (along the rows):
```python
# Sample DataFrame
data = {'A': [1, 2, 3], 'B': [4, 5, 6], 'C': [7, 8, 9]}
df = pd.DataFrame(data)

# Define a function to add 10 to each element
def add_10(x):
    return x + 10

# Apply the function to each column
result = df.apply(add_10)

print(result)
```
Output:
```
    A   B   C
0  11  14  17
1  12  15  18
2  13  16  19
```
### #2: Applying a Function to Each Row (along the columns):

```python
# Sample DataFrame
data = {'A': [1, 2, 3], 'B': [4, 5, 6], 'C': [7, 8, 9]}
df = pd.DataFrame(data)

# Define a function to sum the elements in each row
def row_sum(row):
    return row.sum()

# Apply the function to each row
result = df.apply(row_sum, axis=1)

print(result)
```
Output:
```
0    12
1    15
2    18
dtype: int64
```
