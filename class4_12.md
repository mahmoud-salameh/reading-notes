# 10 minutes to pandas

This is a short introduction to pandas, geared mainly for new users. You can see more complex recipes in the 

Customarily, we import as follows:

    In [1]: import numpy as np

    In [2]: import pandas as pd

## Object creation

Creating a Series by passing a list of values, letting pandas create a default integer index:

    In [3]: s = pd.Series([1, 3, 5, np.nan, 6, 8])

    In [4]: s
    Out[4]: 
    0    1.0
    1    3.0
    2    5.0
    3    NaN
    4    6.0
    5    8.0
    
Creating a DataFrame by passing a NumPy array, with a datetime index and labeled columns:


    In [5]: dates = pd.date_range("20130101", periods=6)

    In [6]: dates
    Out[6]: 
    DatetimeIndex(['2013-01-01', '2013-01-02', '2013-01-03', '2013-01-04',
                '2013-01-05', '2013-01-06'],
                dtype='datetime64[ns]', freq='D')

    In [7]: df = pd.DataFrame(np.random.randn(6, 4), index=dates, columns=list("ABCD"))

    In [8]: df
    Out[8]: 
                    A         B         C         D
    2013-01-01  0.469112 -0.282863 -1.509059 -1.135632
    2013-01-02  1.212112 -0.173215  0.119209 -1.044236
    2013-01-03 -0.861849 -2.104569 -0.494929  1.071804
    2013-01-04  0.721555 -0.706771 -1.039575  0.271860
    2013-01-05 -0.424972  0.567020  0.276232 -1.087401
    2013-01-06 -0.673690  0.113648 -1.478427  0.524988

Creating a DataFrame by passing a dict of objects that can be converted to series-like.

    In [9]: df2 = pd.DataFrame(
    ...:     {
    ...:         "A": 1.0,
    ...:         "B": pd.Timestamp("20130102"),
    ...:         "C": pd.Series(1, index=list(range(4)), dtype="float32"),
    ...:         "D": np.array([3] * 4, dtype="int32"),
    ...:         "E": pd.Categorical(["test", "train", "test", "train"]),
    ...:         "F": "foo",
    ...:     }
    ...: )
    ...: 

    In [10]: df2
    Out[10]: 
        A          B    C  D      E    F
    0  1.0 2013-01-02  1.0  3   test  foo
    1  1.0 2013-01-02  1.0  3  train  foo
    2  1.0 2013-01-02  1.0  3   test  foo
    3  1.0 2013-01-02  1.0  3  train  foo

The columns of the resulting DataFrame have different dtypes.

    In [11]: df2.dtypes
    Out[11]: 
    A           float64
    B    datetime64[ns]
    C           float32
    D             int32
    E          category
    F            object
    dtype: object

## Viewing data

Here is how to view the top and bottom rows of the frame:

    In [13]: df.head()
    Out[13]: 
                    A         B         C         D
    2013-01-01  0.469112 -0.282863 -1.509059 -1.135632
    2013-01-02  1.212112 -0.173215  0.119209 -1.044236
    2013-01-03 -0.861849 -2.104569 -0.494929  1.071804
    2013-01-04  0.721555 -0.706771 -1.039575  0.271860
    2013-01-05 -0.424972  0.567020  0.276232 -1.087401

    In [14]: df.tail(3)
    Out[14]: 
                    A         B         C         D
    2013-01-04  0.721555 -0.706771 -1.039575  0.271860
    2013-01-05 -0.424972  0.567020  0.276232 -1.087401
    2013-01-06 -0.673690  0.113648 -1.478427  0.524988


Display the index, columns:


    In [15]: df.index
    Out[15]: 
    DatetimeIndex(['2013-01-01', '2013-01-02', '2013-01-03', '2013-01-04',
                '2013-01-05', '2013-01-06'],
                dtype='datetime64[ns]', freq='D')

    In [16]: df.columns
    Out[16]: Index(['A', 'B', 'C', 'D'], dtype='object')

__DataFrame.to_numpy() gives a NumPy representation of the underlying data. Note that this can be an expensive operation when your DataFrame has columns with different data types, which comes down to a fundamental difference between pandas and NumPy: NumPy arrays have one dtype for the entire array, while pandas DataFrames have one dtype per column. When you call DataFrame.to_numpy(), pandas will find the NumPy dtype that can hold all of the dtypes in the DataFrame. This may end up being object, which requires casting every value to a Python object.__

    In [17]: df.to_numpy()
    Out[17]: 
    array([[ 0.4691, -0.2829, -1.5091, -1.1356],
        [ 1.2121, -0.1732,  0.1192, -1.0442],
        [-0.8618, -2.1046, -0.4949,  1.0718],
        [ 0.7216, -0.7068, -1.0396,  0.2719],
        [-0.425 ,  0.567 ,  0.2762, -1.0874],
        [-0.6737,  0.1136, -1.4784,  0.525 ]])

For df2, the DataFrame with multiple dtypes, DataFrame.to_numpy() is relatively expensive

    In [18]: df2.to_numpy()
    Out[18]: 
    array([[1.0, Timestamp('2013-01-02 00:00:00'), 1.0, 3, 'test', 'foo'],
        [1.0, Timestamp('2013-01-02 00:00:00'), 1.0, 3, 'train', 'foo'],
        [1.0, Timestamp('2013-01-02 00:00:00'), 1.0, 3, 'test', 'foo'],
        [1.0, Timestamp('2013-01-02 00:00:00'), 1.0, 3, 'train', 'foo']],
        dtype=object)

describe() shows a quick statistic summary of your data:

    In [19]: df.describe()
    Out[19]: 
                A         B         C         D
    count  6.000000  6.000000  6.000000  6.000000
    mean   0.073711 -0.431125 -0.687758 -0.233103
    std    0.843157  0.922818  0.779887  0.973118
    min   -0.861849 -2.104569 -1.509059 -1.135632
    25%   -0.611510 -0.600794 -1.368714 -1.076610
    50%    0.022070 -0.228039 -0.767252 -0.386188
    75%    0.658444  0.041933 -0.034326  0.461706
    max    1.212112  0.567020  0.276232  1.071804

### Selection

__Getting__

Selecting a single column, which yields a Series, equivalent to df.A:

    In [23]: df["A"]
    Out[23]: 
    2013-01-01    0.469112
    2013-01-02    1.212112
    2013-01-03   -0.861849
    2013-01-04    0.721555
    2013-01-05   -0.424972
    2013-01-06   -0.673690
    Freq: D, Name: A, dtype: float64