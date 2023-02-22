.. include:: <isonum.txt>
.. include:: <isopub.txt>

Configuring happn and happner
=============================

Introduction
~~~~~~~~~~~~

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


Function matrix
~~~~~~~~~~~~~~~

The following matrix breaks down the functions related to each builder - please note the following:

- function parameters are omitted for brevity (see links to function details)
- table legend:
   - H: happn builder
   - HR: happner builder
   - HC: happn-cluster builder
   - HRC: happner-cluster builder

.. tabularcolumns:: |l{2cm}|l|c|c|c|c|c|

+------------------------------------------------------------+---------------+---+----+----+-----+
| function                                                   | usage         | H | HR | HC | HRC |
+============================================================+===============+===+====+====+=====+
| **withCacheStatisticsCheckPointAuthOverride**              | caching       | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withCacheStatisticsCheckPointAuthTokenOverride**         | caching       | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withCacheStatisticsInterval**                            | caching       | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withCacheStatisticsSecurityGroupPermissionsOverride**    | caching       | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withCacheStatisticsSecurityGroupsOverride**              | caching       | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withCacheStatisticsSecurityPasswordsOverride**           | caching       | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withCacheStatisticsSecurityUserPermissionsOverride**     | caching       | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withCacheStatisticsSecurityUsersOverride**               | caching       | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withConnectSecurityExclusion**                           |               | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withConnectSecurityForbiddenResponsePath**               |               | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withConnectSecurityUnauthorizedResponsePath**            |               | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withDataStore**                                          | data          | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withDataIsSecure**                                       | data          | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withProtocolAllowNestedPermissions**                     | protocols     | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withProtocolInboundLayer**                               | protocols     | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withProtocolIsSecure**                                   | protocols     | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withProtocolOutboundLayer**                              | protocols     | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withPublisherAcknowledgeTimeout**                        | pubsub        | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withPublisherTimeout**                                   | pubsub        | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withSecurityActivateSessionManagement**                  | security      | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withSecurityAccountLockoutEnabled**                      | security      | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withSecurityAccountLockoutAttempts**                     | security      | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withSecurityAccountLockoutRetryInterval**                | security      | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withSecurityAdminPassword**                              | security      | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withSecurityAdminPublicKey**                             | security      | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withSecurityAdminGroupCustomData**                       | security      | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withSecurityAdminGroupPermission**                       | security      | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withSecurityAllowAnonymousAccess**                       | security      | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withSecurityAuthProvider**                               | security      | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withSecurityCookie**                                     | security      | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withSecurityLogSessionActivity**                         | security      | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withSecurityLockTokenToLoginType**                       | security      | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withSecurityLockTokenToUserId**                          | security      | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withSecurityPbkdf2Iterations**                           | security      | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withSecurityProfile**                                    | security      | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withSessionActivityTTL**                                 | sessions      | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withSessionTokenSecret**                                 | sessions      | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withSubscriptionAllowNestedPermissions**                 | pubsub        | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withSubscriptionTreeSearchCacheSize**                    | pubsub        | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withSubscriptionTreePermutationCacheSize**               | pubsub        | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withSubscriptionTreeTimeout**                            | pubsub        | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withSubscriptionTreeFilterFunction**                     | pubsub        | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withSystemName**                                         |               | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withTransportCert**                                      | transport     | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withTransportCertPath**                                  | transport     | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withTransportKeepAliveTimout**                           | transport     | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withTransportKey**                                       | transport     | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withTransportKeyPath**                                   | transport     | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withTransportMode**                                      | transport     | x | x  | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withDeferListen**                                        |               |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withListenFirst**                                        |               |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **beginComponent**                                         | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |rtrif| withName                             | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |rtrif| withModuleName                       | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |rtrif| withSchemaExclusive                  | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |rtrif| withWebRoute                         | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |rtrif| withDataRoute                        | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |rtrif| withEvent                            | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |rtrif| beginFunction                        | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |nbsp| |nbsp| |rtri| *withName*              | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |nbsp| |nbsp| |rtri| *withModelType*         | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |nbsp| |nbsp| |rtri| *withAlias*             | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |nbsp| |nbsp| |rtri| *withParameter*         | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |nbsp| |nbsp| |rtri| *withCallbackParameter* | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |nbsp| |nbsp| |rtri| *endFunction*           | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |rtrif| endComponent                         | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **beginEndpoint**                                          | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |rtrif| withName                             | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |rtrif| withAllowSelfSignedCerts             | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |rtrif| withHost                             | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |rtrif| withPassword                         | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |rtrif| withPort                             | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |rtrif| withReconnect                        | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |rtrif| withUrl                              | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |rtrif| withUsername                         | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |rtrif| endEndpoint                          | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **beginModule**                                            | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |rtrif| withName                             | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |rtrif| withPath                             | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |rtrif| beginConstruct                       | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |nbsp| |nbsp| |rtri| *withName*              | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |nbsp| |nbsp| |rtri| *withParameter*         | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |nbsp| |nbsp| |rtri| *withCallbackParameter* | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |nbsp| |nbsp| |rtri| *endConstruct*          | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |rtrif| beginCreate                          | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |nbsp| |nbsp| |rtri| *withName*              | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |nbsp| |nbsp| |rtri| *withParameter*         | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |nbsp| |nbsp| |rtri| *withCallbackParameter* | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |nbsp| |nbsp| |rtri| *endCreate*             | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| |nbsp| |nbsp| |rtrif| endModule                            | rpc           |   | x  |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withHealthInterval**                                     | health monit. |   |    | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withHealthWarmupLimit**                                  | health monit. |   |    | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withOrchestratorMinimumPeers**                           | orchestration |   |    | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withOrchestratorReplicatePath**                          | orchestration |   |    | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withOrchestratorStableReportInterval**                   | orchestration |   |    | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withOrchestratorStabiliseTimeout**                       | orchestration |   |    | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withProxyAllowSelfSignedCerts**                          | proxy         |   |    | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withProxyCertPath**                                      | proxy         |   |    | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withProxyHost**                                          | proxy         |   |    | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withProxyKeyPath**                                       | proxy         |   |    | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withProxyTimeout**                                       | proxy         |   |    | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withReplicatorSecurityChangeSetReplicateInterval**       | replication   |   |    | x  | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withClusterRequestTimeout**                              |               |   |    |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withClusterResponseTimeout**                             |               |   |    |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
| **withDomain**                                             |               |   |    |    | x   |
+------------------------------------------------------------+---------------+---+----+----+-----+
