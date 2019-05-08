=====================
Creating a Test Suite
=====================

A test suite brings a collection of tests together to represent a full user journey.
You might think it odd that we're diving straight into test suites before covering how to create tests.

Tests outside of the context of a test suite are somewhat abstract. Running head first into defining a test suite
is the way to go.

We're going to be creating a YAML_ file to define our test suite. In fact, all basil code is stored in YAML files.

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

.. _tutorial-test-suite-test-suite:


.. literalinclude:: includes/examples/test-suite/google-search-query-literal.yml

----------------------------
Understanding the Test Suite
----------------------------

Remember from the :doc:`terminology overview </tutorial-terminology>` that a test verifies one precise piece of functionality
and a test suite combines a series of tests to represent a full user journey.

Our test suite contains two tests, each having a name that we've chosen:

- ``open https://www.google.com``
- ``query 'example'``

The name can be whatever you chosen. There is no right answer, but it is good practice to name a test after what an end
user would be looking to achieve. Phrasing the name of a test as an action to be undertaken works well.

*****************************
Opening the Page to Be Tested
*****************************

The first test within a suite can be whatever you choose. In practice, opening the page at which we want to start, and
verifying that this has occurred, is generally a good idea.

.. literalinclude:: includes/examples/test-suite-partial/google-search-query-literal-open.yml

Here we define the name of the test (``open https://www.google.com``). This name is not part of the test itself, it is
here to give meaning to the test within the context of the test suite.

The test itself comprises the ``actions`` and ``assertions`` that follow the name:

.. literalinclude:: includes/examples/test/google-open-literal.yml

You can see that the ``actions`` section lists a single action. The next section in the tutorial covers the actions
you can perform. For now, it is enough to see that actions are the interactions with the browser that are needed to get
into an expected state.

The ``assertions`` section covers one or more factors that we need to examine to be sure that the browser is in the
state that we expect. In this case there are two assertions to verify the content of the address bar and the content
of the page ``<title>`` element.

*******************************
Querying For the Word "example"
*******************************

We want to enter the word "example" (without the quotes) into the Google search field and then to submit the search
form.

.. literalinclude:: includes/examples/test-suite-partial/google-search-query-literal-query.yml

The ``actions`` section lists the two steps needed: setting the input field to the required value and clicking the form
submission button.

The input field (``.gLFyf.gsfi``) and submit button (``.FPdoLc.VlcLAe input[name=btnK]``) are identified here
with CSS selectors. Page elements can also be identified with XPath and, more robustly, with page model element
reference. The tutorial on identifiers goes into more depth.

The ``assertions`` section lists one assertion to verify that the page ``<title>`` is as expected. We could also
verify that ``browser.url`` but in this case the page title suffices. The fewer assertions needed to verify the browser
state the faster your tests will complete.

.. _YAML: https://en.wikipedia.org/wiki/YAML/