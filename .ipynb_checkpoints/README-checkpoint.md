Making sense of rCCA, with `pyrcca`, `cca` in `scikit-learn`, and the R libraries `CCA` and `mixOmics`

### Definitions

For each vector **x<sub>1</sub>**...**x<sub>n</sub>** and **y<sub>1</sub>**...**y<sub>m</sub>** in input matrices **X** and **Y** respectively, canonical correlation analysis constructs two **canonical variates**: CVX<sub>1</sub> = a<sub>1</sub>x<sub>1</sub> + … + a<sub>p</sub>x<sub>p</sub> and CVY<sub>1</sub> = b<sub>1</sub>y<sub>1</sub> + … + b<sub>q</sub>y<sub>q</sub>. 

* The **canonical weights** `a<sub>1</sub>…a<sub>n</sub>` and `b<sub>1</sub>…b<sub>m</sub>` are chosen so that they maximize the correlation between the canonical variates `CVX<sub>1</sub>` and `CVY<sub>1</sub>`. The weights themselves don't mean much, so don't read too much into them. 
* The **canonical loadings** are the correlations between the original variables and the canonical variates. 



### Datasets

1. Nutrimouse: lipids and genes
2. NYC schools dataset
3. Example sales dataset

### Matrix dimensions

```
# inputs
X.shape = (n_samples, n_xfeatures)
Y.shape = (n_samples, n_yfeatures)
n_components =< min(n_xfeatures, n_yfeatures)
# if n_samples > n_features, normal CCA
# else, regularized CCA

# canonical correlation
cancorr.shape = (n_components, 1)

# Weights
a.shape = (n_xfeatures, n_comp)
b.shape = (n_yfeatures, n_comp)

# Canonical variates
# where CVx = (a.t %*% X).t
CVx.shape = (n_xfeatures, n_comp)
CVy.shape = (n_yfeatures, n_comp)

# canonical loadings := corr(original variable, its canonical variate)

```