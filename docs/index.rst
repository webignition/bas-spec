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
* ``tests`` and ``test suites`` to arrange collections of actions and assertions
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
    tutorial-test-suite
    tutorial-actions-and-assertions
    tutorial-import-test
    tutorial-page-model
    tutorial-parameterised-tests

.. toctree::
    :caption: Reference
    :maxdepth: 1

    actions
    assertions
    browser-properties
    identifiers
    selectors
    page-model
    tests
    test-suites
    data-providers
