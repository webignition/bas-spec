.. |br| raw:: html

   <br />

=====================
Environment Variables
=====================

Environment variable values can be accessed through the :ref:`environment variables object <parameters-environment-variables>`
and can be referenced :doc:`actions </actions>`, :doc:`assertions </assertions>` and :doc:`data providers </data-providers>`.

A default can be provided if the environment variable does not exist: ``$env.APP_SECRET|"secret"``.

--------
Examples
--------

.. list-table::
    :stub-columns: 1

    * - ``env.APP_SECRET``
      - Use the ``APP_SECRET`` environment variable value.

    * - ``env.APP_SECRET|"secret"``
      - Use the ``APP_SECRET`` environment variable value with a default |br| of "secret!" if not set.
