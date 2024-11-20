# `multiclass`

## `hamming_dist_matrix`

```
Calculates the hamming distance matrix for a data matrix `X` using SciPy.

Parameters (inputs)
----------
X: a pandas/polars DataFrame or a NumPy array. It represents a data matrix.

Returns (outputs)
-------
M: the hamming distance matrix between the rows of X.
```

### Example


```python
import pandas as pd
from PyDistances.multiclass import hamming_dist_matrix

data_url = "https://raw.githubusercontent.com/FabioScielzoOrtiz/PyDistances-demo/refs/heads/main/data/madrid_houses_processed.csv"

multiclass_cols = ['energy_certificate', 'house_type']

data = pd.read_csv(data_url)

hamming_dist_matrix(X=data[multiclass_cols])
```
```
array([[0. , 0.5, 0.5, ..., 0.5, 1. , 0.5],
       [0.5, 0. , 0. , ..., 0.5, 0.5, 0.5],
       [0.5, 0. , 0. , ..., 0.5, 0.5, 0.5],
       ...,
       [0.5, 0.5, 0.5, ..., 0. , 1. , 0.5],
       [1. , 0.5, 0.5, ..., 1. , 0. , 1. ],
       [0.5, 0.5, 0.5, ..., 0.5, 1. , 0. ]])
```


## `hamming_dist`

```
Calculates the hamming distance between a pair of vectors.

Parameters (inputs)
----------
xi, xr: a pair of quantitative vectors. They represent a couple of statistical observations.

Returns (outputs)
-------
The Matching distance between the observations `xi` and `xr`.
```

### Example

```python
import pandas as pd
from PyDistances.multiclass import hamming_dist

data_url = "https://raw.githubusercontent.com/FabioScielzoOrtiz/PyDistances-demo/refs/heads/main/data/madrid_houses_processed.csv"

multiclass_cols = ['energy_certificate', 'house_type']

data = pd.read_csv(data_url)

xi = data[multiclass_cols].iloc[2,:]
xr = data[multiclass_cols].iloc[10,:]

hamming_dist(xi=xi, xr=xr)
```
```
0.0
```