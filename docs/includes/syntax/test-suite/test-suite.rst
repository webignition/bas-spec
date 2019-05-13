.. code-block:: text

    import:
        tests:
            {test-import-name-1}: {import-path-1}
            ...
            {test-import-name-N}: {import-path-N}

    {test-name-1}:
        use: {test-import-name-1}
    ...
    {test-name-N}:
        use: {test-import-name-N}

    ---------------------------------------------

    test-import-name-*:
        <string>

    import-path-*:
        <string>, a path to the file to import, relative to the location of the suite

    test-name-*:
        <string>
