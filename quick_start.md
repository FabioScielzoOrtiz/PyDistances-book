# Quick start

## Requirements 

```


## Installation

```python
pip install PyDistances
```

To see the available versions of the package go to the release history at https://pypi.org/project/PyDistances/#history



## Example


```python
from PyDistances.mixed import GGowerDistMatrix

data_url = "https://raw.githubusercontent.com/FabioScielzoOrtiz/PyDistances-demo/refs/heads/main/data/madrid_houses_processed.csv"

data = pd.read_csv(data_url)

quant_cols = ['sq_mt_built', 'n_rooms', 'n_bathrooms', 'n_floors', 'buy_price']
binary_cols = ['is_renewal_needed', 'has_lift', 'is_exterior', 'has_parking']
multiclass_cols = ['energy_certificate', 'house_type']

p1 = len(quant_cols)
p2 = len(binary_cols)
p3 = len(multiclass_cols)

ggower_dist_matrix = GGowerDistMatrix(p1=p1, p2=p2, p3=p3,
                                      d1="robust_mahalanobis", d2="jaccard", d3="hamming",
                                      robust_method="trimmed", alpha=0.07, epsilon=0.05, 
                                      n_iters=20, weights=None)

ggower_dist_matrix.compute(X=data)
```
```
array([[0.        , 2.21871457, 1.93429293, ..., 1.94305438, 3.1223396 ,
        2.26768279],
       [2.21871457, 0.        , 1.22327246, ..., 2.38753004, 2.64304949,
        2.00865696],
       [1.93429293, 1.22327246, 0.        , ..., 2.36077974, 2.50019632,
        1.63811682],
       ...,
       [1.94305438, 2.38753004, 2.36077974, ..., 0.        , 2.9036275 ,
        1.75869492],
       [3.1223396 , 2.64304949, 2.50019632, ..., 2.9036275 , 0.        ,
        3.03987403],
       [2.26768279, 2.00865696, 1.63811682, ..., 1.75869492, 3.03987403,
        0.        ]])
```
