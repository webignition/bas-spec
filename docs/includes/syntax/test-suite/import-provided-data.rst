.. code-block:: text

    imports:
        tests:
            {test-import-name}: {import-path}
        data_providers:
            {data-provider-import-name}: {import-path}

    {test-name}:
        use: {test-import-name}
        data: {data-provider-import-name}

    -----------------------------------------------

    test-import-name:
        <string>

    import-path:
        <string>, a path to the file to import, relative to the location of the suite

    data-provider-import-name:
        <string>

    test-name:
        <string>
