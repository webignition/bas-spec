.. code-block:: text

    setup:
        browser: {browser}
        url: {url}

    imports:
        pages:
            {page-import-name}: "{import-path}"

    {step-name}:
      actions:
        - open {import_name}

      assertions:
        - {page-import-name}.elements.{element-name} {comparison} [{value}]

    -----------------------------------------------------------------------

    browser:
        <string>

    url:
        <url>

    page-import-name:
        <string>

    import-path:
        <string>, a path to the file to import, relative to the location of the test

    step-name:
        <string>

    element-name:
        <string>, defined within the imported page model

    comparison:
        <string>, comparison for assertion

    value:
        <string>, value for assertion

