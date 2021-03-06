==============
Data Providers
==============

A data provider defines a data collection to be used with a parameterised :doc:`test </steps>`.

A data collection contains one or more data sets. Each data set has a name and provides values for the parameters
as required by a test.

------
Syntax
------

A data provider defines a data collection. A data collection is a YAML object with user-defined named properties.
Each property name is the name of a data set. Each data set maps parameter names to parameter values.

.. include:: includes/syntax/data-provider.rst

--------
Examples
--------

.. literalinclude:: includes/examples/data-provider/google-search-query.yml
.. literalinclude:: includes/examples/data-provider/example-sign-in.yml
