======================================
Creating and Using Parameterised Tests
======================================

We previously saw how a commonly-used test can be :doc:`defined independently and imported into a test suite </tutorial-import-test>`
where needed.

In that instance, the commonly-used test opened https://www.google.com/ and verified that the page URL and page title
were as expected.

.. literalinclude:: includes/examples/test/google-open-literal.yml

Needing to open a page and to then verify that the correct page is open is a common starting point for many test suites.

Instead of defining the URL to visit and the page properties to verify within the test itself, it would be nice to leave
those details aside for the time being and to provide the appropriate details when needed.

Let's do that.

---------------------------
Adding Parameters to a Test
---------------------------

.. literalinclude:: includes/examples/test/open-url-parameterised.yml

We've replace absolute values (``https://www.google.com`` and ``Google``) with named parameters (``url`` and ``expected_title``).

You'll notice that the parameters within the test are written as ``{{ url }}`` and ``{{ expected_title }}``. Those brackets
before and after the parameter name let us know that we're dealing with a parameter.

Parameter names are user-defined. The names we choose are used within a test suite that imports our parameterised test.
Although parameter names can be whatever we like, picking something that makes sense outside of the context of the test
is good practice.

We now have a general-purpose test for opening a page and for verifying that the correct page has been opened.

Given that pretty much every test suite must start with the opening of a page, this parameterised test can be re-used
in pretty much every test suite.

Let's see how.

----------------------------------------
Importing and Using a Parameterised Test
----------------------------------------

.. literalinclude:: includes/examples/test/open-url-parameterised.yml
.. literalinclude:: includes/examples/test-suite/google-open-parameterised.yml

At the start of the test suite, under the ``imports`` and ``tests`` objects, we provide an import name and import path
just as when importing any other test.

The ``data`` property of the test is a data collection. A data collection defined directly within a test contains
a list of data sets. Each data set is a YAML object with property names matching the test parameter names and values as
needed.

In this case our data collection has just one data set. A parameterised test that is given a data collection holding
many data sets will be run once per data set.

Let's see how the data is passed to the parameterised test.

.. literalinclude:: includes/examples/test-suite-partial/google-open-parameterised-test.yml

------------------------------
Parameterising Querying Google
------------------------------

A great feature of a parameterised test is that it can be passed a data collection with many data sets and the test
will run once for each data set.

The act of opening https://www.google.com doesn't lend itself to being repeated many times with different sets of data.

But querying Google does!

.. literalinclude:: includes/examples/page-model/google.com-element-scoped.yml
.. literalinclude:: includes/examples/test/open-url-parameterised.yml
.. literalinclude:: includes/examples/test/google-search-query-parameterised-with-page-model.yml
.. literalinclude:: includes/examples/test-suite/google-search-parameterised.yml

Our import of a the parameterised test to open a page is there as before. We've now defined a parameterised test to
query Google and we've define a data collection with two data sets to pass to the parameterised querying test.

What if we wanted to run the test to query Google with more than just two data sets? We could keep on adding to the
data collection within the test suite. And adding. And adding. Eventually we are going to run into a data collection
large enough that it makes our test suite cumbersome and hard to follow.

The separation of that being tested from the data with which it is being tested is often useful. We'll solve that next
when we look at data providers.