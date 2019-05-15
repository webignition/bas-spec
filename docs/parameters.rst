==========
Parameters
==========

Parameters may be used within :doc:`actions </actions>`, :doc:`assertions </assertions>` and
:doc:`data providers </data-providers>`.

A parameter is prefixed with ``$``. This denotes that something is a parameter and not a literal value.

There are five types of parameter:

- built-in objects
- test configuration
- data parameters
- element parameters
- environment variables

.. _parameters-built-in:

----------------
Built-in Objects
----------------

:doc:`Browser properties </browser-properties>` and :doc:`page properties </page-properties>` are built-in objects
that can be referenced in :doc:`actions </actions>` and :doc:`assertions </assertions>`.

Use ``$browser.{name}`` and ``$page.{name}`` to reference these built-in objects.

.. literalinclude:: includes/examples/step/browser-size.yml
.. literalinclude:: includes/examples/step/google-assert-open-literal.yml

------------------
Test Configuration
------------------

The ``config`` section of a test is referenced within the test using ``$config.{name}``.

.. literalinclude:: includes/examples/test/about-google-verify-opened-page.yml

---------------
Data Parameters
---------------

Data parameters can be used in :doc:`actions </actions>` and :doc:`assertions </assertions>`. Literal values are
replaced with data parameters.

Data is passed to a test step from a test. Data passed to a test step is referenced within the step using
``$data.{name}``.

.. literalinclude:: includes/examples/step/assert-page-open-parameterised.yml
.. literalinclude:: includes/examples/test/google-open-parameterised.yml

------------------
Element Parameters
------------------

Element parameters can be used in the :doc:`identifiers </identifiers>` of :doc:`actions </actions>` and
:doc:`assertions </assertions>`. Identifiers are replaced with element parameters.

Elements are passed to a test step from a test. Elements passed to a test step are referenced using ``$elements.{name}``.

.. literalinclude:: includes/examples/step/google-query-parameterised.yml
.. literalinclude:: includes/examples/page/google.com.yml
.. literalinclude:: includes/examples/test/google-imported-steps-with-page-model.yml

.. _parameters-environment-variables:

---------------------
Environment Variables
---------------------

Environment variables can be treated as parameters within :doc:`actions </actions>`, :doc:`assertions </assertions>` and
:doc:`data providers </data-providers>`. Values can be referenced using ``$env.{name}``.

.. literalinclude:: includes/examples/data-provider/example-sign-in.yml
