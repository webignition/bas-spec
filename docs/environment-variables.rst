.. |br| raw:: html

   <br />

=====================
Environment Variables
=====================

Environment variables can be used in any place where a variable value can be used:

- as action arguments
- as assertion values
- within data providers and data collections

Use the ``env`` object to reference environment variables.

A default can be provided if the environment variable does not exist: ``env.APP_SECRET|"secret"``.

--------
Examples
--------

.. list-table::
    :stub-columns: 1

    * - ``env.APP_SECRET``
      - Use the ``APP_SECRET`` environment variable value.

    * - ``env.APP_SECRET|"secret"``
      - Use the ``APP_SECRET`` environment variable value with a default |br| of "secret!" if not set.
