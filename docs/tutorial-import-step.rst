==============================
Importing Steps Into Your Test
==============================

In the previous :doc:`tutorial on tests </tutorial-test>` we opened https://www.google.com/ and then we performed a
search. The Google search form is shown on the homepage which is why we first verify that we're at the homepage before
performing a search.

Searching is not the only action we can perform on the homepage. We could have plenty of tests that take the form:

- verify that we're at the homepage
- do *something*

By defining the *verify that we're at the homepage* step independently, we can use the step within any test without
needing to repeatedly redefine the step.

-----------------------------
Defining and Importing a Step
-----------------------------

This is the same as the :ref:`first step from the test tutorial <tutorial-test-test>` placed into its own file.

.. literalinclude:: includes/examples/step/google-assert-open-literal.yml

Here we import and use the step within our test.

.. literalinclude:: includes/examples/test/google-import-assert-open.yml

Imports are defined in the ``imports`` section within the ``steps`` section. We will see later that you can import
more than just steps.

A step import has an import name (``google_open``) and an import path (``step/google-assert-open-literal.yml``).

The import name is something you choose. It can be anything you like. We use the import name to refer to the step
later within the test  An import name that is concise and which makes sense later in the context of the test is a good
idea.

The import path tells us where to look, relative to the test, to find the step to be imported. Here we defined the
step in a file at ``step/google-assert-open-literal.yml`` relative to our test.

----------------------------
Referencing an Imported Step
----------------------------

Compare our previous test that defined the step directly to how we are now using the imported step.

**Previously**

.. literalinclude:: includes/examples/test-partial/google-search-query-literal-open.yml

**Now**

.. literalinclude:: includes/examples/test-partial/google-search-import-open.yml

--------------------------
Extending an Imported Step
--------------------------

An imported step can have additional assertions applied. As actions always come before assertions and as an imported
step will have assertions defined, an imported step cannot have additional actions.

.. literalinclude:: includes/examples/test/google-import-assert-open-additional-assertions.yml

That's starting to look quite nice, except I feel that those identifiers (such as ``.gLFyf.gsfi``) are going to get messy
if we keep having to write them out in the middle of each test that needs them.

Next? Page models!