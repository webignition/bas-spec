.. code-block:: text

    imports:
        tests:
            {test-import-name}: {import-path}

    {test-name}:
        use: {test-import-name}
        data:
            {data-set-name-1}:
                {parameter-name-1}: {parameter-value-1}
                ...
                {parameter-name-N}: {parameter-value-N}
            ...
            {data-set-name-N}:
                {parameter-name-1}: {parameter-value-1}
                ...
                {parameter-name-N}: {parameter-value-N}

    -----------------------------------------------

    test-import-name:
        <string>

    import-path:
        <string>, a path to the file to import, relative to the location of the suite

    data-set-name-*:
        <string>

    parameter-name-*:
        <string>, must match the name of a parameter as required by a test

    parameter-value-*:
        <string>

    test-name:
        <string>
