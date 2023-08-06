# `pandas.DataFrame.merge()`

The `pandas.DataFrame.merge()` method is used to merge two DataFrames based on **common columns**. It allows you to combine data from different DataFrames into a single DataFrame based on the specified merge criteria. The general syntax of `merge()` is as follows:

```python
DataFrame.merge(
    right,
    how='inner',
    on=None,
    left_on=None,
    right_on=None,
    left_index=False,
    right_index=False,
    sort=False,
    suffixes=('_x', '_y'),
    copy=True,
    validate=None,
)
```
Let's discuss each of the important arguments:

`right:` The DataFrame or Series to merge with the current DataFrame. It is the second DataFrame involved in the merge operation.

`how:` The type of merge to be performed. It can take the following values:

- `'inner':` Performs an inner join. It keeps only the rows that have matching keys in both DataFrames.
- `'outer':` Performs an outer join. It keeps all the rows from both DataFrames and fills in missing values with **NaN** where there is no match.
- `'left':` Performs a left join. It keeps all the rows from the left DataFrame and fills in missing values with **NaN** where there is no match in the right DataFrame.
- `'right':` Performs a right join. It keeps all the rows from the right DataFrame and fills in missing values with **NaN** where there is no match in the left DataFrame.

`on:` The column or list of columns to use as the merge key. This is used when both DataFrames have the same column name for merging.

`left_on, right_on:` The column or list of columns to use as the merge key from the left and right DataFrames, respectively. This is used when the column names are different in both DataFrames.

`left_index, right_index:` If True, use the index of the DataFrames as the merge key instead of columns. Default is False.

`sort:` If True, sort the result DataFrame by the columns used for merging. Default is False.

`suffixes:` A tuple of strings to append to the overlapping column names in case of name conflicts. The default values are ('_x', '_y').

`copy:` If True, always copy data from the source DataFrame, regardless of whether it is necessary. Default is True.
