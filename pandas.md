# Data Science Learning Repository(Pandas)

**Table of Contents**
- [BASICS OF PANDAS](#basics-of-pandas)
 - [What is Pandas?](#what-is-pandas)
 - [Package Installation](#package-installation)
 - [Import numpy package](#import-numpy-package)
 - [Creating a series from array](#creating-a-series-from-array)
 - [Creating a series from list](#creating-a-series-from-list)
 - [Creating a series from dictionary](#creating-a-series-from-dictionary)
 - [Accessing elements from series with position](#accessing-elements-from-series-with-position)
 - [Accessing Element Using Label (index)](#accessing-element-using-label-index)
 - [To find the maximum value](#to-find-maximum-value)
 - [Pandas DataFrame](#pandas-dataframe)
 - [Creating a data frame using List](#creating-a-data-frame-using-list)
 - [Creating a dataframe from dictionary](#creating-a-dataframe-from-dictionary)
 - [DataFrames - Adding and Deleting Columns](#dataframes-adding-and-deleting-columns)
 - [DataFrames - Filtering and Querying](#dataframes-filtering-and-querying)
 - [DataFrames - Grouping and Aggregating](#dataframes-grouping-and-aggregating)
 - [DataFrames - Merging and Joining](#dataframes-merging-and-joining)
 - [DataFrames - Reading and Writing Data](#dataframes-reading-and-writing-data)


## BASICS OF PANDAS <a name="basics-of-pandas"></a>

### What is Pandas? <a name="what-is-pandas"></a>

- Pandas is an open source python library providing high performance data manipulation and analysis tool using its powerful data structure. Pandas is the backbone for most of the data projects.

- Through pandas , you get acquainted with your data by cleaning,transforming and analyzing it. 
- Python with pandas is used in a wide range of fields including academic and commercial domains including finance,economics,Statistics,analytics,etc.

- Pandas generally provide two data structure for manipulating data, They are:

        Series
        DataFrame

### Package Installation <a name="package-installation"></a>
```pip install pandas```

### Importing numpy package <a name="import-numpy-package"></a>
```python
import pandas as pd
```
 > With the above import statement, you can access pandas functions using the pd.

**Creating a series from array**<a name="creating-a-series-from-array"></a>
```python
import pandas as pd
import numpy as np
data = np.array(['p','y','t','h','o','n'])
ser = pd.Series(data)
print(ser)
```

**Creating a series from list** <a name="creating-a-series-from-list"></a>

```python
import pandas as pd
list = ['p', 'y', 't', 'h', ‘o', 'n']
ser = pd.Series(list)
print(ser)
```

**Creating a series from dictionary**<a name="creating-a-series-from-dictionary"></a>
```python
import pandas as pd
dictionary = {'A' : 10, 'B' : 20, 'C' : 30}
series = pd.Series(dictionary)
print(series)
```

**Accessing elements from series with position**<a name="accessing-elements-from-series-with-position"></a>
```python
import pandas as pd
import numpy as np
data = np.array(['p','y','t','h','o','n', 'p','r','o','g','r','a','m'])
ser = pd.Series(data)
print(ser[:5])
```

**Accessing Element Using Label (index)** <a name="accessing-element-using-label-index"></a>
```python
import pandas as pd
import numpy as np
data = np.array(['p','y','t','h','o','n'])
ser = pd.Series( data, index=[10,11,12,13,14,15])
print(ser)
print(ser[12])
```

**To find maximum value**<a name="to-find-maximum-value"></a>
```python
import pandas as pd
sr = pd.Series([10, 25, 3, 25, 24, 6],index=['Coca Cola', 'Sprite', 'Coke', 'Fanta','Dew', ‘ThumbsUp‘])
print(sr)
result=max(sr)
print(result)
```


## Pandas data frame
**What is DataFrame?** <a name="pandas-dataframe"></a>

- Pandas DataFrame is two-dimensional size-mutable, potentially heterogeneous tabular data structure with labeled axes (rows and columns).
-  A Data frame is a two-dimensional data structure, i.e., data is aligned in a tabular fashion in rows and columns.

**Creating a data frame using List**<a name="creating-a-data-frame-using-list"></a>
```python
import pandas as pd
lst = ['data', 'visualization', 'using', 'python', 'and', 'r', 'programming']

# converting list into data frame
df = pd.DataFrame(lst)
print(df)
```

**Creating a dataframe from dictionary**<a name="creating-a-dataframe-from-dictionary"></a>
```python
import pandas as pd

# Create DataFrame

data = {
    'Name':['Tom', 'nick', ‘krish', 'jack'],
    'Age':[20, 21, 19, 18]
    }

df = pd.DataFrame(data)
print(df)
```
**DataFrames - Adding and Deleting Columns**<a name="dataframes-adding-and-deleting-columns"></a>
```python
import pandas as pd
#Create DataFrame
data = {
    'Name': ['Tom', 'Nick', 'Krish', 'Jack'],
    'Age': [20, 21, 19, 18]
}

df = pd.DataFrame(data)
print("Original DataFrame:")
print(df)

# Adding a new column
df['Gender'] = ['M', 'M', 'M', 'M']
print("\nDataFrame after adding 'Gender' column:")
print(df)

# Deleting a column
df.drop('Age', axis=1, inplace=True)
print("\nDataFrame after deleting 'Age' column:")
print(df)
```

**DataFrames - Filtering and Querying**<a name="dataframes-filtering-and-querying"></a>
```python
import pandas as pd

# Create DataFrame
data = {
    'Name': ['Tom', 'Nick', 'Krish', 'Jack'],
    'Age': [20, 21, 19, 18]
}

df = pd.DataFrame(data)

# Filtering rows based on a condition
filtered_df = df[df['Age'] >= 20]
print("\nFiltered DataFrame:")
print(filtered_df)

# Querying the DataFrame using the query() method
query_result = df.query('Age >= 20')
print("\nQuery Result:")
print(query_result)
```

**DataFrames - Grouping and Aggregating**<a name="dataframes-grouping-and-aggregating"></a>
```python
import pandas as pd

# Create DataFrame
data = {
    'Name': ['Tom', 'Nick', 'Krish', 'Jack', 'Tom', 'Nick'],
    'Age': [20, 21, 19, 18, 20, 21],
    'Score': [85, 90, 78, 82, 88, 92]
}

df = pd.DataFrame(data)

# Grouping by 'Name' and calculating mean of 'Score'
grouped_df = df.groupby('Name')['Score'].mean()
print("\nGrouped DataFrame:")
print(grouped_df)

# Grouping by multiple columns and calculating multiple aggregations
grouped_df_multiple = df.groupby(['Name', 'Age']).agg({'Score': ['mean', 'min', 'max']})
print("\nGrouped DataFrame with multiple aggregations:")
print(grouped_df_multiple)
```

**DataFrames - Merging and Joining** <a name="dataframes-merging-and-joining"></a>
```python
import pandas as pd
# Create DataFrame 1
data1 = {
    'ID': [1, 2, 3, 4],
    'Name': ['Tom', 'Nick', 'Krish', 'Jack']
}

df1 = pd.DataFrame(data1)

# Create DataFrame 2
data2 = {
    'ID': [3, 4, 5, 6],
    'Age': [20, 21, 19, 18]
}

df2 = pd.DataFrame(data2)

# Merging DataFrames on 'ID'
merged_df = pd.merge(df1, df2, on='ID', how='inner')
print("\nMerged DataFrame:")
print(merged_df)

# Joining DataFrames on 'ID'
joined_df = df1.set_index('ID').join(df2.set_index('ID'), how='inner')
print("\nJoined DataFrame:")
print(joined_df)
```

**DataFrames - Reading and Writing Data**<a name="dataframes-reading-and-writing-data"></a>
```python
import pandas as pd
# Reading data from a CSV file
csv_file = "data.csv"
df = pd.read_csv(csv_file)

# Display the first few rows of the DataFrame
print("\nData from CSV:")
print(df.head())

# Writing data to a CSV file
df.to_csv("output.csv", index=False)

# Reading data from an Excel file
excel_file = "data.xlsx"
df_excel = pd.read_excel(excel_file)

# Display the first few rows of the DataFrame
print("\nData from Excel:")
print(df_excel.head())

# Writing data to an Excel file
df_excel.to_excel("output.xlsx", index=False)
```
