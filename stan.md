## stan

### `parameters` block

Not specifying a prior leads to an implicit (_improper_) uniform prior on non-negative real numbers.

### `model` block

`target += normal_lpdf(y | mu, sigma);`

is equivalent to

`y ~ normal(mu, sigma);`
