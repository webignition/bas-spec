==================
Browser Properties
==================

Properties for the browser can be accessed through the ``browser`` object and can be used directly in :doc:`assertions </assertions>`.

.. _browser-properties-url:

---
url
---

The current content of the browser address bar.

.. _browser-properties-title:

-----
title
-----

The page title (content of the ``<title>`` element).

-------
Example
-------

.. code-block:: yaml

    # test.yml
    actions:
     - open "https://www.google.com"

    assertions:
      - browser.url is https://www.google.com
      - browser.title is "Google"
