Conda Buildpack
===============

This is a fork of Heroku build pack for conda (https://github.com/kennethreitz/conda-buildpack) that supports Python 3.

This buildpack enables the installation of binary packages through the
open source [conda](http://conda.pydata.org/) application.  Conda is
recognized as being core to Continuum's Anaconda Scientific Python distro
but it's also at the heart of the lighter weight
[Miniconda](http://conda.pydata.org/miniconda.html) distro which we use
here to install _only_ the binary packages we need for our apps deployed
on Heroku.

To control what binary packages are installed by conda, supply a
`conda-requirements.txt` file (which can be created by capturing the output
of `conda list -e` for your working conda environment).
Like when using the standard buildpack for python from Heroku, you can also
still supply a `requirements.txt` file for [pip](https://github.com/pypa/pip)
to process.  In this way, you can install binary packages via conda for
everything you can and still use pip for anything you can't.
Usage
-----
