===========================
Using Environment Variables
===========================

We've seen how to :doc:`pass data to parameterised tests </tutorial-parameterised-tests>` and we've seen how
:doc:`data providers can pass many sets of data </tutorial-data-providers>` to run a test many times.

Most of your test data will be benign, such as our test Google search terms of ``foo`` and ``bar``.

Some test data is intended to be kept a secret. Perhaps not a nobody-must-ever-know secret, but certainly something
that you don't want defined in the middle of a test or within a data provider.

Defining secrets within your basil code will mean that those secrets will eventually end up in your code repository.
Such secrets are irreversibly no longer secret.

A common good practice is to store secrets within environment variables. Let's see how you can use environment
variables within action arguments, assertion arguments and within data sets and data providers.

------------------------------------------
Creating a Test Requiring User Credentials
------------------------------------------

.. literalinclude:: includes/examples/test-suite/example-sign-in.yml

------------------------------------------
Defining and Using An Environment Variable
------------------------------------------

Let's pretend that some environment variables exist:

.. code-block:: bash

    export TEST_USER_USERNAME=user@example.com
    export TEST_USER_PASSWORD=password123

Referencing an environment variable is very similar to referencing a parameter in a test.

.. literalinclude:: includes/examples/test-suite/example-sign-in-with-environment-variables.yml

An environment variable is just a special-case parameter, so we wrap the parameter reference as usual in pairs of
curly braces ``{{ ... }}``.

Prefixing the environment variable name with `env:` marks the parameter as an environment variable
``{{ env::TEST_USER_EMAIL }}``.

---------------------------------------------------------------
Using Environment Variables Within Data Sets and Data Providers
---------------------------------------------------------------

What if we have a set of test users that we want to run through the sign in test?

Here are two examples, one with the data sets defined within the test and a one with the data sets defined within
a data provider.

.. literalinclude:: includes/examples/step/example-sign-in-as-user.yml
.. literalinclude:: includes/examples/data-provider/example-sign-in.yml
.. literalinclude:: includes/examples/test-suite/example-sign-in-with-data-provider.yml
