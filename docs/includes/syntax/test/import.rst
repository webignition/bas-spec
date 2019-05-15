.. code-block:: text

    setup:
        browser: {browser}
        url: {url}

    imports:
        steps:
            {step-import-name}: "{import-path}"

    {step-name}:
        use: {step-import-name}

    -------------------------------------------

    browser:
        <string>

    url:
        <url>

    step-import-name:
        <string>

    import-path:
        <string>, a path to the file to import, relative to the location of the test

    step-name:
        <string>
