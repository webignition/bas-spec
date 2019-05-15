.. code-block:: text

    config:
        browser: {browser}
        url: {url}

    {step-name-1}:
        {step}
    ...
    {step-name-N}
        {step}

    ----------------------

    browser:
        <string>

    url:
        <url>

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
