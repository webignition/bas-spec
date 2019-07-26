.. |br| raw:: html

   <br />

=========
Selectors
=========

A ``selector`` uniquely identifies an element, or an attribute of an element, within a page with the use of a CSS
selector or XPath expression. A selector is one form of :doc:`identifier </identifiers>`.

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

    * - ``"#element-id".title``
      - CSS selector referencing the ``title`` attribute of the |br| matched element.

    * - ``"//*[@id='element-id']"``
      - XPath expression matching against the element ``id`` attribute.

    * - ``"//*[@id='element-id']".title``
      - XPath expression referencing the ``title`` attribute of |br| the matched element.

    * - ``".listed-item":1``
      - Finding the first matched item from the start of the list.

    * - ``".listed-item":1.title``
      - Finding the ``title`` attribute of the first matched item |br| from the start of the list.

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
