Simple matrix multiplication
================
Oliver Dürr
11/7/2016

In R

``` r
m1_values = matrix(c(3,3), nrow = 1)
m2_values = matrix(c(2,2), nrow = 2)
10 * m1_values %*% m2_values
```

    ##      [,1]
    ## [1,]  120

``` r
#10 * m2_values %*% m1_values
```

In Tensorflow: Building the graph

``` r
library(tensorflow)
tf$reset_default_graph()
m1 = tf$constant(m1_values, name='M1', dtype='float32')
m2 = tf$constant(m2_values, name='M2', dtype='float32')
product = 10*tf$matmul(m1,m2)
```

In Tensorflow: Executung the graph to the tensor "product"

``` r
sess = tf$Session()
res = sess$run(product)
print(res)
```

    ##      [,1]
    ## [1,]  120

``` r
sess$close()
```
