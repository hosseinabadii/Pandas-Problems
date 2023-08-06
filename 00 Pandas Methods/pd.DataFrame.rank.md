# `pandas.DataFrame.rank`

The `pandas.DataFrame.rank` method in pandas is used to compute the ranks of elements in a DataFrame. It assigns a rank to each element in the DataFrame based on the specified method. The resulting rank is an integer value that represents the position of the element in its ordered series.

Here's the general syntax of the rank method:

```python
DataFrame.rank(
    axis=0,
    method='average',
    numeric_only=None,
    na_option='keep',
    ascending=True,
    pct=False,
)
```
## Parameters:

`axis:` Determines whether to calculate ranks along the rows (0 or 'index') or columns (1 or 'columns').

`method:` Specifies the method used to assign ranks to tied values. It can take the following values:
- `'average' (default):` average rank of the group
- `'min':` lowest rank in the group
- `'max':` highest rank in the group
- `'first':` ranks assigned in order they appear in the array
- `'dense':` like ‘min’, but rank always increases by 1 between groups.

`numeric_only:` If set to False (default), all columns will be ranked. If set to True, only numeric columns will be ranked.

`na_option:` Determines how NaN values are treated. It can take the following values:
- `'keep' (default):` Leaves NaN values as is and does not assign a rank to them.
- `'top':` Assigns the lowest rank to NaN values.
- `'bottom':` Assigns the highest rank to NaN values.

`ascending:` Determines whether the ranks should be in ascending order (True) or descending order (False).

`pct:` If True, the returned rank values will be the percentage ranks from 0 to 100.

## Return value:
The method returns a new DataFrame with the same shape as the original DataFrame, but with the elements replaced by their respective ranks.
