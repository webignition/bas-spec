.. code-block:: text

    imports:
        steps:
            {step-import-name}: "{import-path}"

    setup:
        browser: {browser}
        url: {url}

    {step-name}:
        use: {step-import-name}
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

    ---------------------------------------------------

    step-import-name:
        <string>

    import-path:
        <string>, a path to the file to import, relative to the location of the test

    browser:
        <string>

    url:
        <url>

    step-name:
        <string>

    data-set-name-*:
        <string>

    parameter-name-*:
        <string>, must match the name of a parameter as required by a step

    parameter-value-*:
        <string>
