=================
Tutorial Overview
=================

A learn-as-you-go guide on writing browser automation tests in basil.

.. admonition:: Topics

    - :doc:`Get To Know the Terminology </tutorial-terminology>`
    - :doc:`Creating a Test to Define What to Do and What to Check </tutorial-test>`
    - :doc:`Understanding Actions and Assertions </tutorial-actions-and-assertions>`
    - :doc:`Importing Steps Into Your Test </tutorial-import-step>`
    - :doc:`Creating a Page Model to Define Properties of the Page Being Tested </tutorial-page-model>`
    - :doc:`Creating and Using Parameterised Tests </tutorial-parameterised-tests>`
    - :doc:`Using Test Suites to Group Tests </tutorial-test-suite>`
    - :doc:`Using a Data Provider to Supply Data Sets to Your Tests </tutorial-data-providers>`
    - :doc:`Using Environment Variables to Keep Secrets Secret </tutorial-environment-variables>`

We'll start out by :doc:`covering some terminology </tutorial-terminology>` so that we're all clear about
browser automation testing concepts.

You will then :doc:`create a test </tutorial-test>` and will see how through a series of test steps we can get
the browser into an expected state and then verify that the browser state is as expected.

We will show you how the :ref:`operations a user can perform <tutorial-actions>` within a browser are translated into a
sequence of actions within a test and how the :ref:`verification of browser state <tutorial-assertions>` is carried out
through a set of assertions.

You will learn how to :doc:`define commonly-repeated test steps </tutorial-import-step>` outside of a test and how to
import a step into many tests.

Repeated references to page elements will get sorted out when we see how :doc:`page models can define page properties </tutorial-page-model>`
and how to refer to these within your tests.

We will see how through the use of :doc:`parameterised tests </tutorial-parameterised-tests>` we can create tests with
'blanks' and replace those blanks later with specific values.

:doc:`Test suites </tutorial-test-suite>` will be used to group tests in whatever manner best fits your needs.

We will finish by learning how to :doc:`use data providers </tutorial-data-providers>` to separate what is being tested
from the data with which it is being tested and how to :doc:`use environment variables </tutorial-environment-variables>`
to keep secrets secret.
