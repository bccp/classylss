classylss
----------

.. image:: https://img.shields.io/pypi/v/classylss.svg
   :alt: PyPi
   :target: https://pypi.python.org/pypi/classylss/

.. image:: https://zenodo.org/badge/61589760.svg
   :target: https://zenodo.org/badge/latestdoi/61589760

|

A lightweight Python binding of the CMB Boltzmann code `CLASS`, which extends the information available in the default wrapper. There is an emphasis on the routines that are important for large-scale structure calculations. The main modules of the CLASS code are exposed to the user via a Cython wrapper.

.. _`CLASS` : http://class-code.net

Documentation
-------------

Installation instructions, examples, and API reference are availabe on ReadTheDocs: http://classylss.readthedocs.io/.

Dependencies
------------

The package is lightweight and the only dependencies are:

- numpy
- cython

The CLASS code will automatically be downloaded and compiled, and is thus, not an external dependency for the user. However, the user will need a valid C compiler to compile the CLASS code. The version of CLASS compiled by the code is stored in the variable ``classylss.class_version``.

Installation
------------

The package can be installed via the `pip` command

.. code:: bash

   pip install classylss
   
The package can be also be downloaded from github using

.. code:: bash

    git clone https://github.com/sbird/classylss.git
    cd classylss

To verify that the installation has succeeded, run:

.. code-block:: python

    import classylss
    
Examples
--------

See the tests of the code in ``classylss/tests/`` for examples of using each of the main CLASS modules. 
