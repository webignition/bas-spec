.. code-block:: text

    url: {url}
    elements:
        {element-name-1}: [${predefined-element-name}|{selector} >> ] {selector}
        ...
        {element-name-N}: [${predefined-element-name}|{selector} >> ] {selector}

    ----------------------------------------------------------------

    url:
        <url>

    element-name-*:
        <string>

    predefined-element-name:
        <string>, name of an element that has previously been defined

    selector:
        <selector>
