==============
Data Providers
==============

A data provider defines a data collection to be used with a parameterised :doc:`test </tests>`.

A data collection contains one or more data sets. Each data set provides values for the parameters
as required by a test.

------
Syntax
------

A test suite is a YAML object with user-defined named properties. Each property name is the name of a data set.
Each data set maps parameter names to parameter values.

.. code-block:: yaml

    {data-set-name-1}:
      {parameter-name-1}: {parameter-value-1}
      {parameter-name-2}: {parameter-value-2}
      # ...
      {parameter-name-N}: {parameter-value-N}

    {data-set-name-2}:
      {parameter-name-1}: {parameter-value-1}
      {parameter-name-2}: {parameter-value-2}
      # ...
      {parameter-name-N}: {parameter-value-N}

    # ...

    {data-set-name-N}:
      {parameter-name-1}: {parameter-value-1}
      {parameter-name-2}: {parameter-value-2}
      # ...
      {parameter-name-N}: {parameter-value-N}

--------
Examples
--------

*******************************************************************
Parameterised Tests With Data Supplied By An Imported Data Provider
*******************************************************************

.. code-block:: yaml

    # test/google-search-query-parameterised.yml
    actions:
      - set ".gLFyf.gsfi" to {{ search_term }}
      - click ".FPdoLc.VlcLAe input[name=btnK]"

    assertions:
      - browser.title is {{ expected_title }}

.. code-block:: yaml

    # data-provider/google-search-query.yml
    foo:
      search_term: foo
      expected_title: foo - Google Search

    bar:
      search_term: bar
      expected_title: bar - Google Search

.. code-block:: yaml

    # test-suite.yml
    imports:
      tests:
        query_test: test/open-url-parameterised.yml
      data_providers:
        google_search_query_data: data-provider/google-search-query.yml

    data:
      open_url_data:
        -
          url: "https://www.google.com"
          expected_title: "Google"

    "open https://www.google.com":
      actions:
        - open "https://www.google.com"

      assertions:
        - browser.title is "Google"

    "query":
      query_test:
        data: google_search_query_data
