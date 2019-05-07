==========
Page Model
==========

A page model holds properties of a web page, avoiding the need to repetitively define such properties at the point
that they are needed.

------
Syntax
------

A page model is a YAML document with ``url`` and ``elements`` properties.

The ``url`` property provides the URL for the web page.
The ``elements`` property is an optional collection mapping convenience names to :doc:`selectors </selectors>`.

Element selectors may optionally be prefixed with an element name that has already been defined within the same page
model. Doing so scopes the selector to the given element.

.. include:: includes/syntax/page-model.rst

--------
Examples
--------

.. literalinclude:: includes/examples/page-model/google.com.yml
.. literalinclude:: includes/examples/page-model/google.com-selector-scoped.yml
.. literalinclude:: includes/examples/page-model/google.com-element-scoped.yml
