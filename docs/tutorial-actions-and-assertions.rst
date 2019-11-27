====================================
Understanding Actions and Assertions
====================================

The previous :doc:`tutorial on tests </tutorial-test>` showed how a test brings a collection of steps together to
examine a full user journey.

Here's the test we previously created for testing Google search:

.. literalinclude:: includes/examples/test/google-search-query-literal.yml

In this tutorial section, we'll look at how ``actions`` and ``assertions`` are formed and what we can do with them.

.. _tutorial-actions:

-------
Actions
-------

An action is something that an end user can do in a browser, such as click on link, enter text into a
field or submit a form. Each specific thing you can do within a browser when using a web page is an action.

We can click elements, set element values or submit elements, as well as take a few more types of action.

All actions take the form of a verb (click, set, submit) followed in many cases by the element on which to apply the
action and, possibly, some additional arguments (such as when setting an element value).

Each test starts with a set of actions to get the browser into an expected state.

***************
Action Examples
***************

.. include:: includes/examples/action-examples.rst

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
``$page.title is "Google"``.

If an assertion is found to be *incorrect* (if the page ``<title>`` is not the word "Google") your test will have failed.

******************
Assertion Examples
******************

.. include:: includes/examples/assertion-examples.rst

*************************
Assertion Comparison List
*************************

.. admonition:: Technical Reference: Assertion Comparisons

    .. include:: includes/assertion-comparison-list.rst
