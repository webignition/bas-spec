.. include:: includes/line-break.rst

===========
Identifiers
===========

An ``identifier`` uniquely identifies an element within a page. It is either a :doc:`selector </selectors>`, a page
model reference or a reference to an element passed to an imported step.

------
Syntax
------

.. include:: includes/syntax/identifier.rst

--------
Examples
--------

.. list-table::
    :widths: 40 60
    :stub-columns: 1

    * - ``"#element-id"``
      - CSS selector matching against the element ``id`` attribute.

    * - ``"//*[@id='element-id']"``
      - XPath expression matching against the element ``id`` attribute.

    * - ``".listed-item":1``
      - CSS selector matching all elements with the ``listed-item`` |br| class name, fetching the first item in the list.

    * - ``".listed-item":3``
      - CSS selector matching all elements with the ``listed-item`` |br| class name, fetching the third item in the list.

    * - ``".listed-item":first``
      - Special position keyword ``first`` is equivalent to ``:1``.

    * - ``".listed-item":1``
      - Special position keyword ``last`` fetches the last matching item.

    * - ``google_com.elements.search_button``
      - Page model element reference.

    * - ``$elements.element_name``
      - Passed element reference.
