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
The ``elements`` property is an optional collection mapping a convenience name to a :doc:`selector </selectors>`.

.. literalinclude:: includes/syntax/page-model.yml

-------
Example
-------

.. literalinclude:: includes/examples/page-model/google.com.yml
