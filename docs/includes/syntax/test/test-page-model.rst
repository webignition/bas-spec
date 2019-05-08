.. code-block:: text

    imports:
      pages:
        {import-name-1}: {import-path-1}
        ...
        {import-name-N}: {import-path-N}

    actions:
      - {action-1}
      ...
      - {action-N}

    assertions:
      - {assertion-1}
      ...
      - {assertion-N}

    ------------------------------------

    action-*:
        <action>

    assertion-*:
        <assertion>

    import-name-*:
        <string>, must be unique within a test

    import-path-*:
        <string>, a path to the file to import, relative to the location of the test
