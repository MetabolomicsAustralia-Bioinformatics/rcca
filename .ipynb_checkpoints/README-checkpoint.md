Making sense of rCCA, with `pyrcca`, `cca` in `scikit-learn`, and the R libraries `CCA` and `mixOmics`

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