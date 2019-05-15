.. code-block:: text

    config:
        browser: {browser}
        url: {url}

    imports:
        steps:
            {step-import-name}: "{import-path}"
        data_providers:
            {data-provider-import-name}: "{import-path}"

    {step-name}:
        use: {step-import-name}
        data: {data-provider-import-name}

    ----------------------------------------------------

    step-import-name:
        <string>

    import-path:
        <string>, a path to the file to import, relative to the location of the test

    browser:
        <string>

    url:
        <url>

    data-provider-import-name:
        <string>

    step-name:
        <string>
