==========
Assertions
==========

Assertions are used to verify that the browser is in the desired state.

------
Syntax
------

An assertion takes the form of an ``identifier`` followed by a ``comparison`` and an optional ``value``.

.. include:: includes/syntax/assertion/assertion.rst

-----------
Comparisons
-----------

.. include:: includes/assertion-comparison-list.rst

.. _comparisons-is:

--
Is
--

Checks if the value being compared equals a given value.

.. include:: includes/syntax/assertion/is.rst

*********
Arguments
*********

.. rst-class:: typed
.. list-table::
    :widths: 10 10 90
    :stub-columns: 1

    * - ``identifier``
      - :doc:`<identifier> </types>`
      - An :doc:`identifier </identifiers>`.
    * - ``value``
      - :doc:`<string> </types>`
      - A string, in double quotes.

********
Examples
********

.. literalinclude:: includes/examples/assertions/is.yml

.. _comparisons-is-not:

------
Is-not
------

Checks if the value being compared does not equal a given value.

.. include:: includes/syntax/assertion/is-not.rst

*********
Arguments
*********

.. rst-class:: typed
.. list-table::
    :widths: 10 10 90
    :stub-columns: 1

    * - ``identifier``
      - :doc:`<identifier> </types>`
      - An :doc:`identifier </identifiers>`.
    * - ``value``
      - :doc:`<string> </types>`
      - A string, in double quotes.

********
Examples
********

.. literalinclude:: includes/examples/assertions/is-not.yml

.. _comparisons-exists:

------
Exists
------

Checks if an element exists on the page.

.. include:: includes/syntax/assertion/exists.rst

*********
Arguments
*********

.. rst-class:: typed
.. list-table::
    :widths: 10 10 90
    :stub-columns: 1

    * - ``identifier``
      - :doc:`<identifier> </types>`
      - An :doc:`identifier </identifiers>`.

********
Examples
********

.. literalinclude:: includes/examples/assertions/exists.yml

.. _comparisons-not-exists:

----------
Not-Exists
----------

Checks if an element does not exist on the page.

.. include:: includes/syntax/assertion/not-exists.rst

*********
Arguments
*********

.. rst-class:: typed
.. list-table::
    :widths: 10 10 90
    :stub-columns: 1

    * - ``identifier``
      - :doc:`<identifier> </types>`
      - An :doc:`identifier </identifiers>`.

********
Examples
********

.. literalinclude:: includes/examples/assertions/not-exists.yml

.. _comparisons-includes:

--------
Includes
--------

Checks if the value being compared contains a given value.

.. include:: includes/syntax/assertion/includes.rst

Everything after the ``includes`` keyword (except the space after the keyword) is the value to be used.

*********
Arguments
*********

.. rst-class:: typed
.. list-table::
    :widths: 10 10 90
    :stub-columns: 1

    * - ``identifier``
      - :doc:`<identifier> </types>`
      - An :doc:`identifier </identifiers>`.
    * - ``value``
      - :doc:`<string> </types>`
      - A string, in double quotes.

********
Examples
********

.. literalinclude:: includes/examples/assertions/includes.yml

.. _comparisons-excludes:

--------
Excludes
--------

Checks if the value being compared does not contain a given value.

.. include:: includes/syntax/assertion/excludes.rst

Everything after the ``excludes`` keyword (except the space after the keyword) is the value to be used.

*********
Arguments
*********

.. rst-class:: typed
.. list-table::
    :widths: 10 10 90
    :stub-columns: 1

    * - ``identifier``
      - :doc:`<identifier> </types>`
      - An :doc:`identifier </identifiers>`.
    * - ``value``
      - :doc:`<string> </types>`
      - A string, in double quotes.

********
Examples
********

.. literalinclude:: includes/examples/assertions/excludes.yml

.. _comparisons-matches:

-------
Matches
-------

Checks if the value being compared matches a given regular expression.

.. include:: includes/syntax/assertion/matches.rst

The value to be used must be within double quotes. The double quotes are not part of the value.

*********
Arguments
*********

.. rst-class:: typed
.. list-table::
    :widths: 10 10 90
    :stub-columns: 1

    * - ``identifier``
      - :doc:`<identifier> </types>`
      - An :doc:`identifier </identifiers>`.
    * - ``regex``
      - :doc:`<regular-expression> </types>`
      - A regular expression.

********
Examples
********

.. literalinclude:: includes/examples/assertions/matches.yml

------------
Example List
------------

.. include:: includes/examples/assertion-examples.rst
