
Introduction
============

**happn** and **happner** (as well as their cluster versions) utilise a comprehensive configuration system - when a server
instance is started, a configuration file is passed as a parameter to the relevant :code:`start` function.

This configuration file is a javascript object in the form of:

**happn and happn-cluster:**

.. code-block::

    // example
    {
        name: "happn-server",
        host: "192.168.1.10",
        port: 90,
        services: {}
    }

**happner and happner-cluster:**

.. code-block::

    // example
    {
        happn: {
            services: {},
            name: "happner-server",
            host: "192.168.1.10",
            port: 90
        },
        endpoints: {},
        modules: {},
        components: {},
    }

The above samples are extremely "bare-bones" - the configuration file can be very comprehensive and is required for setting
up **happn** *services*, **happner** *rpc components, modules and endpoints*, as well as clustering configuration.

Configuration helper library
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

In order to simplify the somewhat complex set of configuration options, the :code:`happn-configuration` library exports
a factory (:code:`ConfigBuilderFactory`) that produces a framework-specific configuration *builder* when required.

.. NOTE::

    :code:`happn-configuration` is a Typescript project, however this has been published to *npm* as a set of CommonJS modules (the
    published package contains Typescript definition files to allow for type safety and type-ahead if you are developing in
    Typescript).

The :code:`ConfigBuilderFactory` exposes the following functions:

- :code:`getHappnBuilder()`
- :code:`getHappnClusterBuilder()`
- :code:`getHappnerBuilder()`
- :code:`getHappnerClusterBuilder()`

Each builder exposes a set of *fluent* functions allowing "chaining" approach to building configuration files.

An example usage of a builder would be as follows:

.. code-block:: javascript

    // example to illustrate building a happn config file
    const { ConfigBuilderFactory } = require('happn-configuration');
    const builderFactory = ConfigBuilderFactory.create();
    const builder = builderFactory.getHappnBuilder();

    const config = builder.withName('test happn')
        .withHost('192.168.1.10')
        .withPort(90)
        .withSecure(true)
        .build();

    /* this produces:
    {
        name: "test happn",
        host: "192.168.1.10",
        port: 90,
        secure: true,
        services: {
            cache: {},
            connect: {},
            data: {},
            protocol: {},
            publisher: {},
            security: {},
            subscription: {},
            system: {},
            transport: {}
        }
    }
    */

A comprehensive list of builder functions can be found :ref:`here<builder-function-matrix>`.

.. autosummary::
   :toctree: generated


