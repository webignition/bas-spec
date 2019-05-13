.. code-block:: text

    {test-name-1}:
        {test}
    ...
    {test-name-N}
        {test}

    --------

    test-name-*:
        <string>

    test:
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
