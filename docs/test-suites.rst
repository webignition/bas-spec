===========
Test Suites
===========

A test suite is composed of a series of :doc:`tests </tests>`. Tests may be defined directly within a suite or may be
defined independently and imported into a suite.

------
Syntax
------

A test suite is a YAML object with user-defined named properties where each property defines a test.
Each named property within the test suite defines the :doc:`actions </actions>` and :doc:`assertions </assertions>`
to be performed for a specific test.

.. literalinclude:: includes/syntax/test-suite/define.yml

A test may be defined independently of the test suite and imported in one or more test suites.

Import names are user-defined. Import names for parameterised tests must not the ``actions`` or ``assertions`` keywords.
Import paths are relative to the test suite.

.. literalinclude:: includes/syntax/test-suite/import.yml

A test suite may both define and import tests.

.. literalinclude:: includes/syntax/test-suite/define-and-import.yml

Imported tests that require parameters must have the parameter values passed at usage time.

Data can be supplied via the ``data`` property of the test suite. The ``data`` property can have any number of data
collections. Each data collection contains one or more data sets. Each data set provides values for the parameters
as required by a test.

.. literalinclude:: includes/syntax/test-suite/import-inline-data.yml

Data can be supplied through the import of a data provider. A data provider is a data collection defined externally
to the test suite.

.. literalinclude:: includes/syntax/test-suite/import-data-provider.yml

Page models can be imported and their properties referenced within the test suite.

.. literalinclude:: includes/syntax/test-suite/page-model.yml

--------
Examples
--------

***********************************
Tests Defined Within The test Suite
***********************************

.. literalinclude:: includes/examples/test-suite/google-search-query-literal.yml

***********************************************************
Parameterised Tests With Data Defined Within The test Suite
***********************************************************

.. literalinclude:: includes/examples/test/open-url-parameterised.yml

.. literalinclude:: includes/examples/test-suite/google-open-parameterised.yml

*******************************************************************
Parameterised Tests With Data Supplied By An Imported Data Provider
*******************************************************************

.. literalinclude:: includes/examples/test/google-search-query-parameterised.yml

.. literalinclude:: includes/examples/data-provider/google-search-query.yml

.. literalinclude:: includes/examples/test-suite/google-search-query-parameterised.yml

*************************************************************
Tests Imported Into the Test Suite With Additional Assertions
*************************************************************

.. literalinclude:: includes/examples/test/google-open-literal.yml

.. literalinclude:: includes/examples/test/google-query-example-literal.yml

.. literalinclude:: includes/examples/test-suite/google-import-open-import-query-additional-assertions.yml

***************************************
Page Model Imported Into the Test Suite
***************************************

.. literalinclude:: includes/examples/page-model/google.com.yml

.. literalinclude:: includes/examples/test-suite/google-inline-tests-with-page-model.yml
