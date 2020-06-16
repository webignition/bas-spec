.. |br| raw:: html

   <br />

====================
Descendant Selectors
====================

A ``descendant selector`` uniquely identifies an element (descendant) relative to another element (ancestor). The
targeted descendant need not be a direct descendant of the given ancestor.

A ``descendant selector`` may be used to target an element by means of an ancestor > descendant relationship which
is otherwise not possible or impractical using a single CSS- or XPath-based ``selector``.

------
Syntax
------

.. include:: includes/syntax/descendant-selector.rst

--------
Examples
--------

.. list-table::
    :stub-columns: 1

    * - ``$"#ancestor" >> $"#descendant"``
      - CSS selector descendant within the scope |br| of a CSS selector ancestor.

    * - ``$"//*[@id='ancestor']" >> $"//*[@id='descendant']"``
      - XPath expression descendant within the scope |br| of an XPath expression ancestor.

    * - ``$"#ancestor" >> $"//*[@id='descendant']"``
      - XPath expression descendant within the scope |br| of a CSS selector ancestor.

    * - ``$"//*[@id='ancestor']" >> $"#descendant"``
      - CSS selector descendant within the scope |br| of an XPath expression ancestor.

    * - ``$"#grandparent" >> $"#parent" >> $"#child"``
      - Targeting the child of a parent which itself |br| is the child of a grandparent.

    * - ``$".grandparent" >> $".parent":2 >> $".child":4``
      - Targeting the fourth child of the second child |br| of the grandparent.
