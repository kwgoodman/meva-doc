====
MEVA
====

Introduction
============

Meva contains two mean-variance portfolio optimizers: an analytical
optimizer and a numerical optimizer. Both are single-period optimizers.

**Analytical optimizer**

The analytical optimizer ``aopt()`` handles linear equality constraints and
soft linear equality constraints (a penalty proportional to the squared
deviation from equality is subtracted from the objective function).

**Numerical optimizer**

The numerical optimizer ``nopt()`` is a long-short optimizer that allows you
to separately specify the sum of the negative portfolio weights and the sum
of the positive weights. It handles soft linear equality constraints,
inequality constraints (implemented as iterative soft constraints),
turnover constraints (iteratively multiplying linear transaction costs),
and (linear and quadratic) transaction costs.

**Covariance estimation**

Both portfolio optimizers need an estimate of the covariance matrix of
asset returns. Meva contains two algorithms to estimate the covariance
matrix: ``cov_pca()`` which is base on principal component analysis and
``cov_fa()`` which is based on factor analysis.

Documentation
=============

- https://kwgoodman.github.io/meva-doc

Install
=======

Requirements:

======================== ===============================
meva                     python, numpy
speed                    accelerated BLAS such as ATLAS
unit tests               nose
======================== ===============================

Meva is a pure Python package. To install, all you have to do is to make
sure Python can find the meva directory. Or you can install the traditional
way::

    $ python setup.py build
    $ sudo python setup.py install

After you have installed meva, run the unit test suite::

    >>> import meva
    >>> meva.test()
    <snip>
    Ran 33 tests in 7.038s
    OK (KNOWNFAIL=1)
    <nose.result.TextTestResult run=33 errors=0 failures=0>
