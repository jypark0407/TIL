```
SettingWithCopyWarning: 
A value is trying to be set on a copy of a slice from a DataFrame.
Try using .loc[row_indexer,col_indexer] = value instead

See the caveats in the documentation: http://pandas.pydata.org/pandas-docs/stable/indexing.html#indexing-view-versus-copy
  
```

https://www.dataquest.io/blog/settingwithcopywarning/

https://stackoverflow.com/questions/31468176/setting-values-on-a-copy-of-a-slice-from-a-dataframe?rq=1



Pandas dType

| Pandas dtype  | Python type | NumPy type                                                   | Usage                             |
| ------------- | ----------- | ------------------------------------------------------------ | --------------------------------- |
| object        | str         | string_, unicode_                                            | Text                              |
| int64         | int         | int_, int8, int16, int32, int64, uint8, uint16, uint32, uint64 | Integer numbers                   |
| float64       | float       | float_, float16, float32, float64                            | Floating point numbers            |
| bool          | bool        | bool_                                                        | True/False values                 |
| datetime64    | NA          | datetime64[ns]                                               | Date and time values              |
| timedelta[ns] | NA          | NA                                                           | Differences between two datetimes |
| category      | NA          | NA                                                           | Finite list of text values        |

http://pbpython.com/pandas_dtypes.html



```python
import re
data_type=data_g["업종명"].str.extractall("일반음식점",regex=True)
#df[df['first_name'].notnull() & (df['nationality'] == "USA")]
#data_g["업종명"] == "일반음식점"
#data_g = data_g.loc[:,"업종명"]
```

```python
data_g.loc[data_g['업종명'] == '일반음식점']
```

the working code I figured out after 2 hours... T_T



but this worked after all?!!

```python
#data_g.loc[data_g['업종명'] == '일반음식점']
data_g = data_g[data_g["업종명"].str.contains("일반음식점", regex=True)]
```

wtf



Don't do this

```python
data_g = data_g[data_g["업종명"].str.contains("일반음식점"|"휴게음식점", regex=True)]
```

Do this instead

```python
data_g = data_g[data_g["업종명"].str.contains("일반음식점|휴게음식점", regex=True)]
```

