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

Action arguments and assertion values can be represented by placeholders. Values for placeholders are passed in
test suites.

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

********************
Without Placeholders
********************

.. code-block:: yaml

    actions:
      - open "https://example.com"

    assertions:
      - browser.url is https://example.com
      - browser.title is Example Domain

*****************
With Placeholders
*****************

.. code-block:: yaml

    actions:
      - open {{ url }}

    assertions:
      - browser.url is {{ url }}
      - browser.title is {{ expected_title }}
