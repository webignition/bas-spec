=================
Using Test Suites
=================

We have so far created a test to open https://www.google.com and to search for given terms. We could keep adding
to this one test but doing so will eventually be impractical to maintain.

One test per user journey is more manageable and easier to maintain. This will lead to many tests covering a range of
pages, functionality and user journeys of varying critical importance.

A test suite brings together a collection of tests grouped in a manner that fits your needs. A given test can be
present in any number of test suites.

You might want to group tests by priority, examining first the most critical user journeys as grouped in one
suite and then examining afterwards some lower-priority functionality grouped in further test suites.

Let's see how this works by creating some more tests for Google.

-----------------------
Additional Google Tests
-----------------------

Google has a store where you can buy devices and accessories. The page at https://about.google presents an overview of
the company. Let's create some tests for those.

.. literalinclude:: includes/examples/test/google-store.yml
.. literalinclude:: includes/examples/test/about-google.yml

--------------------
Creating Test Suites
--------------------

A :doc:`test suite is a YAML list </test-suites>`. It doesn't get much easier than this. Create a YAML document for
your test suite and within define a list of imports.

The first test imported is the first to be run and so on.

.. literalinclude:: includes/examples/test-suite/google-high-priority.yml
.. literalinclude:: includes/examples/test-suite/google-low-priority.yml