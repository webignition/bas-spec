======================================
Creating and Using Parameterised Tests
======================================

We previously saw how a commonly-used test step can be :doc:`defined independently and imported into a test </tutorial-import-step>`
where needed.

In that instance, the commonly-used step verified that the page URL and page title were as expected.

.. literalinclude:: includes/examples/step/google-assert-open-literal.yml

Needing to verify that the correct page is open is a common starting point for many tests.

Instead of declaring page properties to verify within the test step itself, it would be nice to
leave those details aside for the time being and to provide the appropriate details when needed.

Let's do that.

-----------------------------
Defining Parameters in a Step
-----------------------------

.. literalinclude:: includes/examples/step/assert-page-open-parameterised.yml

We've replace literal values (``https://www.google.com`` and ``Google``) with data parameters
(``data.expected_url`` and ``data.expected_title``).

.. admonition:: Parameters Crash Course

    Parameters are prefixed with ``$``. The prefix denotes that something is a parameter and not a literal value.
    Data parameters (defined by you that expect values at some point) must be prefixed with ``data.``.
    The :doc:`parameters reference </parameters>` does into detail about the different parameter types.

The parameter names we choose are used within a test that imports our parameterised test step.
Pick something that makes sense outside of the context of the step.

We now have a general-purpose step for verifying that the correct page has been opened.

Given that pretty much every test must start with the opening of a page, this parameterised step can be re-used
in pretty much every test. Let's see how.

----------------------------------------
Importing and Using a Parameterised Test
----------------------------------------

.. literalinclude:: includes/examples/step/assert-page-open-parameterised.yml
.. literalinclude:: includes/examples/test/google-open-parameterised.yml

We provide an import name and import path just as when importing any other step.

The ``data`` property of the step is a list of data sets. Each data set is a YAML object with property names matching
the test parameter names and values as needed. In this case our there is just one data set.

------------------------------
Parameterising Querying Google
------------------------------

A great feature of a parameterised test is that it can be passed a list of many data sets and the test will run once
for each data set.

The act of opening https://www.google.com doesn't lend itself to being repeated many times with different sets of data.
But querying Google does!

.. literalinclude:: includes/examples/page/google.com-element-scoped-reference.yml
.. literalinclude:: includes/examples/step/assert-page-open-parameterised.yml
.. literalinclude:: includes/examples/step/google-query-parameterised.yml
.. literalinclude:: includes/examples/test/google-search-parameterised.yml

Our import of a the parameterised test step to verify the opened page is there as before.

We've also defined a parameterised test step to query Google and we've defined a data list with two data sets to pass to
the parameterised querying test. We've also parameterised the page elements within the querying test step.

What if we wanted to run the test to query Google with more than just two data sets? We could keep on adding data sets
within the test. And adding. And adding. Eventually we are going to run into a collection of data sets large enough that
it makes our test hard to follow.

The separation of that being tested from the data with which it is being tested is often useful. We'll solve that next
when we look at data providers.