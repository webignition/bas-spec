.. code-block:: text

    config:
        browsers:
            - {browser-1}
            ...
            - {browser-N}
        url: {url}

    imports:
        pages:
            {page-import-name}: "{import-path}"

    {step-name}:
      actions:
        - open {import_name}

      assertions:
        - {page-import-name}.elements.{element-name} {operator} [{value}]

    -----------------------------------------------------------------------

    page-import-name:
        <string>

    import-path:
        <string>, a path to the file to import, relative to the location of the test

    browser-*:
        <string>

    url:
        <url>

    step-name:
        <string>

    element-name:
        <string>, defined within the imported page model

    operator:
        <string>, operator for assertion

    value:
        <string>, value for assertion

