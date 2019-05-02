==========
Assertions
==========

Assertions are used to verify that the browser is in the desired state.

------
Syntax
------

An assertion takes the form of an ``identifier`` followed by a ``comparison`` and an optional ``value``.

``{identifier} {comparison} [{value}]``

---------------
Comparison List
---------------

- :ref:`is <comparisons-is>`
- :ref:`is-not <comparisons-is-not>`
- :ref:`includes <comparisons-includes>`
- :ref:`excludes <comparisons-excludes>`
- :ref:`matches <comparisons-matches>`

.. _comparisons-is:

--
is
--

Checks if the value being compared equals a given value.

``{identifier} is {value}``

Everything after the ``is`` keyword (except the space after the keyword) is the value to be used.

*********
Arguments
*********

.. list-table::
    :widths: 10 90
    :stub-columns: 1

    * - ``identifier``
      - Any valid identifier.
    * - ``value``
      - Any string.

********
Examples
********

- ``browser.title is Homepage``
- ``browser.title is "Homepage"`` (literal double quotes)
- ``imported_page_model.elements.sign_in_button is Sign in``

.. _comparisons-is-not:

------
is-not
------

Checks if the value being compared does not equal a given value.

``{identifier} is-not {value}``

Everything after the ``is-not`` keyword (except the space after the keyword) is the value to be used.

*********
Arguments
*********

.. list-table::
    :widths: 10 90
    :stub-columns: 1

    * - ``identifier``
      - Any valid identifier.
    * - ``value``
      - Any string.

********
Examples
********

- ``browser.title is-not Homepage``
- ``browser.title is-not "Homepage"`` (literal double quotes)
- ``imported_page_model.elements.sign_out_button is-not Sign in``

.. _comparisons-includes:

--------
includes
--------

Checks if the value being compared contains a given value.

``{identifier} includes {value}``

Everything after the ``includes`` keyword (except the space after the keyword) is the value to be used.

*********
Arguments
*********

.. list-table::
    :widths: 10 90
    :stub-columns: 1

    * - ``identifier``
      - Any valid identifier.
    * - ``value``
      - Any string.

********
Examples
********

- ``browser.title includes page``
- ``imported_page_model.elements.sign_in_button includes Sign``

.. _comparisons-excludes:

--------
excludes
--------

Checks if the value being compared does not contain a given value.

``{identifier} excludes {value}``

Everything after the ``excludes`` keyword (except the space after the keyword) is the value to be used.

*********
Arguments
*********

.. list-table::
    :widths: 10 90
    :stub-columns: 1

    * - ``identifier``
      - Any valid identifier.
    * - ``value``
      - Any string.

********
Examples
********

- ``browser.title excludes error``
- ``imported_page_model.elements.sign_in_button excludes Log``

.. _comparisons-matches:

-------
matches
-------

Checks if the value being compared matches a given regular expression.

``{identifier} matches {value}``

Everything after the ``matches`` keyword (except the space after the keyword) is the value to be used.

*********
Arguments
*********

.. list-table::
    :widths: 10 90
    :stub-columns: 1

    * - ``identifier``
      - Any valid identifier.
    * - ``value``
      - A regular expression.

********
Examples
********

- ``browser.title matches /homepage$/i``
- ``imported_page_model.elements.sign_in_button matches /^Sign/``