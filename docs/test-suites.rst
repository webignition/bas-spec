===========
Test Suites
===========

A test suite is composed of a series of :doc:`tests </tests>`. Tests may be defined directly within a suite or may be
defined independently and imported into a suite.

------
Syntax
------

A test suite is a YAML object with user-defined named properties where each property defines a test.
Each named property within the test suite defines the :doc:`actions </actions>` and :doc:`assertions </assertions>`
to be performed for a specific test.

.. code-block:: yaml

    {test-name}:
      actions:
        {actions}

      assertions:
        {assertions}

A test may be defined independently of the test suite and imported in one or more test suites.

Import names are user-defined. Import names for parameterised tests must not the ``actions`` or ``assertions`` keywords.
Import paths are relative to the test suite.

.. code-block:: yaml

    imports:
      tests:
        {import-name}: {import-path}

    {test-name}:
      - {import-name}


A test suite may both define and import tests.

.. code-block:: yaml

    imports:
      tests:
        {import-name}: {import-path}

    {first-test-name}:
      - {import-name}

    {second-test-name}:
      actions:
        {actions}

      assertions:
        {assertions}

Imported tests that require parameters must have the parameter values passed at usage time.

.. code-block:: yaml

    imports:
      tests:
        {import-name}: {import-path}

    {test-name}:
      {import-name}:
        {parameter-name}: {parameter-value}

Page models can be imported and their properties referenced within the test suite.

.. code-block:: yaml

    imports:
      pages:
        {import-name}: {import-path}

    {test-name}:
      actions:
        - open {import_name}

      assertions:
        - {import_name}.elements.{element_name} {comparison} {value}

--------
Examples
--------

***********************************
Tests Defined Within The test Suite
***********************************

.. code-block:: yaml

    "open https://www.google.com":
      actions:
        - open "https://www.google.com"

      assertions:
        - browser.title is "Google"

    "query 'example'":
      actions:
        - set ".gLFyf.gsfi" to "example"
        - click ".FPdoLc.VlcLAe input[name=btnK]"

      assertions:
        - browser.title is "example - Google Search"

*************************************************
Parameterised Tests Defined Within The test Suite
*************************************************

.. code-block:: yaml

    # test/open-url-parameterised.yml
    actions:
      - open {{ url }}

    assertions:
      - url is {{ url }}
      - {{ title_selector}} is {{ expected_title }}

.. code-block:: yaml

    # test-suite.yml
    imports:
      tests:
        open_url: test/open-url-parameterised.yml

    "open https://www.google.com":
      open_url:
        url: "https://www.google.com"
        expected_title: "Google"

*************************************************************
Tests Imported Into the Test Suite With Additional Assertions
*************************************************************

.. code-block:: yaml

    # test/google-search-open-url.yml
    actions:
      - open "https://www.google.com"

    assertions:
      - browser.title is "Google"

.. code-block:: yaml

    # test/google-search-query-example.yml
    actions:
      - set ".gLFyf.gsfi" to "example"
      - click ".FPdoLc.VlcLAe input[name=btnK]"

    assertions:
      - browser.title is "example - Google Search"

.. code-block:: yaml

    # test-suite.yml
    imports:
      tests:
        google_search_open_url: test/google-search-open-url.yml
        google_search_query_example: test/google-search-query-example.yml

    "open https://www.google.com":
      - google_search_open_url

      assertions:
        - browser.url is "https://google.com"

    "query 'example'":
      - google_search_query_example

***************************************
Page Model Imported Into the Test Suite
***************************************

.. code-block:: yaml

    # page/google.com.yml
    url: https://www.google.com
    elements:
      search_input: ".gLFyf.gsfi"
      search_button: ".FPdoLc.VlcLAe input[name=btnK]"

.. code-block:: yaml

    # test-suite.yml
    imports:
      pages:
        google_com: page/google.com.yml

    "open https://www.google.com":
      actions:
        - open google_com

      assertions:
        - browser.title is "Google"

    "query 'example'":
      actions:
        - set google_com.elements.search_input to "example"
        - click google_com.elements.search_button

      assertions:
        - browser.title is "example - Google Search"
