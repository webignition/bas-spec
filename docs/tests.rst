=====
Tests
=====

A test is composed of a series of :doc:`steps </steps>`.
Steps may be defined directly within a test or may be defined independently and imported into a test. A test may
import steps, may import page models and may import data providers.

------
Syntax
------

A test is a YAML object. The most basic test specifies the ``browser`` and starting ``url`` and defines steps directly.

.. include:: includes/syntax/test/test.rst

A step may be defined independently of the test and imported into any number of tests. Import names are user-defined.
Import paths are relative to the test.

.. include:: includes/syntax/test/import.rst

A test may both define and import steps.

.. include:: includes/syntax/test/define-and-import.rst

Imported steps that require parameters must have the parameter values passed at usage time.

Data can be supplied via the ``data`` property of the step. The ``data`` property can define one or more data sets.
Each data set provides values for the parameters as required by a step.

.. include:: includes/syntax/test/import-inline-data.rst

Data can be supplied through the import of a data provider. A data provider is a collection of data sets defined externally
to the test.

.. include:: includes/syntax/test/import-provided-data.rst

Page models can be imported and their defined page properties referenced within the test.

.. include:: includes/syntax/test/page-model.rst

--------
Examples
--------

*************************
Steps With Literal Values
*************************

.. literalinclude:: includes/examples/test/google-search-query-literal.yml

************************************
Parameterised Steps With Inline Data
************************************

.. literalinclude:: includes/examples/step/assert-page-open-parameterised.yml
.. literalinclude:: includes/examples/test/google-open-parameterised.yml

**************************************
Parameterised Steps With Provided Data
**************************************

.. literalinclude:: includes/examples/step/google-search-query-parameterised.yml
.. literalinclude:: includes/examples/data-provider/google-search-query.yml
.. literalinclude:: includes/examples/test/google-search-query-parameterised.yml

*******************************************************
Steps Imported Into the Test With Additional Assertions
*******************************************************

.. literalinclude:: includes/examples/step/google-assert-open-literal.yml
.. literalinclude:: includes/examples/step/google-query-example-literal.yml
.. literalinclude:: includes/examples/test/google-import-assert-open-import-query-additional-assertions.yml

*********************************************
Imported Page Model Used Directly Within Test
*********************************************

.. literalinclude:: includes/examples/page/google.com.yml
.. literalinclude:: includes/examples/test/google-inline-steps-with-page-model.yml

****************************************************
Imported Page Model Elements Passed To Imported Step
****************************************************

.. literalinclude:: includes/examples/page/google.com.yml
.. literalinclude:: includes/examples/step/google-query-parameterised.yml
.. literalinclude:: includes/examples/test/google-imported-steps-with-page-model.yml