.. code-block:: text

    {variable} {later-defined} "{variable-within-literal-quotes}" [{optional}] literal

    -------------------------------------------------------------------------------------------

    variable:
        <type>, the type for the variable value (<string>, <integer>, <url>).

    later-defined:
        A variable value to be defined later, most commonly if composed of multiple parts where
        each part requires its own definition or description.

    optional:
        <type>, optional values are encapsulated in [square brackets].


    Any characters within the definition not encapsulated in curly or square brackets are
    literal. Literal characters do not denote any special purpose and to be present as-is.

