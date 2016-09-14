# Glmnet for python 

## Introduction

This is a python version of the popular `glmnet` library. Glmnet fits the entire lasso or elastic-net regularization path for `linear` regression, `logistic` and `multinomial` regression models, `poisson` regression and the `cox` model. This is a beta-release. 

The underlying fortran codes are the same as the `R` version, and uses a cyclical path-wise coordinate descent algorithm as described in the papers linked below. 

Currently, `glmnet` calls for gaussian, multi-variate gaussian, binomial, multinomial, poisson and cox models are implemented for both normal and sparse matrices.

Additionally, cross-validation is also implemented for gaussian, binomial and multinomial models. CV for multi-variate gaussian, cox and poisson models are yet to be implemented. Note that all CV is done serially in the current version. Parallel versions will be implemented in the future.

During installation, the fortran code is compiled in the local machine using `gfortran`, and is called by the python code. 

**The best starting point to use this library is to start with the Jupyter notebooks in the `test` directory (glmnet_examples.ipynb).**

## Installation

Unzip the package into a suitable location.

Recompile the GLMnet.so shared library (located in ./lib) using:

    gfortran GLMnet.f -fPIC -fdefault-real-8 -shared -o GLMnet.so
 
Currently, the checked-in version of GLMnet.so is compiled for the following config:

 **Linux:** Linux version 2.6.32-573.26.1.el6.x86_64 (gcc version 4.4.7 20120313 (Red Hat 4.4.7-16) (GCC) ) 
 **OS:** CentOS 6.7 (Final) 
 **Hardware:** 8-core Intel(R) Core(TM) i7-2630QM 
 **gfortran:** version 4.4.7 20120313 (Red Hat 4.4.7-17) (GCC)
 
## Authors:

Algorithm was designed by Jerome Friedman, Trevor Hastie and Rob Tibshirani. Fortran code was written by Jerome Friedman. R wrapper (from which the MATLAB wrapper was adapted) was written by Trevor Hastie.

The original MATLAB wrapper was written by Hui Jiang (14 Jul 2009), and was updated and is maintained by Junyang Qian (30 Aug 2013).

This python wrapper (which was adapted from the MATLAB and R wrappers) was written by B. J. Balakumar, bbalasub@stanford.edu (5 Sep 2016).

Department of Statistics, Stanford University, Stanford, California, USA. 

REFERENCES:
* Friedman, J., Hastie, T. and Tibshirani, R. (2008) Regularization Paths for Generalized Linear Models via Coordinate Descent, 
http://www.jstatsoft.org/v33/i01/
*Journal of Statistical Software, Vol. 33(1), 1-22 Feb 2010*
    
* Simon, N., Friedman, J., Hastie, T., Tibshirani, R. (2011) Regularization Paths for Cox's Proportional Hazards Model via Coordinate Descent,
http://www.jstatsoft.org/v39/i05/
*Journal of Statistical Software, Vol. 39(5) 1-13*

* Tibshirani, Robert., Bien, J., Friedman, J.,Hastie, T.,Simon, N.,Taylor, J. and Tibshirani, Ryan. (2010) Strong Rules for Discarding Predictors in Lasso-type Problems,
http://www-stat.stanford.edu/~tibs/ftp/strong.pdf
*Stanford Statistics Technical Report*

