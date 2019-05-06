=======
Actions
=======

Actions are operations that can be performed to get the browser into the desired state.

------
Syntax
------

An action takes the form of a verb followed by zero or more arguments and keywords and zero or more keywords.

``{verb} [arguments] [keywords]``

-----
Verbs
-----

.. include:: includes/action-verb-list.rst

.. _actions-open:

----
Open
----

Visit a URL in the browser.

``open {url} [in {browser}]``

*********
Arguments
*********

.. list-table::
    :widths: 10 90
    :stub-columns: 1

    * - ``url``
      - The URL to visit. Double-quoting is required if the URL contains whitespace.
    * - ``browser``
      - The browser to use. One of: ``chrome``, ``firefox``. Optional, defaults to ``chrome``.

********
Examples
********

- ``open https://example.com``
- ``open "https://example.com"``
- ``open https://example.com in chrome``
- ``open "https://example.com" in firefox``
- ``open "https://example.com in chrome" in firefox``

.. _actions-click:

-----
Click
-----

Click on an element.

``click {identifier}``

*********
Arguments
*********

.. list-table::
    :widths: 10 90
    :stub-columns: 1

    * - ``identifier``
      - Any valid identifier.

********
Examples
********
- ``click ".sign-in-form .submit-button"``
- ``click ".listed-item":0``
- ``click imported_page_model.elements.element_name``

.. _actions-set:

---
Set
---

Set the value of an element. Most applicable to form field elements.

``set {identifier} to {value}``

Anything following the ``to`` keyword (except the space after the keyword) is the value to be used.

*********
Arguments
*********

.. list-table::
    :widths: 10 90
    :stub-columns: 1

    * - ``identifier``
      - Any valid identifier.
    * - ``value``
      - Any string.

********
Examples
********
- ``set "#sign-in-form .username" to user@example.com``
- ``set "#sign-in-form .username" to "user@example.com"`` (literal double quotes)
- ``set imported_page_model.elements.username to user@example.com``

.. _actions-submit:

------
Submit
------

Submits a form.

``submit {identifier}``

*********
Arguments
*********

.. list-table::
    :widths: 10 90
    :stub-columns: 1

    * - ``identifier``
      - Any valid identifier.

********
Examples
********
- ``submit "#sign-in-form"``
- ``submit imported_page_model.elements.submit_button``

.. _actions-wait:

----
Wait
----

Wait for a specified number of seconds.

``wait {number-of-seconds}``

*********
Arguments
*********

.. list-table::
    :widths: 10 90
    :stub-columns: 1

    * - ``number-of-seconds``
      - Any whole integer greater than ``0``.

********
Examples
********
- ``wait 1``
- ``wait 15``

.. _actions-wait-for:

--------
Wait-for
--------

Wait for an element to be rendered. Waits for up to 30 seconds.

``wait-for {identifier}``

*********
Arguments
*********

.. list-table::
    :widths: 10 90
    :stub-columns: 1

    * - ``identifier``
      - Any valid identifier.

********
Examples
********
- ``wait-for "#asychronously-loaded-content"``
- ``wait-for imported_page_model.elements.delayed_element_name``

.. _actions-reload:

------
Reload
------

Reload the current page.

``reload``

.. _actions-forward:

-------
Forward
-------

Move forward one item in the current session history.

``forward``

.. _actions-back:

----
Back
----

Move back one item in the current session history.

``back``
