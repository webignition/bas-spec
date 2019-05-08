=======
Actions
=======

Actions are operations that can be performed to get the browser into the desired state.

------
Syntax
------

An action takes the form of a verb followed optionally an argument, a keyword and an additional argument.

The verb is always required. Whether arguments and keywords are optional is dependent on the verb.

.. include:: includes/syntax/action/action.rst

-----
Verbs
-----

.. include:: includes/action-verb-list.rst

.. _actions-open:

----
Open
----

Visit a URL in the browser.

.. include:: includes/syntax/action/open.rst

*********
Arguments
*********

.. rst-class:: typed
.. list-table::
    :widths: 10 10 80
    :stub-columns: 1

    * - ``url``
      - :doc:`<url> </types>`
      - The URL to visit, in double quotes.
    * - ``browser``
      - :doc:`<string> </types>`
      - The browser to use, in double quotes.

********
Examples
********

.. literalinclude:: includes/examples/actions/open.yml

.. _actions-click:

-----
Click
-----

Click on an element.

.. include:: includes/syntax/action/click.rst

*********
Arguments
*********

.. rst-class:: typed
.. list-table::
    :widths: 10 10 80
    :stub-columns: 1

    * - ``identifier``
      - :doc:`<identifier> </types>`
      - An :doc:`identifier </identifiers>`.

********
Examples
********

.. literalinclude:: includes/examples/actions/click.yml

.. _actions-set:

---
Set
---

Set the value of an element. Most applicable to form field elements.

.. include:: includes/syntax/action/set.rst

*********
Arguments
*********

.. rst-class:: typed
.. list-table::
    :widths: 10 10 80
    :stub-columns: 1

    * - ``identifier``
      - :doc:`<identifier> </types>`
      - An :doc:`identifier </identifiers>`.
    * - ``value``
      - :doc:`<string> </types>`
      - A string.

********
Examples
********

.. literalinclude:: includes/examples/actions/set.yml

.. _actions-submit:

------
Submit
------

Submits a form.

.. include:: includes/syntax/action/submit.rst

*********
Arguments
*********

.. rst-class:: typed
.. list-table::
    :widths: 10 10 80
    :stub-columns: 1

    * - ``identifier``
      - :doc:`<identifier> </types>`
      - An :doc:`identifier </identifiers>`.

********
Examples
********

.. literalinclude:: includes/examples/actions/submit.yml

.. _actions-wait:

----
Wait
----

Wait for a specified number of seconds.

.. include:: includes/syntax/action/wait.rst

*********
Arguments
*********

.. rst-class:: typed
.. list-table::
    :widths: 10 10 90
    :stub-columns: 1

    * - ``number-of-seconds``
      - :doc:`<positive-integer> </types>`
      - An integer greater than zero.

********
Examples
********

.. literalinclude:: includes/examples/actions/wait.yml

.. _actions-wait-for:

--------
Wait-for
--------

Wait for an element to be rendered. Waits for up to 30 seconds.

.. include:: includes/syntax/action/wait-for.rst

*********
Arguments
*********

.. rst-class:: typed
.. list-table::
    :widths: 10 10 90
    :stub-columns: 1

    * - ``identifier``
      - :doc:`<identifier> </types>`
      - An :doc:`identifier </identifiers>`.

********
Examples
********

.. literalinclude:: includes/examples/actions/wait-for.yml

.. _actions-reload:

------
Reload
------

Reload the current page.

.. include:: includes/syntax/action/reload.rst

.. _actions-forward:

-------
Forward
-------

Move forward one item in the current session history.

.. include:: includes/syntax/action/forward.rst

.. _actions-back:

----
Back
----

Move back one item in the current session history.

.. include:: includes/syntax/action/back.rst

------------
Example List
------------

.. include:: includes/examples/action-examples.rst
