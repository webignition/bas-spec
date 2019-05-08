.. |br| raw:: html

   <br />

=========
Selectors
=========

A ``selector`` uniquely identifies an element within a page with the use of a CSS selector or XPath.
A selector is one form of :doc:`identifier </identifiers>`.

------
Syntax
------

.. include:: includes/syntax/selector.rst

--------
Examples
--------

.. list-table::
    :stub-columns: 1

    * - ``"#element-id"``
      - CSS selector matching against the element ``id`` attribute.

    * - ``"//*[@id='element-id']"``
      - XPath query matching against the element ``id`` attribute.

    * - ``".listed-item":1``
      - Finding the first matched item from the start of the list.

    * - ``".listed-item":3``
      - Finding the third matched item from the start of the list.

    * - ``".listed-item":-1``
      - Finding the first matched item from the end of the list.

    * - ``".listed-item":-3``
      - Finding the third matched item from the end of the list.

    * - ``".listed-item":first``
      - Special position keyword ``first`` is equivalent to ``:1``.

    * - ``".listed-item":last``
      - Special position keyword ``last`` is equivalent to ``:-1``.
