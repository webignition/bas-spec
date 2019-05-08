===============================
Importing Tests Into Your Suite
===============================

In the previous :doc:`tutorial on test suites </tutorial-test-suite>` we opened https://www.google.com/ and then we
performed a search.

The Google search form is shown on the homepage which is why we first visit the homepage before performing a search.

Searching is not the only action we can perform on the homepage. We could have plenty of tests that take the form:

- visit the homepage
- do *something*

By defining the *visit the homepage* test independently, we can use the test within any test suite without needing
to repeatedly redefine the *visit the homepage* test.

-----------------------------
Defining and Importing a Test
-----------------------------

.. literalinclude:: includes/examples/test/google-open-literal.yml

A test is a YAML object with ``actions`` and ``assertions`` properties. This is the same as the :ref:`first test from
the test suite tutorial <tutorial-test-suite-test-suite>` placed into its own file.

.. literalinclude:: includes/examples/test-suite/google-import-open.yml

Here we import and use the test within our test suite.

Imports are defined at the start of the test suite under the ``imports`` property within the ``tests`` property. We
will see later that you can import more than just tests.

A test import has an import name (``google_open``) and an import path (``test/google-open-literal.yml``).

The import name is something you yourself choose. It can be anything you like so long as it is unique within a given
test suite. We use the import name to refer to the test later within the test suite. An import name that is concise and
which makes sense later in the context of the test suite is a good idea.

The import path tells us where to look, relative to the current test suite, to find the test to be imported. Here
we defined the test in a file at ``test/google-open-literal.yml`` relative to our test suite.

----------------------------
Referencing an Imported Test
----------------------------

Compare our previous test suite defined the test within the suite to how we are now using the imported test.

**Previously**

.. literalinclude:: includes/examples/test-suite-partial/google-search-query-literal-open.yml

**Now**

.. literalinclude:: includes/examples/test-suite-partial/google-search-import-open.yml

--------------------------
Extending an Imported Test
--------------------------

An imported test can have additional assertions applied. As actions always come before assertions and as an imported
test will have performed actions, an imported test cannot have additional actions.

.. literalinclude:: includes/examples/test-suite/google-import-open-additional-assertions.yml

That's starting to look quite nice, except I feel that those identifiers (such as ``.gLFyf.gsfi``) are going to get messy
if we keep having to write them out in the middle of each test that needs them.

Next? Page models!