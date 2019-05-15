===============
Creating a Test
===============

Through a series of steps, a test performs actions to get the browser into a required state and evaluates assertions
to verify that the state is as expected.

We will be creating a YAML_ file to define our test. In fact, all basil code is stored in YAML files.

.. admonition:: Note

    You will benefit from an editor (a text editor or IDE) that understands YAML (``.yml``) files. Your favourite
    editor probably already does so, but go and check if you're not sure. Whitespace is significant and tabs are bad.
    Use an editor that knows how to handle YAML.

---------------------
Testing Google Search
---------------------

Let's start somewhere nice and simple. We want to

- visit https://www.google.com/
- enter "example" into the search box
- submit the form
- examine the title of the resulting page to verify that this all worked correctly

Here's what that looks like in basil:

.. _tutorial-test-test:


.. literalinclude:: includes/examples/test/google-search-query-literal.yml

----------------------
Understanding the Test
----------------------

We then have two steps (``verify Google is open``
and ``query 'example'``) to handle carrying out actions and evaluating the browser state.

--------------------
Configuring the Test
--------------------

You can't test a web page without first opening a browser and visiting a URL. Every test starts with a ``config``
section declaring the ``browser`` to use and the ``url`` to start at.

.. literalinclude:: includes/examples/test-partial/google-search-query-literal-config.yml

----------
Test Steps
----------

Remember from the :doc:`terminology overview </tutorial-terminology>` that a step verifies one precise piece of functionality
and a test combines a series of steps to represent a full user journey.

Our test contains two steps, each having a name that we've chosen:

- ``verify Google is open``
- ``query 'example'``

The name can be whatever you chose. There is no right answer, but it is good practice to name a test after what an end
user would be looking to achieve. Phrasing the name of a step as an action to be undertaken works well.

-------------------------
Verifying the Opened Page
-------------------------

The first step within a test can be whatever you choose. In practice, verifying that the correct page has been opened
is generally a good idea.

.. literalinclude:: includes/examples/test-partial/google-search-query-literal-open.yml

Firstly we name the step (``verify Google is open``). This name is not part of the step itself, it is
here to give meaning to the step within the context of the test.

The step itself comprises the ``assertions`` that follow the name:

.. literalinclude:: includes/examples/step/google-assert-open-literal.yml

The ``assertions`` section covers the factors that we need to examine to be sure that the browser is in the
state that we expect. A test step must include assertions. If a test step is not checking that things are correct,
the test step isn't really doing any meaningful testing.

In this case there are two assertions: one to verify the page URL and one to verify the content
of the page ``<title>`` element.

.. admonition:: ?What

    The above assertions refer to ``$page.url`` and ``$page.title``. These are :ref:`built-in parameters <parameters-built-in>`
    referencing :doc:`page properties </page-properties>`.

-------------------------------
Querying For the Word "example"
-------------------------------

We want to enter the word "example" (without the quotes) into the Google search field and to submit the search form.

.. literalinclude:: includes/examples/test-partial/google-search-query-literal-query.yml

This step has an ``actions`` section. This lists the steps needed: setting the input field to the required value and
clicking the form submission button. Actions are optional but necessary if you want to interact with the browser in
any way.

The input field and submit button are identified here with CSS selectors. Page elements can also be identified with
XPath and, more robustly, with page model element references. The :doc:`tutorial on page models </tutorial-page-model>`
goes into more depth.

The ``assertions`` section lists one assertion to verify that the page ``<title>`` is as expected. We could also
verify that ``page.url`` is correct but in this case the page title suffices. The fewer assertions needed to verify
the browser state the faster your tests will complete.

.. _YAML: https://en.wikipedia.org/wiki/YAML/