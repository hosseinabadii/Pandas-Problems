# `pandas.DataFrame.groupby()`

The `pandas.DataFrame.groupby()` method is used to group data in a DataFrame based on **one or more columns**. It allows you to split the data into groups based on the unique values in the specified columns and perform aggregation or transformation on each group.

The general syntax of groupby() is as follows:

```python
DataFrame.groupby(
    by=None,
    axis=0,
    level=None,
    as_index=True,
    sort=True,
    group_keys=True,
    squeeze=False,
    observed=False,
    dropna=True
)
```
Let's discuss each of the important arguments:

`by:` The column(s) or key(s) to use for grouping. It can be a single column name, a list of column names, or a callable function to extract group keys from the DataFrame.

`axis:` The axis along which the grouping should be performed. It can take the following values:

- `0 or 'index' (default):` Group by rows.
- `1 or 'columns':` Group by columns.

`level:` If the axis is a MultiIndex (hierarchical index), use the level(s) to perform grouping.

`as_index:` If True (default), the grouped column(s) will become the index of the resulting DataFrame. If False, the grouping columns will be kept as regular columns.

`sort:` If True (default), sort the groups by the group keys.

`group_keys:` If True (default), include the group keys in the result as index levels.

`squeeze:` If True, return a Series when there is a single group. If False (default), always return a DataFrame.

`observed:` If True (default is False), treat a Categorical dtype as observed during the grouping process, even if it has missing categories.

`dropna:` If True (default), exclude NA/null values from the group keys. If False, keep NA/null values as a group.

The groupby() method returns a `DataFrameGroupBy` or `SeriesGroupBy` object, depending on the axis and squeeze arguments. These objects represent the grouped data and allow you to perform various aggregate and transformation operations.

## Here are some examples of how to use the groupby() method:

### #1: Grouping and Aggregating Data:

```python
# Sample DataFrame
data = {'Department': ['IT', 'IT', 'Sales', 'Sales', 'IT'],
        'Employee': ['Joe', 'Jim', 'Henry', 'Sam', 'Max'],
        'Salary': [70000, 90000, 80000, 60000, 90000]}

df = pd.DataFrame(data)

# Group by 'Department' and calculate the mean salary for each group
grouped = df.groupby('Department')['Salary'].mean()

print(grouped)
```
Output:
```
Department
IT       83333.333333
Sales    70000.000000
Name: Salary, dtype: float64
```

### #2: Grouping and Applying Custom Function:

```python
# Sample DataFrame
data = {'Department': ['IT', 'IT', 'Sales', 'Sales', 'IT'],
        'Employee': ['Joe', 'Jim', 'Henry', 'Sam', 'Max'],
        'Salary': [70000, 90000, 80000, 60000, 90000]}

df = pd.DataFrame(data)

# Define a custom function to get the highest salary employee in each department
def get_highest_salary_employee(group):
    return group[group['Salary'] == group['Salary'].max()]

# Group by 'Department' and apply the custom function
result = df.groupby('Department').apply(get_highest_salary_employee)

print(result)
```
Output:
```
  Department Employee  Salary
0         IT      Joe   70000
1         IT      Jim   90000
2      Sales    Henry   80000
```
