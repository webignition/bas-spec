=====================
Creating a Page Model
=====================

We've been working on a test to open https:/www.google.com and to query for the word "example".
For the querying part, we need to identify the search input field and the button to submit the search form.

.. literalinclude:: includes/examples/test-partial/google-search-query-literal-query.yml

The test step works for now so that's fine, right?

Well, those selectors are a bit messy and that's not so fine. The selectors are hard to read (``.gLFyf.gsfi``
doesn't really shout "search input") and may well need to be updated in many places when the page being tested changes.

Let's create a page model to store all of these page properties. We can refer to the page model in our tests, making
the tests clearer to read. And we can make sure that if something needs updating it only needs to be changed in one place.

-------------------------------
Creating and Using a Page Model
-------------------------------

A page model is a YAML object with ``url`` and ``elements`` properties. The ``url`` property holds the page URL. The
``elements`` section maps convenience names to ways of identifying elements.

.. literalinclude:: includes/examples/page/google.com.yml

For the time being those selectors are a little hard on the eyes but at least we need to only update them in one place.

.. literalinclude:: includes/examples/step/google-assert-open-literal.yml
.. literalinclude:: includes/examples/test/google-import-assert-open-with-page-model.yml

We've added a ``pages`` section to the ``imports`` section to reference the page model we created. We've chosen an import
name (``google_com``) and provided an import path (``page/google.com.yml``).

Within our assertions, we use the name of the page import to reference the elements that the page model defines.

See how ``click $google_com.elements.search_button`` is a lot easier on the brain than ``click $".FPdoLc.VlcLAe input[name=btnK]"``?

------------------------------------
Scoping Elements Within a Page Model
------------------------------------

Both the search input field and the search button are within a form. And both elements have some properties other than
class names that are probably less prone to change.

We can make our page model more robust.

.. literalinclude:: includes/examples/page/google.com-selector-scoped.yml

That makes my brain hurt just a little bit less. But we're still repeating the ``form[action='/search']`` part of each
of the selectors.

Thankfully we can refer to any element that we have already named within any subsequent element identifier.

.. literalinclude:: includes/examples/page/google.com-element-scoped.yml

That is much easier to read.
