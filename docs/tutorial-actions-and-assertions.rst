=========================================
Understanding Test Actions and Assertions
=========================================

The previous :doc:`tutorial on test suites </tutorial-test-suite>` showed how a test suite brings a collection of tests
together to represent a full user journey

Here's the test suite we previously created for testing Google search:

.. literalinclude:: includes/examples/test-suite/google-search-query-literal.yml

In this tutorial, we'll look at how ``actions`` and ``assertions`` are formed and what we can do with them.

.. _tutorial-actions:

-------
Actions
-------

An action is something that an end user can do in a browser, such as visit a URL, click on link, enter text into a
field or submit a form. Each specific thing you can do within a browser when using a web page is an action.

We can click elements, set element values or submit elements, as well as take a few more types of action.

All actions take the form of a verb (click, set, submit) followed in many cases by the element on which to apply the
action and, possibly, some additional arguments (such as when setting an element value).

Each test starts with a set of actions to get the browser into an expected state.

***************
Action Examples
***************

.. literalinclude:: includes/examples/action-examples.yml

****************
Action Verb List
****************

.. admonition:: Technical Reference: Action Verbs

    .. include:: includes/action-verb-list.rst

.. _tutorial-assertions:

----------
Assertions
----------

Actions get the browser into an expected state. Assertions then verify that the state is as expected.

In plain English, we might say "Verify that the page title is "Google". A basil assertion for this reads as
``browser.title is Google``.

If an assertion is found to be correct (if the page ``<title>`` is indeed the word "Google") your test will have passed.
If not, your test will have failed.

******************
Assertion Examples
******************

.. literalinclude:: includes/examples/assertion-examples.yml

*************************
Assertion Comparison List
*************************

.. admonition:: Technical Reference: Assertion Comparisons

    .. include:: includes/assertion-comparison-list.rst
