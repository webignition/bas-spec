.. code-block:: text

    imports:
        steps:
            {step-import-name}: {import-path}

    {step-name}:
        use: {step-import-name}

    ------------------------------------

    step-import-name:
        <string>

    import-path:
        <string>, a path to the file to import, relative to the location of the test

    step-name:
        <string>
