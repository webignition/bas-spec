.. code-block:: text

    {step-name-1}:
        {test}
    ...
    {step-name-N}
        {step}

    --------

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
