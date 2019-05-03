==============
Data Providers
==============

A data provider defines a data collection to be used with a parameterised :doc:`test </tests>`.

A data collection contains one or more data sets. Each data set provides values for the parameters
as required by a test.

------
Syntax
------

A test suite is a YAML object with user-defined named properties. Each property name is the name of a data set.
Each data set maps parameter names to parameter values.

.. literalinclude:: includes/syntax/data-provider.yml

--------
Examples
--------

*******************************************************************
Parameterised Tests With Data Supplied By An Imported Data Provider
*******************************************************************

.. literalinclude:: includes/examples/test/google-search-query-parameterised.yml

.. literalinclude:: includes/examples/data-provider/google-search-query.yml

.. literalinclude:: includes/examples/test-suite/google-search-query-parameterised.yml
