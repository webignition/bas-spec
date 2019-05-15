==========
Test Steps
==========

A step modifies the browser state and verifies the state using:

- an optional sequence of :doc:`actions </actions>` to be performed to get the browser into a desired state
- a set of :doc:`assertions </assertions>` to verify the browser state

------
Syntax
------

A step is a YAML object with ``actions`` and ``assertions`` properties. The `actions` property is a list of
:doc:`actions </actions>`. The `assertions` property is a list of :doc:`assertions </assertions>`.

Action arguments and assertion values can be represented by named parameters. Values for parameters are provided by
test suites.

.. include:: includes/syntax/step/step.rst

Actions are optional. Assertions are non-optional. A step can omit actions.

.. include:: includes/syntax/step/step-no-actions.rst

--------
Examples
--------

**************
Literal Values
**************

.. literalinclude:: includes/examples/step/google-assert-open-literal.yml

********************
Parameterised Values
********************

.. literalinclude:: includes/examples/step/assert-page-open-parameterised.yml

***********************************************
Parameterised Elements and Parameterised Values
***********************************************

.. literalinclude:: includes/examples/step/google-query-parameterised.yml

**********
No Actions
**********

.. literalinclude:: includes/examples/step/google-homepage-assertions.yml
