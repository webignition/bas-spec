==========
Test Steps
==========

A step modifies the browser state and verifies the state using:

- a sequence of :doc:`actions </actions>` to be performed to get the browser into a desired state
- a set of :doc:`assertions </assertions>` to verify the browser state

------
Syntax
------

A step is a YAML object with ``actions`` and ``assertions`` properties. The `actions` property is a list of
:doc:`actions </actions>`. The `assertions` property is a list of :doc:`assertions </assertions>`.

Action arguments and assertion values can be represented by named parameters. Values for parameters are provided by
test suites. Test suites can pass elements as parameter values.

.. include:: includes/syntax/step/step.rst

--------
Examples
--------

**************
Literal Values
**************

.. literalinclude:: includes/examples/step/google-open-literal.yml

********************
Parameterised Values
********************

.. literalinclude:: includes/examples/step/open-url-parameterised.yml

***********************************************
Parameterised Elements and Parameterised Values
***********************************************

.. literalinclude:: includes/examples/step/google-query-page-model.yml