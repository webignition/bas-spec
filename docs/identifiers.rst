.. include:: includes/line-break.rst

===========
Identifiers
===========

An ``identifier`` uniquely identifies an element within a page. This may take the form of a:

- a :doc:`selector </selectors>` (a CSS selector or XPath query)
- page model element reference

------
Syntax
------

For CSS selectors or XPath queries:

.. include:: includes/selectors-syntax.rst

For page model element references:

``{import-name}.elements.{element-name}``

.. list-table::
    :widths: 10 90
    :stub-columns: 1

    * - ``import-name``
      - The name chosen when importing a page model.
    * - ``element-name``
      - The element name as defined in the page model.

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

    * - ``google_com.elements.search_button``
      - Page model element reference.