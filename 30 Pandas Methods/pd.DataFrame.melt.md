# `pandas.DataFrame.melt`

The `pandas.DataFrame.melt` method is used to transform a DataFrame from wide format to long format, also known as "unpivoting" or "melting" the DataFrame. It is particularly useful when you want to reorganize your data by converting column headers into rows. This function is commonly used during data preprocessing or when you need to reshape your data for analysis or visualization purposes.

Here's the general syntax of the melt method:

```python
DataFrame.melt(
    id_vars=None,
    value_vars=None,
    var_name=None,
    value_name='value',
    col_level=None
)
```
## Parameters:

`id_vars:` A list or array of column names that you want to retain as identifier variables. These columns will not be melted and will be used as identifiers to uniquely identify each row in the output DataFrame.

`value_vars:` A list or array of column names that you want to melt into rows. If set to None, all columns not in id_vars will be melted.

`var_name:` The name of the variable column that will store the column names of the original DataFrame. By default, it is set to None, and the resulting column will be named "variable".

`value_name:` The name of the variable column that will store the values of the original DataFrame. By default, it is set to "value".

`col_level:` If the DataFrame has columns with MultiIndex (hierarchical columns), this parameter specifies the level(s) to melt. It can be an integer or a list of integers representing the levels.

## Return value:
The method returns a new DataFrame with the melted data.

## Example:

```python
# Create a DataFrame in wide format
data = {
    'ID': [1, 2, 3],
    'A': [10, 20, 30],
    'B': [40, 50, 60],
    'C': [70, 80, 90]
}

df = pd.DataFrame(data)

# Melt the DataFrame to long format
df_melted = df.melt(id_vars=['ID'], var_name='Category', value_name='Value')

print(df_melted)
```
Output:
```
   ID Category  Value
0   1        A     10
1   2        A     20
2   3        A     30
3   1        B     40
4   2        B     50
5   3        B     60
6   1        C     70
7   2        C     80
8   3        C     90
```
