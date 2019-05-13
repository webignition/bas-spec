==========
Test Steps
==========

A test is composed of steps. A step comprises two parts:

- a sequence of :doc:`actions </actions>` to be performed to get the browser into a desired state
- a set of :doc:`assertions </assertions>` to verify the browser state

------
Syntax
------

A step is a YAML object with ``actions`` and ``assertions`` properties. The `actions` property is a list of
:doc:`actions </actions>`. The `assertions` property is a list of :doc:`assertions </assertions>`.

Action arguments and assertion values can be represented by named parameters. Values for parameters are passed in
:doc:`tests </tests>`.

.. include:: includes/syntax/step/step.rst

Page models can be imported and referenced in actions and assertions:

.. include:: includes/syntax/step/step-page-model.rst

--------
Examples
--------

.. literalinclude:: includes/examples/step/google-open-literal.yml
.. literalinclude:: includes/examples/step/open-url-parameterised.yml
.. literalinclude:: includes/examples/step/google-query-page-model.yml