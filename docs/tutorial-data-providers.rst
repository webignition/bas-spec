=====================
Using a Data Provider
=====================

We previously learned how a :doc:`data set list can be passed to a parameterised test step </tutorial-parameterised-tests>`
to run a single step once per set of data.

We defined the data list set within our test. Doing so can get cumbersome over time. An overly-large collection of data
can make the test hard to follow. We run the risk of too-closely coupling that which is being tested with the data
with which it is being tested.

A data provider imported into a test addresses these matters.

------------------------
Creating a Data Provider
------------------------

We create a ``data_providers`` section within our ``imports`` section, choose an import a name and give the
path to our data provider.

Now just pass the import name we chose as the ``data`` property of the test.

.. literalinclude:: includes/examples/data-provider/google-search-query.yml
.. literalinclude:: includes/examples/test/google-search-parameterised-with-data-provider.yml
