# PyDistances

Data scientists address real-world problems using multivariate and heterogeneous
datasets, characterized by multiple variables of different natures. 
Selecting a suitable
distance function between units is crucial, as many statistical techniques and
machine learning algorithms depend on this concept. 
Traditional distances, like
classical Gower’s or Euclidean, are unsuitable for mixed-type data when underlying
correlation or outlying observations are present, and often lead to suboptimal results.

In the paper ***Grané, A., Scielzo-Ortiz, F.: PyDistances: A Python package for mixed-type
data. Submitted to SORT (2024)*** robust distances for mixed-type data were defined and explored, like **robust
Generalized Gower’s** and **robust Related Metric Scaling**, and this **new Python package** called `PyDistances` was developed, which enables to compute these robust proposals as well as classical ones.

```{tableofcontents}
```
