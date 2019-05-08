.. code-block:: text

    {data-set-name-1}
        {parameter-name-1}: {parameter-value-1}
        ...
        {parameter-name-N}: {parameter-value-N}

    ...

    {data-set-name-N}
        {parameter-name-1}: {parameter-value-1}
        ...
        {parameter-name-N}: {parameter-value-N}

    -------------------------------------------

    data-set-name-*:
        <string>, must be unique with a data collection

    parameter-name-*:
        <string>, must match the name of a parameter as required by a test

    parameter-value-*:
        <string>
