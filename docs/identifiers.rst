.. include:: includes/line-break.rst

===========
Identifiers
===========

An ``identifier`` uniquely identifies an element within a page. This may take the form of a:

- CSS selector
- XPath query
- page model element reference

------
Syntax
------

For CSS selectors or XPath queries:

``"{css-selector}"[:{position}]`` |br|
``"{xpath-query}"[:{position}]``

.. list-table::
    :widths: 10 90
    :stub-columns: 1

    * - ``css-selector``
      - Any valid CSS selector, may match more than one item.
    * - ``xpath-query``
      - Any valid XPath query, may match more than one item.
    * - ``position``
      - Optional, the position with a set of elements if the selector matches more than |br| one element.

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