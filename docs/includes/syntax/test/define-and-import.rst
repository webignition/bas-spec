.. code-block:: text

    setup:
        browser: {browser}
        url: {url}

    imports:
        steps:
            {step-import-name}: "{import-path}"

    {step-name-1}:
        use: {step-import-name}
    ...
    {step-name-N}
        {step}

    -------------------------------------------

    browser:
        <string>

    url:
        <url>

    step-import-name:
        <string>

    import-path:
        <string>, a path to the file to import, relative to the location of the test

    step-name-*:
        <string>

    step:
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
