
<!-- README.md is generated from README.Rmd. Please edit that file -->

# DoubleML - Double Machine Learning in R

[![build](https://github.com/DoubleML/doubleml-for-r/workflows/build/badge.svg)](https://github.com/DoubleML/doubleml-for-r/actions?query=workflow%3Abuild)
[![CRAN
Version](https://www.r-pkg.org/badges/version/DoubleML)](https://cran.r-project.org/package=DoubleML)

The R package **DoubleML** provides an implementation of the double /
debiased machine learning framework of [Chernozhukov et
al. (2018)](https://arxiv.org/abs/1608.00060). It is built on top of
[mlr3](https://mlr3.mlr-org.com/) and the [mlr3
ecosystem](https://github.com/mlr-org/mlr3/wiki/Extension-Packages)
(Lang et al., 2019).

Note that the R package was developed together with a python twin based
on [scikit-learn](https://scikit-learn.org/). The python package is also
available on [GitHub](https://github.com/DoubleML/doubleml-for-py) and
[![PyPI
version](https://badge.fury.io/py/DoubleML.svg)](https://badge.fury.io/py/DoubleML).

## Documentation and maintenance

Documentation of functions in R:
<https://docs.doubleml.org/r/stable/reference/index.html>

User guide: <https://docs.doubleml.org>

**DoubleML** is currently maintained by
[`@MalteKurz`](https://github.com/MalteKurz) and
[`@PhilippBach`](https://github.com/PhilippBach).

## Main Features

Double / debiased machine learning framework of [Chernozhukov et
al. (2018)](https://arxiv.org/abs/1608.00060) for

-   Partially linear regression models (PLR)
-   Partially linear IV regression models (PLIV)
-   Interactive regression models (IRM)
-   Interactive IV regression models (IIVM)

The object-oriented implementation of **DoubleML** that is based on the
[R6 package for R](https://r6.r-lib.org/) is very flexible. The model
classes `DoubleMLPLR`, `DoubleMLPLIV`, `DoubleMLIRM` and `DoubleIIVM`
implement the estimation of the nuisance functions via machine learning
methods and the computation of the Neyman orthogonal score function. All
other functionalities are implemented in the abstract base class
`DoubleML`. In particular functionalities to estimate double machine
learning models and to perform statistical inference via the methods
`fit`, `bootstrap`, `confint`, `p_adjust` and `tune`. This
object-oriented implementation allows a high flexibility for the model
specification in terms of …

-   … the machine learners for the nuisance functions,
-   … the resampling schemes,
-   … the double machine learning algorithm,
-   … the Neyman orthogonal score functions,
-   …

It further can be readily extended with regards to

-   … new model classes that come with Neyman orthogonal score functions
    being linear in the target parameter,
-   … alternative score functions via callables,
-   … alternative resampling schemes,
-   …

![OOP structure of the DoubleML package](man/figures/oop.svg?raw=true)

## Installation

Install the latest release from CRAN:

``` r
remotes::packages("DoubleML")
```

Install the development version from GitHub:

``` r
remotes::install_github("DoubleML/doubleml-for-r")
```

**DoubleML** requires

-   R (&gt;= 3.5.0)
-   R6 (&gt;= 2.4.1)
-   data.table (&gt;= 1.12.8)
-   stats
-   checkmate
-   mlr3 (&gt;= 0.5.0)
-   mlr3tuning (&gt;= 0.3.0)
-   mvtnorm
-   utils
-   clusterGeneration
-   readstata13

## Citation

If you use the DoubleML package a citation is highly appreciated:

Bach, P., Chernozhukov, V., Kurz, M. S., and Spindler, M. (2020),
DoubleML - Double Machine Learning in R. URL:
<https://github.com/DoubleML/doubleml-for-r>, R-Package version 0.1.0.

Bibtex-entry:

    @Manual{DoubleML2020,
      title = {DoubleML - Double Machine Learning in R},
      author = {Bach, P., Chernozhukov, V., Kurz, M. S., and Spindler, M.},
      year = {2020},
      note = {URL: \url{https://github.com/DoubleML/doubleml-for-r}, R-Package version 0.1.0}
    }

## References

-   Chernozhukov, V., Chetverikov, D., Demirer, M., Duflo, E., Hansen,
    C., Newey, W. and Robins, J. (2018), Double/debiased machine
    learning for treatment and structural parameters. The Econometrics
    Journal, 21: C1-C68, <https://doi.org/10.1111/ectj.12097>.

-   Lang, M., Binder, M., Richter, J., Schratz, P., Pfisterer, F.,
    Coors, S., Au, Q., Casalicchio, G., Kotthoff, L., Bischl, B. (2019),
    mlr3: A modern object-oriented machine learing framework in R.
    Journal of Open Source Software,
    <https://doi.org/10.21105/joss.01903>.
