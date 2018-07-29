## Pandas

Pandas is a Python library created by Wes McKinney for high-performance data analysis. It's one of the most-used Python libraries for data analysis along with Matplotlib(data visualization) and Numpy. (large multi-dimensional arrays)



10 Minutes to Pandas

https://pandas.pydata.org/pandas-docs/stable/10min.html



Pandas Cheat Sheet

https://www.datacamp.com/community/blog/python-pandas-cheat-sheet



## Pandas - Data Structure

What's a data structure?

- Way of organizing data for using it efficiently
  - each data structure has advantages and disadvantages. 
  - Challenge : Either The Space (memory) or The Time
- Examples in Python : list, tuple, dict, string, set, array, Series, DataFrame
- Some of them are built-in, but others come with Python packages



Built-In Python Data Structures

- List, dict, tuple, set, string
- Mutable vs immutable



List

- Versatile, can hold items of different types. Mutable.
- Create using []



Set

- Unordered collection with **no duplicated values**. Mutable.
- Create using {}



Tuple

- Collection of values. **Immutable**
- Creat using (). Also can be empty
- Useful when storing data that does not change, when needing to optimize performance of code 



Dict

- Collection of matching keys and values
- Create using {} or dict() 



Array 

- "list of lists"
- a data structure consisting of a collection of elements (values or variables), each identified by at least one array index or key 
- The simplest form is one-dimensional array, or linear array
- Often considered as the most efficient way of storing data (You can call the list of elements with one index or key)
- NumPy is a good tool to handle array, including multi-dimentional ones



The N-dimensional array (Python Library DataStucture, like Scipy)

`ndarray` is a multidimensional container of items of the same type and size. The number of dimensions and items in an array is defined by its `shape`, which is a `tuple` of N positive integers that specify the sizes of each dimension. 

The contents of `ndarray`can be accessed and modified by indexing or slicing the array and via the methods and attributes of the `ndarray`



Pandas DataFrame

Series (1-Dimensional Data Structure)

- 1 Dimensional array that can hold any data type with, labels known as the 'index'

  ```
  s = pd.Series(data, index=index)
  ```

  * Data can be 
    * Python dictionary
    * an ndarray
    * a scalar value 
  * Index is a list of axis labels

- Series with Dict as data 

  without passing an index

  ```python
  d = {'b':1,'a':0, 'c':2}
  pd.Series(d)
  b	1
  a	0
  c	2
  ```

  passing the index (notice how the order changed and NaN is created)

  ```python
  d = {'b':1,'a':0, 'c':2}
  pd.Series(d,index=['b','c','d','a'])
  b	1.0
  c	2.0
  d	NaN
  a	0.0
  ```

- **Series with ndarray as data**

  If data is an ndarray, index must be the same length as data. If no index is passed, one will be created having values [0,...,len(data) -1]

  ```python
  s = pd.Series(np.random.randn(5), index = ['a','b','c','d','e'])
  ```

- Series with Scalar as data

  If data is a scalar value, an index must be provided. The value will be repeated to match the length of index.

  ```python
  pd.Series(5., index='a','b','c','d','e')
  a	5.0
  b	5.0
  c	5.0
  d	5.0
  e	5.0
  ```



* Indexing and Selecting Data

  [ ] indexing operator

  .attribute operator

  Primary function of indexing with [] is selecting out lower-dimensional slices. 

  Slice Series(1D Data Structure) --> Scalar

  Slice DataFrame(2D Data Structure)--> Series

  

  

DataFrame (2-Dimensional Data Structure)

- 2-dimensional labeled data structure with columns of potentially different types. 

  - (However it does not work exactly like a 2-dimensional NumPy ndarray)

  - Takes Dic of 1D ndarrays, lists, dicts, Series

  - 2-D bumpy.ndarray

  - Structured or record ndarry (don't understand...)

  - A Series

  - Another DataFrame

    

- You can optionally pass index (row labels) and colunms (column lables) arguments. If axis labels are not passed, they will be constructed from the input data based on common sense rules.

  - From dic of Series or dicts

    ```python
    d = {'one' : pd.Series([1,2,3], index=['a','b','c']),
         'two' : pd.Series([1,2,3,4],index = 'a','b','c','d')}
    df = pd.DataFrame(d)
    df2 = pd.DataFrame(d, index = ['d','b','a'])
    df3 = pd.DataFrame(d, index = ['d','b', 'a'], columns = 'two','three')
    ```



  * From arrays (Need to learn more about arrays...)

    ```python
    data = np.zeros((2,), dtype=[('A', 'i4'),('B', 'f4'),('C', 'a10')]')
    ```

* From a list of dicts

  ```python
  data= [{'a': 1, 'b': 2}, {'a': 5, 'b': 10, 'c': 20}] #list of dictionary
  pd.Series(data) # make a Series that takes data as data
  0              {'a': 1, 'b': 2}
  1    {'a': 5, 'b': 10, 'c': 20}
  
  pd.DataFrame(data) #make a DataFrame that takes data as data
     a   b     c
  0  1   2   NaN
  1  5  10  20.0
  
  pd.DataFrame(data, index = ['first', 'second'])
  
  
  pd.DataFrame(data, column = ['a','b'])
  ```

* From a dict of tuples

  ```python
  pd.DataFrame({('a','b'):{('A','B'):1, ('A', 'C'):2}, 
               ()})
  ```

  

source : http://www.grapenthin.org/teaching/geop501/lectures/lecture_06_data_structures.pdf

http://blog.benoitvallon.com/data-structures-in-javascript/data-structures-in-javascript/

https://en.wikipedia.org/wiki/Array_data_structure

https://docs.scipy.org/doc/numpy-1.13.0/reference/arrays.ndarray.html



**Series**

one-dimensional labeled array capalabe of holding any data type 

## Jupyter Notebook

* How to set start-up folder?
  * set jupyter notebook in terminal in the path you want to set 

    

## `.ipynb` versus checkpoint file

https://stackoverflow.com/questions/46421663/what-are-jupyter-notebook-checkpoint-files-for?rq=1







vector and matrix 



이해안가는것

Indexing and Slicing narray-like object

Numpy vs Pandas

list of dictionary is ndarry or ndarry like object?

list of dictionary can be taken as data both for Series and DataFrame?

```python
Creating a DataFrame by passing a dict of objects that can be converted to series-like.

In [10]: df2 = pd.DataFrame({ 'A' : 1.,
   ....:                      'B' : pd.Timestamp('20130102'),
   ....:                      'C' : pd.Series(1,index=list(range(4)),dtype='float32'),
   ....:                      'D' : np.array([3] * 4,dtype='int32'),
   ....:                      'E' : pd.Categorical(["test","train","test","train"]),
   ....:                      'F' : 'foo' })
   ....: 

In [11]: df2
Out[11]: 
     A          B    C  D      E    F
0  1.0 2013-01-02  1.0  3   test  foo
1  1.0 2013-01-02  1.0  3  train  foo
2  1.0 2013-01-02  1.0  3   test  foo
3  1.0 2013-01-02  1.0  3  train  foo

```

DataFrame의 Index가 0123이라는 것이 이해가 잘 되지 않음...

--> 참조

The resulting **index** will be the **union** of the indexes of the various Series. If there are any nested dicts, these will first be converted to Series. If no columns are passed, the **columns** will be the ordered list of **dict keys**.



Selecting via `[]`, which slices the rows.

```
In [24]: df[0:3]
Out[24]: 
                   A         B         C         D
2013-01-01  0.469112 -0.282863 -1.509059 -1.135632
2013-01-02  1.212112 -0.173215  0.119209 -1.044236
2013-01-03 -0.861849 -2.104569 -0.494929  1.071804

In [25]: df['20130102':'20130104']
Out[25]: 
                   A         B         C         D
2013-01-02  1.212112 -0.173215  0.119209 -1.044236
2013-01-03 -0.861849 -2.104569 -0.494929  1.071804
2013-01-04  0.721555 -0.706771 -1.039575  0.271860
```

how do you slice columns?

df['A'] - how do you tell if it's index or column?



**Viewing Data of DataFrame**

View index, columns, and the underlying data (value)

```python
df.index
df.columns
df.values
df.sort_index(axis = 1, ascending=False)
df.sort_values(by='b')
```



**Selecting Data Using Labels(Column Heading)** - Python way

Either using square brackets `[]` or .

```python
df['one']
df.one
```

**Grabbing data that meets a certain condition**

```python
df[df.A > 0] #grab values under indexA that is bigger than 0
```



**Add a new column at the end of dataframe**

```python
df['E']=['one','one','two'...]
```



**Column Selection, Addtion, Deletion**

You can treat a DataFrame semantically like a dict of like-indexed Series objects. Getting, setting, and deleting columns works with the same syntax as the analogous dict operations.

```python 
df['one'] # prints Series with values under column 'one' passing index from DataFrame
```



Columns can be deleted or popped like with dict:

```python
del df['two']
three = df.pop('three')
```



When inserting a scalar value, it will natrually be propapgated to fill the column:

```python
df['foo'] = 'bar'
```

When inserting a Series that does not have the same index as the DataFrame, it will be conformed to the DataFrame's index

By default, columns get inserted at the end. The insert function is available to insert at a paricular location in the columns



**Selecting Data Using Labels(Column Heading)** - using Pandas attributes

Pandas provides a suite of methods in order to hvae purely label based indexinb. Every label asked for must be in the index, or a KeyError will be raised. When slicing, both the start bound and the stop bound are included. Integers are valid labels, but they refer to the label and not the position. 

1. Selecting data by row numbers (.iloc)

   integer-location based indexing/selection by position

   ```python
   data.iloc[0] # first row of dataframe
   data.iloc[-1] # last row of dataframe
   data.iloc[:,0] # first column of dataframe
   data.iloc[:,-1] # last column of dataframe
   
   data.iloc[0:5] # first five rows
   data.iloc[:, 0:2] # first two columns with all rows
   ## but if I only want to select the columns, what do I do?
   ```

   iloc returns a Pandas Series when one row is selected, and a Pandas DataFrame when multiple rows are selected of if any column in full is selected. To counter this, pass a **single-valued list** if you require DataFrame output.

   ```python
   data.iloc[100] Series - one row selected
   data.iloc[[100]] DataFrame - list selection does the trick
   data.iloc[2:10]  #huh?
   data.iloc[1:2,3] #Series because only one column selected
   ```

    

2. Selecting data by label or by a conditional statement (.loc)

   ```python
   data.loc[data['id']>2000, "first_name"] @change the first name of all rows with an ID greater than 2000 to 'john'
   ```

   ```python
   df.loc[dates[0]] # returns Series of first index
   df.loc[:,['A','B']] # returns DataFrame of all the index and A,B columns
   ```

   ```python
   df.loc['20130102':'20130104', ['A','B']] # returns DataFrame with index from 20130102 to 2013014 and columns A and B
   ```

   ```python
   df.loc[dates[0],'A'] # returns a scalar value 
   df.at[dates[0], 'A'] # also same
   ```

   **When selecting by label, Python's 0-based indexing does not work!

   When selecting by position, it follows Python's 0-based indexing**

   

3. Boolean Indexing

   Using a single column's values to select data

   ```python
   df[df.A >0 ] # returns values of column A, bigger than 0
   ```

   ```python 
   df[df > 0] # returns values bigger than 0 (if not, returns NaN)
   ```

   `isin()` : filter

   

**Slicing**

By using square brackets `[]`

`data[start:stop`



**Reindexing**

change/add/delete the index on a specificed axis 

```python 
df1 = df.reindex(index=dates[0:4], columns=list(df.columns)+ ['E'])
df1.loc[dates[0]:dates[1], 'E'] = 1
```

to drop any rows that have missing data

```python
df1.dropna(how='any')
```

filling missing data

```python
df1.fillna(value=5)
```

to get the boolean mask where values are nan

```python
pd.isna(df1)
```

**Apply**

apply functions to the data

```python
df.apply(np.cumsum)
```

**Append**

append rows to a dataframe

```python
df= pd.DataFrame(np.random.randn(8,4), columns = 'A','B','C','D')
s = df.iloc[3] 
df.append(s, ignore_index=True)
```



https://www.shanelynn.ie/select-pandas-dataframe-rows-and-columns-using-iloc-loc-and-ix/