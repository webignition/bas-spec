.. include:: includes/line-break.rst

=========
Selectors
=========

A ``selector`` uniquely identifies an element within a page with the use of a CSS selector or XPath query.
A ``selector`` is one form of :doc:`identifier </identifiers>`.

------
Syntax
------

.. include:: includes/selectors-syntax.rst

--------
Examples
--------

.. list-table::
    :widths: 40 60
    :stub-columns: 1

    * - ``"#element-id"``
      - CSS selector matching against the element ``id`` attribute.

    * - ``"//*[@id='element-id']"``
      - XPath query matching against the element ``id`` attribute.

    * - ``".listed-item":1``
      - CSS selector matching all elements with the ``listed-item`` |br| class name, fetching the first item in the list.

    * - ``".listed-item":3``
      - CSS selector matching all elements with the ``listed-item`` |br| class name, fetching the third item in the list.

    * - ``".listed-item":first``
      - Special position keyword ``first`` is equivalent to ``:1``.

    * - ``".listed-item":1``
      - Special position keyword ``last`` fetches the last matching item.
