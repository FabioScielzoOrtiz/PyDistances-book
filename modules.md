# Modules

## `quantitative`

### `euclidean_dist_matrix`

```
Calculates the Euclidean distance matrix for a data matrix using SciPy.

Parameters (inputs)
----------
X: a Pandas or Polars DataFrame or a NumPy array. It represents a data matrix.

Returns (outputs)
-------
M: the Euclidean distance matrix between the rows of `X`.
```

#### Example
```python
import pandas as pd
from PyDistances.quantitative import euclidean_dist_matrix

data_url = "https://raw.githubusercontent.com/FabioScielzoOrtiz/PyDistances-demo/refs/heads/main/data/madrid_houses_processed.csv"

data = pd.read_csv(data_url)

quant_cols = ['sq_mt_built', 'n_rooms', 'n_bathrooms', 
              'n_floors', 'buy_price']
 
euclidean_dist_matrix(X=data[quant_cols])
```
```
array([[     0.        ,  44900.00041203,  59247.00760376, ...,
        595000.01035798, 610000.04150574, 339000.00009587],
       [ 44900.00041203,      0.        ,  14347.02014357, ...,
        550100.01002272, 565100.04244381, 294100.0000102 ],
       [ 59247.00760376,  14347.02014357,      0.        , ...,
        535753.00612689, 550753.03452909, 279753.00086505],
       ...,
       [595000.01035798, 550100.01002272, 535753.00612689, ...,
             0.        ,  15000.43336041, 256000.02072851],
       [610000.04150574, 565100.04244381, 550753.03452909, ...,
         15000.43336041,      0.        , 271000.08689667],
       [339000.00009587, 294100.0000102 , 279753.00086505, ...,
        256000.02072851, 271000.08689667,      0.        ]])
```

### `euclidean_dist`

```
Calculates the Euclidean distance between a pair of vectors.

Parameters (inputs)
----------
xi, xr: a pair of Pandas or Polars Series or DataFrames, or Numpy arrays. They represent a couple of statistical observations of quantitative variables. 

Returns (outputs)
-------
The Euclidean distance between the observations `xi` and `xr`.
```

#### Example 

```python
import pandas as pd
from PyDistances.quantitative import euclidean_dist

data_url = "https://raw.githubusercontent.com/FabioScielzoOrtiz/PyDistances-demo/refs/heads/main/data/madrid_houses_processed.csv"

data = pd.read_csv(data_url)

quant_cols = ['sq_mt_built', 'n_rooms', 'n_bathrooms', 
              'n_floors', 'buy_price']

xi = data[quant_cols].iloc[2,:]
xr = data[quant_cols].iloc[10,:]

euclidean_dist(xi=xi, xr=xr)
```

```
26247.011906119904
```

### `minkowski_dist_matrix`

```
Calculates the Minkowski distance matrix for a data matrix using SciPy.

Parameters (inputs)
----------
X: a Pandas or Polars DataFrame or a NumPy array. It represents a data matrix.
q: the parameters that defines the Minkowski form. Some particular cases: q=1 := Manhattan, q=2 := Euclidean.

Returns (outputs)
-------
M: the Minkowski(`q`) distance matrix between the rows of `X`.
```

#### Example

```python
import pandas as pd
from PyDistances.quantitative import minkowski_dist_matrix 

data_url = "https://raw.githubusercontent.com/FabioScielzoOrtiz/PyDistances-demo/refs/heads/main/data/madrid_houses_processed.csv"

data = pd.read_csv(data_url)

quant_cols = ['sq_mt_built', 'n_rooms', 'n_bathrooms', 
              'n_floors', 'buy_price']
   
minkowski_dist_matrix(X=data[quant_cols], q=1)
```
```
array([[     0.,  44907.,  59278., ..., 595114., 610231., 339009.],
       [ 44907.,      0.,  14373., ..., 550207., 565324., 294104.],
       [ 59278.,  14373.,      0., ..., 535836., 550953., 279775.],
       ...,
       [595114., 550207., 535836., ...,      0.,  15117., 256105.],
       [610231., 565324., 550953., ...,  15117.,      0., 271222.],
       [339009., 294104., 279775., ..., 256105., 271222.,      0.]])
```

### `minkowski_dist`


```
Calculates the Minkowski distance between a pair of vectors.

Parameters (inputs)
----------
xi, xr: a pair of quantitative vectors. They represent a couple of statistical observations.
q: the parameters that defines the Minkowski form. Some particular cases: q=1 := Manhattan, q=2 := Euclidean.

Returns (outputs)
-------
The Minkowki(`q`) distance between the observations `xi` and `xr`.
```

#### Example


```python
import pandas as pd
from PyDistances.quantitative import minkowski_dist

data_url = "https://raw.githubusercontent.com/FabioScielzoOrtiz/PyDistances-demo/refs/heads/main/data/madrid_houses_processed.csv"

data = pd.read_csv(data_url)

quant_cols = ['sq_mt_built', 'n_rooms', 'n_bathrooms', 
              'n_floors', 'buy_price']

xi = data[quant_cols].iloc[2,:]
xr = data[quant_cols].iloc[10,:]

minkowski_dist(xi=xi, xr=xr, q=1)
```

```
26272.0
```

### `canberra_dist_matrix`

```
Calculates the Canberra distance matrix for a data matrix using SciPy.

Parameters (inputs)
----------
X: a pandas/polars DataFrame or a NumPy array. It represents a data matrix.

Returns (outputs)
-------
M: the Canberra distance matrix between the rows of `X`.
```

#### Example


```python
import pandas as pd
from PyDistances.quantitative import  

data_url = "https://raw.githubusercontent.com/FabioScielzoOrtiz/PyDistances-demo/refs/heads/main/data/madrid_houses_processed.csv"

data = pd.read_csv(data_url)

quant_cols = ['sq_mt_built', 'n_rooms', 'n_bathrooms', 
              'n_floors', 'buy_price']

canberra_dist_matrix(X=data[quant_cols])
```
```
array([[0.        , 0.45371051, 0.78164852, ..., 1.90887959, 2.75277838,
        1.05816865],
       [0.45371051, 0.        , 0.73200803, ..., 1.58398156, 2.43793773,
        1.07838011],
       [0.78164852, 0.73200803, 0.        , ..., 1.28443942, 2.19871833,
        0.62483892],
       ...,
       [1.90887959, 1.58398156, 1.28443942, ..., 0.        , 0.95659875,
        0.98222144],
       [2.75277838, 2.43793773, 2.19871833, ..., 0.95659875, 0.        ,
        1.87662188],
       [1.05816865, 1.07838011, 0.62483892, ..., 0.98222144, 1.87662188,
        0.        ]])
```

### `canberra_dist`

```
Calculates the Canberra distance between a pair of vectors.

Parameters (inputs)
----------
xi, xr: a pair of quantitative vectors. They represent a couple of statistical observations.

Returns (outputs)
-------
The Canberra distance between the observations `xi` and `xr`.
```

#### Example


```python
import pandas as pd
from PyDistances.quantitative import canberra_dist 

data_url = "https://raw.githubusercontent.com/FabioScielzoOrtiz/PyDistances-demo/refs/heads/main/data/madrid_houses_processed.csv"

data = pd.read_csv(data_url)

quant_cols = ['sq_mt_built', 'n_rooms', 'n_bathrooms', 
              'n_floors', 'buy_price']

xi = data[quant_cols].iloc[2,:]
xr = data[quant_cols].iloc[10,:]

canberra_dist(xi=xi, xr=xr)
```
```
0.25345926746669145
```

### `pearson_dist_matrix`

```
Calculates the Pearson distance matrix for a data matrix using SciPy.

Parameters (inputs)
----------
X: a pandas/polars DataFrame or a NumPy array. It represents a data matrix.

Returns (outputs)
-------
M: the Pearson distance matrix between the rows of X.
```

#### Example


```python
import pandas as pd
from PyDistances.quantitative import pearson_dist_matrix  

data_url = "https://raw.githubusercontent.com/FabioScielzoOrtiz/PyDistances-demo/refs/heads/main/data/madrid_houses_processed.csv"

data = pd.read_csv(data_url)

quant_cols = ['sq_mt_built', 'n_rooms', 'n_bathrooms', 
              'n_floors', 'buy_price']

pearson_dist_matrix(X=data[quant_cols])
```
```
array([[0.        , 0.66557805, 0.73750837, ..., 1.81426832, 3.76742474,
        0.83385122],
       [0.66557805, 0.        , 0.98231536, ..., 1.35816365, 3.56285077,
        1.04162306],
       [0.73750837, 0.98231536, 0.        , ..., 1.56993872, 3.47873654,
        0.38187408],
       ...,
       [1.81426832, 1.35816365, 1.56993872, ..., 0.        , 2.98830222,
        1.50055625],
       [3.76742474, 3.56285077, 3.47873654, ..., 2.98830222, 0.        ,
        3.4727102 ],
       [0.83385122, 1.04162306, 0.38187408, ..., 1.50055625, 3.4727102 ,
        0.        ]])
```

### `mahalanobis_dist_matrix`

```
Calculates the Mahalanobis distance matrix for a data matrix using SciPy.

Parameters (inputs)
----------
X: a pandas/polars DataFrame or a NumPy array. It represents a data matrix.

Returns (outputs)
-------
M: the Mahalanobis distance matrix between the rows of X.
```

#### Example


```python
import pandas as pd
from PyDistances.quantitative import  

data_url = "https://raw.githubusercontent.com/FabioScielzoOrtiz/PyDistances-demo/refs/heads/main/data/madrid_houses_processed.csv"

data = pd.read_csv(data_url)

quant_cols = ['sq_mt_built', 'n_rooms', 'n_bathrooms', 
              'n_floors', 'buy_price']

mahalanobis_dist_matrix(X=data[quant_cols])
```
```
array([[0.        , 0.98305366, 1.35352819, ..., 1.51225082, 2.9059013 ,
        1.39140298],
       [0.98305366, 0.        , 2.03435122, ..., 0.95079695, 2.95281549,
        2.01444275],
       [1.35352819, 2.03435122, 0.        , ..., 2.12708355, 3.26187536,
        0.82635883],
       ...,
       [1.51225082, 0.95079695, 2.12708355, ..., 0.        , 3.28213849,
        2.08421407],
       [2.9059013 , 2.95281549, 3.26187536, ..., 3.28213849, 0.        ,
        3.30618935],
       [1.39140298, 2.01444275, 0.82635883, ..., 2.08421407, 3.30618935,
        0.        ]])
```

### `mahalanobis_dist`


```
Calculates the Mahalanobis distance between a pair of vectors.

Parameters (inputs)
----------
xi, xr: a pair of quantitative vectors. They represent a couple of statistical observations.
S: the covariance matrix of the data matrix to which `xi` and `xr` belong.

Returns (outputs)
-------
The Mahalanobis distance between the observations `xi` and `xr`.
```


#### Example


```python
import pandas as pd
from PyDistances.quantitative import  

data_url = "https://raw.githubusercontent.com/FabioScielzoOrtiz/PyDistances-demo/refs/heads/main/data/madrid_houses_processed.csv"

data = pd.read_csv(data_url)

quant_cols = ['sq_mt_built', 'n_rooms', 'n_bathrooms', 
              'n_floors', 'buy_price']

xi = data[quant_cols].iloc[2,:]
xr = data[quant_cols].iloc[10,:]

S = np.cov(data_pd[quant_cols], rowvar=False)

mahalanobis_dist(xi=xi, xr=xr, S=S)
```
```
20524268507.123516
```

### `robust_maha_dist_matrix`


```
Calculates the Robust Mahalanobis distance matrix for a data matrix `X` using SciPy and a robust estimation of the covariance matrix.

Parameters (inputs)
----------
X: a pandas/polars DataFrame or a NumPy array. It represents a data matrix.
S_robust: the robust covariance matrix of `X`.

Returns (outputs)
-------
M: the Robust Mahalanobis distance matrix between the rows of X.
```


#### Example

```python
import pandas as pd
from PyDistances.quantitative import robust_maha_dist_matrix, S_robust  

data_url = "https://raw.githubusercontent.com/FabioScielzoOrtiz/PyDistances-demo/refs/heads/main/data/madrid_houses_processed.csv"

data = pd.read_csv(data_url)

quant_cols = ['sq_mt_built', 'n_rooms', 'n_bathrooms', 
              'n_floors', 'buy_price']        
```

```python
S_robust_estimation = S_robust(X=data[quant_cols], method="trimmed",
                               epsilon=0.05, n_iters=20, alpha=0.07, 
                               weights=None)

robust_maha_dist_matrix(X=data[quant_cols],   
                        S_robust=S_robust_estimation)
```
```
array([[0.        , 1.07619417, 1.52755549, ..., 1.6039788 , 3.03495824,
        1.64495744],
       [1.07619417, 0.        , 2.26168841, ..., 0.93299896, 3.15055951,
        2.09739707],
       [1.52755549, 2.26168841, 0.        , ..., 2.39613957, 3.24280591,
        1.28951587],
       ...,
       [1.6039788 , 0.93299896, 2.39613957, ..., 0.        , 3.48370099,
        2.1326725 ],
       [3.03495824, 3.15055951, 3.24280591, ..., 3.48370099, 0.        ,
        3.52339443],
       [1.64495744, 2.09739707, 1.28951587, ..., 2.1326725 , 3.52339443,
        0.        ]])
```

```python
S_robust_estimation = S_robust(X=data[quant_cols],  
                               method="winsorized", epsilon=0.05, 
                               n_iters=20, alpha=0.07, weights=None)


robust_maha_dist_matrix(X=data[quant_cols],                          
                        S_robust=S_robust_estimation)
```
```
array([[0.        , 1.04388227, 1.52580544, ..., 1.58209452, 2.9790249 ,
        1.62043215],
       [1.04388227, 0.        , 2.1919243 , ..., 0.97608111, 3.02378791,
        2.0634736 ],
       [1.52580544, 2.1919243 , 0.        , ..., 2.25328446, 3.36744463,
        1.21972552],
       ...,
       [1.58209452, 0.97608111, 2.25328446, ..., 0.        , 3.40773227,
        2.09940077],
       [2.9790249 , 3.02378791, 3.36744463, ..., 3.40773227, 0.        ,
        3.42871647],
       [1.62043215, 2.0634736 , 1.21972552, ..., 2.09940077, 3.42871647,
        0.        ]])
```

```python
S_robust_estimation = S_robust(X=data[quant_cols], method="MAD", epsilon=0.05, 
                               n_iters=20, alpha=None, weights=None)

robust_maha_dist_matrix(X=data[quant_cols], S_robust=S_robust_estimation)
```
```
array([[0.        , 0.92229336, 0.97058617, ..., 1.78839817, 3.60593355,
        1.04126762],
       [0.92229336, 0.        , 1.02265462, ..., 1.0354775 , 3.3402759 ,
        1.01713595],
       [0.97058617, 1.02265462, 0.        , ..., 1.4612904 , 3.24480033,
        0.62190049],
       ...,
       [1.78839817, 1.0354775 , 1.4612904 , ..., 0.        , 3.09615949,
        1.35288379],
       [3.60593355, 3.3402759 , 3.24480033, ..., 3.09615949, 0.        ,
        3.39834726],
       [1.04126762, 1.01713595, 0.62190049, ..., 1.35288379, 3.39834726,
        0.        ]])
```

### `robust_maha_dist`

```
Calculates the Robust Mahalanobis distance between a pair of vectors.

Parameters (inputs)
----------
xi, xr: a pair of quantitative vectors. They represent a couple of statistical observations.
S_robust: the robust covariance matrix of the data matrix to which `xi` and `xr` belong.

Returns (outputs)
-------
The Robust Mahalanobis distance between the observations `xi` and `xr`.
```


#### Example

```python
import pandas as pd
from PyDistances.quantitative import robust_maha_dist, S_robust 

data_url = "https://raw.githubusercontent.com/FabioScielzoOrtiz/PyDistances-demo/refs/heads/main/data/madrid_houses_processed.csv"

data = pd.read_csv(data_url)

quant_cols = ['sq_mt_built', 'n_rooms', 'n_bathrooms', 
              'n_floors', 'buy_price']

xi = data[quant_cols].iloc[2,:]
xr = data[quant_cols].iloc[10,:]
```
```python
S_robust_estimation = S_robust(X=data[quant_cols], method="trimmed", 
                               epsilon=0.05, n_iters=20, alpha=0.07, 
                               weights=None)

robust_maha_dist(xi=xi, xr=xr, S_robust=S_robust_estimation)
```
```
0.45774797743084744
```
```python
S_robust_estimation = S_robust(X=data[quant_cols],                   
                               method="winsorized", epsilon=0.05, 
                               n_iters=20, alpha=0.07, weights=None)

robust_maha_dist(xi=xi, xr=xr, S_robust=S_robust_estimation)
```
```
0.45545084258890073
```
```python
S_robust_estimation = S_robust(X=data[quant_cols], method="MAD",
                               epsilon=0.05, n_iters=20, alpha=None,
                               weights=None)

robust_maha_dist(xi=xi, xr=xr, S_robust=S_robust_estimation)
```
```
0.2838731015529872
```


## `binary`




## `multiclass`

## `mixed`