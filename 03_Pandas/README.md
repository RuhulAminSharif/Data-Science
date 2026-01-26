## Pandas

Pandas is a fast, powerful, flexible and easy to use open source data analysis and manipulation tool,
built on top of the Python programming language.

### Pandas Series

> - Creation of Series
>   > - Series from List
>   > - Series from Dictionary
>   > - Series from CSV
> - Series Attributes
>   > - size
>   > - dtype
>   > - name
>   > - is_unique
>   > - index
>   > - values
> - Series Operations
>   > - Addition
>   > - Subtraction
>   > - Multiplication
>   > - Division
> - Series Methods
>   > - head()
>   > - tail()
>   > - sample()
>   > - value_counts()
>   > - sort_values()
>   > - sort_index()
> - Seris Math Functions
>   > - count()
>   > - sum(), product()
>   > - mean(), median(), mode()
>   > - std(), var()
>   > - min(), max()
>   > - describe()
> - Series Indexing and Slicing
>   > - Indexing using labels
>   > - Indexing using positions
>   > - Fancy Indexing
>   > - Slicing using labels
>   > - Slicing using positions
> - Editing Series
>   > - Adding elements
>   > - Modifying elements
>   > - Deleting elements
> - Series with Python Functionalities
>   > - len(), type(), dir(), sorted(), max(), min()
>   > - type conversion using list(), dict()
>   > - membership operators: in, not in
>   > - iteration using for loop
>   >   Arithmetic operations with scalar values
>   > - Relational operations with scalar values
> - Boolean Indexing
> - Plotting Series
> - More Methods on Series
>   > - astype()
>   > - between()
>   > - clip()
>   > - drop_duplicates()
>   > - isnull()
>   > - dropna()
>   > - fillna()
>   > - isin()
>   > - apply()
> - Copy and View of Series

### Pandas DataFrame

> - Creation of DataFrame
>   > - DataFrame from List of Lists
>   > - DataFrame from Dictionary
>   > - DataFrame from CSV
> - DataFrame Attributes
>   > - shape
>   > - dtypes
>   > - index
>   > - columns
>   > - values
> - DataFrame Methods
>   > - head()
>   > - tail()
>   > - sample()
>   > - info()
>   > - describe()
>   > - isnull()
>   > - duplicated()
>   > - rename()
>   > - sum(), mean(), median(), std(), var()
>   > - min(), max()
> - Selecting Columns from DataFrame
>   > - Selecting single column
>   > - Selecting multiple columns
> - Selecting Rows from DataFrame
>   > - Selecting by position using iloc[]
>   > - Selecting by label using loc[]
> - Selecting both Rows and Columns
>   > - Using iloc[]
>   > - Using loc[]
> - Filtering DataFrame
> - Adding new Columns
> - Important DataFrame Methods
>   > - info()
>   >   -astype()
>   >   -value_counts()
>   > - sort_values()
>   > - sort_index()
>   > - rank()
>   > - set_index()
>   > - reset_index()
>   > - rename()
>   > - unique() and nunique()
>   > - isnull(), notnull(), and hasnans()
>   > - dropna()
>   > - fillna()
>   > - drop_duplicates()
>   > - drop()
>   > - apply()

### Groupby Objects

> - Grouping DataFrame
> - Aggregation Functions
>   > - sum()
>   > - mean()
>   > - median()
>   > - std(), var()
>   > - min(), max()
>   > - count()
> - Groupby Attributes and Methods
>   > - len()
>   > - size()
>   > - first(), last(), nth()
>   > - get_group() vs filtering
>   > - groups
>   > - describe()
>   > - sample()
>   > - nunique()
> - agg() Method
>   > - passing dictionary to agg()
>   > - passing list to agg()
>   > - passing both list and dictionary to agg()
> - Iterating through Groupby objects
> - Split-Apply-Combine Paradigm
> - Groupby with Multiple Columns
> - Groupby with Different Aggregation for Different Columns

### Pandas Merging, Joining, and Concatenating

> - Concatenating DataFrames
>   > - Concatenating along rows
>   > - Concatenating along columns
>   > - Handling Indexes while Concatenating
> - Merging DataFrames
>   > - Inner Join
>   > - Left Join
>   > - Right Join
>   > - Outer Join
>   > - Self Join
>   > - Merging on Multiple Columns
