=====
Tests
=====

A test comprises two parts:

- a sequence of :doc:`actions </actions>` to be performed to get the browser into a desired state
- a set of :doc:`assertions </assertions>` to verify the browser state

------
Syntax
------

A test is a YAML object with ``actions`` and ``assertions`` properties. The `actions` property is a list of
:doc:`actions </actions>`. The `assertions` property is a list of :doc:`assertions </assertions>`.

Action arguments and assertion values can be represented by named parameters. Values for parameters are passed in
:doc:`test suites </test-suites>`.

.. include:: includes/syntax/test/test.rst

Page models can be imported and referenced in actions and assertions:

.. include:: includes/syntax/test/test-page-model.rst

--------
Examples
--------

.. literalinclude:: includes/examples/test/google-open-literal.yml
.. literalinclude:: includes/examples/test/open-url-parameterised.yml
.. literalinclude:: includes/examples/test/google-query-page-model.yml