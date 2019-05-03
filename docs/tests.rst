=====
Tests
=====

A test comprises two parts:

- a sequence of :doc:`actions </actions>` to be performed to get the browser into a desired state
- a set of :doc:`assertions </assertions>` to verify the browser state

------
Syntax
------

A test is a YAML object with ``actions`` and ``assertions`` properties.

The `actions` property is a list of :doc:`actions </actions>`.
The `assertions` property is a list of :doc:`assertions </assertions>`.

Action arguments and assertion values can be represented by named parameters. Values for parameters are passed in
:doc:`test suites </test-suites>`.

.. code-block:: yaml

    actions:
      - ...
      - ...
      - ...

    assertions:
      - ...
      - ...
      - ...

--------
Examples
--------

******************
Without Parameters
******************

.. code-block:: yaml

    actions:
      - open "https://example.com"

    assertions:
      - browser.url is https://example.com
      - browser.title is Example Domain

***************
With Parameters
***************

.. code-block:: yaml

    actions:
      - open {{ url }}

    assertions:
      - browser.url is {{ url }}
      - browser.title is {{ expected_title }}
