=====================
Using a Data Provider
=====================

We previously learned how a :doc:`data collection can be passed to a parameterised test </tutorial-parameterised-tests>`
to run a single test once per set of data.

We defined a data collection within our test suite. Doing so can get cumbersome over time. An overly-large data collection
can make the test suite hard to follow. We run the risk of too-closely coupling that which is being tested with the data
with which it is being tested.

A data provider imported into a test suite solves addresses these matters.

------------------------
Creating a Data Provider
------------------------

We create a ``data_providers`` object within our existing ``imports`` object, choose an import a name and give the
path to our data provider.

Now just pass the import name we chose as the ``data`` property of the test.

.. literalinclude:: includes/examples/data-provider/google-search-query.yml
.. literalinclude:: includes/examples/test/google-search-parameterised-with-data-provider.yml
