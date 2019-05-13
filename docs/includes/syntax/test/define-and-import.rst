.. code-block:: text

    imports:
        tests:
            {test-import-name}: {import-path}

    {test-name-1}:
        use: {test-import-name}
    ...
    {test-name-N}
        {test}

    ------------------------------------

    test-import-name:
        <string>, must be unique within a test

    import-path:
        <string>, a path to the file to import, relative to the location of the suite

    test-name-*:
        <string>

    test:
        actions:
          - {action-1}
          ...
          - {action-N}

        assertions:
          - {assertion-1}
          ...
          - {assertion-N}

    action-*:
        <action>

    assertion-*:
        <assertion>
