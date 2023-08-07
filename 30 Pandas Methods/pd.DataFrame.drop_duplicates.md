# `pandas.DataFrame.drop_duplicates`

The `pandas.DataFrame.drop_duplicates` method is used to remove duplicate rows from a DataFrame based on specified columns. It helps in cleaning and preprocessing data by eliminating redundant entries.

Here's the general syntax of the drop_duplicates method:

```python
DataFrame.drop_duplicates(
    subset=None,
    keep='first',
    inplace=False,
    ignore_index=False
)
```
## Parameters:

`subset:` A list or array of column names indicating the subset of columns to consider when identifying duplicates. By default, it is set to None, which means all columns are used to identify duplicates.

`keep:` Specifies which occurrence of the duplicated rows to keep. It can take the following values:
- `'first' (default):` Keep the first occurrence and drop the rest.
- `'last':` Keep the last occurrence and drop the rest.
- `False:` Drop all occurrences of duplicates.

`inplace:` If True, the DataFrame will be modified in place, and None will be returned. If False (default), a new DataFrame with duplicates removed will be returned.

`ignore_index:` If True, the resulting DataFrame will have a new index assigned in ascending order after dropping duplicates. If False (default), the index of the original DataFrame will be preserved.

## Return value:
The method returns a DataFrame with duplicates removed. If inplace=True, it returns None, and the DataFrame is modified in place.

## Example:

```python
# Create a DataFrame with duplicate rows
data = {
    'Name': ['John', 'Alice', 'John', 'Bob', 'Alice'],
    'Age': [25, 30, 25, 28, 30],
    'City': ['New York', 'Los Angeles', 'New York', 'Chicago', 'Los Angeles']
}

df = pd.DataFrame(data)

# Drop duplicates based on all columns
df_unique = df.drop_duplicates()

print(df_unique)
```
Output:
```
    Name  Age         City
0   John   25     New York
1  Alice   30  Los Angeles
3    Bob   28      Chicago
```
In the above example, the drop_duplicates method is called without specifying the subset parameter, so it considers all columns. It keeps the first occurrence of each duplicate row and drops the subsequent ones, resulting in a DataFrame with duplicates removed.