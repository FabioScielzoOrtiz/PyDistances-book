# `binary`

## `sokal_dist_matrix`

```
Calculates the Sokal distance matrix for a data matrix `X` using SciPy.

Parameters (inputs)
----------
X: a pandas/polars DataFrame or a NumPy array. It represents a data matrix.

Returns (outputs)
-------
M: the Sokal distance matrix between the rows of X.
```

### Example

```python
import pandas as pd
from PyDistances.binary import jaccard_dist_matrix

data_url = "https://raw.githubusercontent.com/FabioScielzoOrtiz/PyDistances-demo/refs/heads/main/data/madrid_houses_processed.csv"

binary_cols = ['is_renewal_needed', 'has_lift', 'is_exterior', 'has_parking']

data = pd.read_csv(data_url)

sokal_dist_matrix(X=data[binary_cols])
```
```
array([[0.        , 0.66666667, 0.4       , ..., 0.4       , 0.4       ,
        0.66666667],
       [0.66666667, 0.        , 0.4       , ..., 0.85714286, 0.85714286,
        0.66666667],
       [0.4       , 0.4       , 0.        , ..., 0.66666667, 0.66666667,
        0.4       ],
       ...,
       [0.4       , 0.85714286, 0.66666667, ..., 0.        , 0.        ,
        0.4       ],
       [0.4       , 0.85714286, 0.66666667, ..., 0.        , 0.        ,
        0.4       ],
       [0.66666667, 0.66666667, 0.4       , ..., 0.4       , 0.4       ,
        0.        ]])
```

## `sokal_dist`


```
Calculates the Sokal distance between a pair of vectors.

Parameters (inputs)
----------
xi, xr: a pair of quantitative vectors. They represent a couple of statistical observations.

Returns (outputs)
-------
The Sokal distance between the observations `xi` and `xr`.
```

### Example


```python
import pandas as pd
from PyDistances.binary import jaccard_dist_matrix

data_url = "https://raw.githubusercontent.com/FabioScielzoOrtiz/PyDistances-demo/refs/heads/main/data/madrid_houses_processed.csv"

binary_cols = ['is_renewal_needed', 'has_lift', 'is_exterior', 'has_parking']

data = pd.read_csv(data_url)

xi = data[binary_cols].iloc[2,:]
xr = data[binary_cols].iloc[10,:]

sokal_dist(xi=xi, xr=xr)
```
```
0.6666666666666666
```

## `jaccard_dist_matrix`


```
Calculates the Jaccard distance matrix for a data matrix `X` using SciPy.

Parameters (inputs)
----------
X: a pandas/polars DataFrame or a NumPy array. It represents a data matrix.

Returns (outputs)
-------
M: the Jaccard distance matrix between the rows of X.
```

### Example

```python
import pandas as pd
from PyDistances.binary import jaccard_dist_matrix

data_url = "https://raw.githubusercontent.com/FabioScielzoOrtiz/PyDistances-demo/refs/heads/main/data/madrid_houses_processed.csv"

binary_cols = ['is_renewal_needed', 'has_lift', 'is_exterior', 'has_parking']

data = pd.read_csv(data_url)

jaccard_dist_matrix(X=data[binary_cols])
```
```
array([[0.        , 0.66666667, 0.5       , ..., 0.5       , 0.5       ,
        0.66666667],
       [0.66666667, 0.        , 0.33333333, ..., 0.75      , 0.75      ,
        0.5       ],
       [0.5       , 0.33333333, 0.        , ..., 0.66666667, 0.66666667,
        0.33333333],
       ...,
       [0.5       , 0.75      , 0.66666667, ..., 0.        , 0.        ,
        0.33333333],
       [0.5       , 0.75      , 0.66666667, ..., 0.        , 0.        ,
        0.33333333],
       [0.66666667, 0.5       , 0.33333333, ..., 0.33333333, 0.33333333,
        0.        ]])
```

## `jaccard_dist` 

```
Calculates the Jaccard distance between a pair of vectors.

Parameters (inputs)
----------
xi, xr: a pair of quantitative vectors. They represent a couple of statistical observations.

Returns (outputs)
-------
The Jaccard distance between the observations `xi` and `xr`.
```

### Example

```python
import pandas as pd
from PyDistances.binary import jaccard_dist

data_url = "https://raw.githubusercontent.com/FabioScielzoOrtiz/PyDistances-demo/refs/heads/main/data/madrid_houses_processed.csv"

binary_cols = ['is_renewal_needed', 'has_lift', 'is_exterior', 'has_parking']

data = pd.read_csv(data_url)

xi = data[binary_cols].iloc[2,:]
xr = data[binary_cols].iloc[10,:]

jaccard_dist(xi=xi, xr=xr)
```
```
0.6666666666666666
```

