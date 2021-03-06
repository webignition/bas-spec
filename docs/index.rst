.. Project Name documentation master file, created by
   sphinx-quickstart on Thu May  2 12:33:19 2019.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

============================
Basil Language Documentation
============================

Basil (**B**\ rowser **A**\ utomation **S**\ cript **I**\ ntermediary **L**\ anguage) is a programming language for
creating web browser automation tests.

Basil defines:

* ``actions`` to be performed to get a browser into a desired state
* ``assertions`` to verify the browser state
* ``steps``, ``tests`` and ``test suites`` to arrange collections of actions and assertions
* ``page models`` to de-couple tests from the pages being tested
* ``data providers`` to de-couple parameterised tests from the data driving them

Goals:

* concise when compared to equivalent WebDriver-powered code
* human-readable, understandable by non-developers
* transpilable to a target language for execution

.. toctree::
    :caption: Tutorial
    :maxdepth: 1

    tutorial
    tutorial-terminology
    tutorial-test
    tutorial-actions-and-assertions
    tutorial-import-step
    tutorial-page-model
    tutorial-parameterised-tests
    tutorial-data-providers
    tutorial-test-suite
    tutorial-environment-variables

.. toctree::
    :caption: Examples
    :maxdepth: 1

    examples
    examples-simple-test
    examples-simple-test-with-descendant-selectors
    examples-import-step
    examples-page-model
    examples-parameterised-test
    examples-test-suite
    examples-data-provider
    examples-environment-variables

.. toctree::
    :caption: Reference
    :maxdepth: 1

    types
    browser-properties
    page-properties
    environment-variables
    parameters

.. toctree::
    :caption: Syntax
    :maxdepth: 1

    syntax-notation
    actions
    assertions
    identifiers
    selectors
    descendant-selectors
    page-model
    steps
    tests
    test-suites
    data-providers
