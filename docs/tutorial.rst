=================
Tutorial Overview
=================

A learn-as-you-go guide on writing browser automation tests in basil.

.. admonition:: Topics

    - :doc:`Get To Know the Terminology </tutorial-terminology>`
    - :doc:`Creating a Test Suite To Define Your Tests </tutorial-test-suite>`
    - :doc:`Understanding Test Actions and Assertions </tutorial-actions-and-assertions>`
    - :doc:`Importing Tests Into Your Test Suite </tutorial-import-test>`
    - :doc:`Creating a Page Model to Define Properties of the Page Being Tested </tutorial-page-model>`
    - :doc:`Creating and Using Parameterised Tests </tutorial-parameterised-tests>`
    - Using a Data Provider To Supply Data Sets To Your Tests

We'll start out by :doc:`covering some terminology </tutorial-terminology>` so that we're all clear about
browser automation testing concepts.

You will then :doc:`create a test suite </tutorial-test-suite>` and will see how through a series of tests we can get
the browser into an expected state and then verify that the browser state is as expected.

We will show you how the :ref:`operations a user can perform <tutorial-actions>` within a browser are translated into a
sequence of actions within a test and how the :ref:`verification of browser state <tutorial-assertions>` is carried out
through a set of assertions.

You will learn how to :doc:`define commonly-repeated tests </tutorial-import-test>` outside of a test suite and how to
import a test into many test suites.

Repeated references to page elements will get sorted out when we see how :doc:`page models can define page properties </tutorial-page-model>`
and how to refer to these within your tests.

We will see how through the use of parameterised tests we can create tests with 'blanks' and replace those blanks later
with specific values.

We will finish by learning how to use data providers to separate what is being tested from the data with which it is
being tested.
