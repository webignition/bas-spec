============
Tests Suites
============

A test suite is composed of a series of :doc:`tests </tests>`. Tests are defined externally and imported into a suite.

------
Syntax
------

A test suite is a YAML object. An ``import`` property defines the tests to include.

.. include:: includes/syntax/test-suite/test-suite.rst

-------
Example
-------

.. literalinclude:: includes/examples/test/google-search-query-literal.yml
.. literalinclude:: includes/examples/test-suite/google-open-and-query.yml
