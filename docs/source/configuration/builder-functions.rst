.. include:: <isonum.txt>
.. include:: <isopub.txt>

Builder functions
=================

.. autosummary::
   :toctree: generated

.. _withName:

withName
--------

 - *definition*: :code:`withName(name: string)`
 - *purpose*: sets the name for the happn instance
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withName('happn-instance')`
 - *build result*:

    .. code-block::

        {
            name: happn-instance
        }

.. _withHost:

withHost
--------

 - *definition*: :code:`withHost(host: string)`
 - *purpose*: sets the host for the happn instance
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withHost('192.168.1.1')`
 - *build result*:

    .. code-block::

        {
            host: 192.168.1.1
        }

.. _withPort:

withPort
--------

 - *definition*: :code:`withPort(port: number)`
 - *purpose*: sets the port for the happn instance
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withPort(90)`
 - *build result*:

    .. code-block::

        {
            port: 90
        }

.. _withSecure:

withSecure
----------

 - *definition*: :code:`withSecure(secure: boolean)`
 - *purpose*: sets secure mode for happn instance
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withSecure(true)`
 - *build result*:

    .. code-block::

        {
            secure: true
        }

.. _withAllowNestedPermissions:

withAllowNestedPermissions
--------------------------

 - *definition*: :code:`withAllowNestedPermissions(allow: boolean)`
 - *purpose*: allows nested permissions
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withAllowNestedPermissions(true)`
 - *build result*:

    .. code-block::

        {
            withAllowNestedPermissions: true
        }


.. _withCacheCheckPointAuthOverride:

withCacheCheckPointAuthOverride
-------------------------------

 - *definition*: :code:`withCacheCheckPointAuthOverride(max: number, maxAge: number)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`.withCacheCheckPointAuthOverride(5, 1000)`
 - *build result*:

    .. code-block::

        {
            services: {
                cache: {
                    config: {
                        overrides: {
                            checkpoint_cache_authorization: {
                                max: 5,
                                maxAge: 1000
                            }
                        }
                    }
                }
            }
        }


.. _withCacheCheckPointAuthTokenOverride:

withCacheCheckPointAuthTokenOverride
------------------------------------

 - *definition*: :code:`withCacheCheckPointAuthTokenOverride(max: number, maxAge: number)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withCacheCheckPointAuthTokenOverride(5, 1000)`
 - *build result*:

    .. code-block::

        {
            services: {
                cache: {
                    config: {
                        overrides: {
                            checkpoint_cache_authorization_token: {
                                max: 5,
                                maxAge: 1000
                            }
                        }
                    }
                }
            }
        }

.. _withCacheStatisticsInterval:

withCacheStatisticsInterval
---------------------------

 - *definition*: :code:`withCacheStatisticsInterval(interval: number)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withCacheStatisticsInterval(5000)`
 - *build result*:

    .. code-block::

        {
            services: {
                cache: {
                    config: {
                            statisticsInterval: 5000
                        }
                    }
                }
            }
        }

.. _withCacheSecurityGroupPermissionsOverride:

withCacheSecurityGroupPermissionsOverride
-----------------------------------------

 - *definition*: :code:`withCacheSecurityGroupPermissionsOverride(max: number, maxAge: number)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withCacheSecurityGroupPermissionsOverride(5, 1000)`
 - *build result*:

    .. code-block::

        {
            services: {
                cache: {
                    config: {
                        overrides: {
                            cache_security_group_permissions: {
                                max: 5,
                                maxAge: 1000
                            }
                        }
                    }
                }
            }
        }


.. _withCacheSecurityGroupsOverride:

withCacheSecurityGroupsOverride
-------------------------------

 - *definition*: :code:`withCacheSecurityGroupsOverride(max: number, maxAge: number)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withCacheSecurityGroupsOverride(5, 1000)`
 - *build result*:

    .. code-block::

        {
            services: {
                cache: {
                    config: {
                        overrides: {
                            cache_security_groups: {
                                max: 5,
                                maxAge: 1000
                            }
                        }
                    }
                }
            }
        }

.. _withCacheSecurityPasswordsOverride:

withCacheSecurityPasswordsOverride
----------------------------------

 - *definition*: :code:`withCacheSecurityPasswordsOverride(max: number, maxAge: number)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withCacheSecurityPasswordsOverride(5, 1000)`
 - *build result*:

    .. code-block::

        {
            services: {
                cache: {
                    config: {
                        overrides: {
                            cache_security_passwords: {
                                max: 5,
                                maxAge: 1000
                            }
                        }
                    }
                }
            }
        }

.. _withCacheSecurityUserPermissionsOverride:

withCacheSecurityUserPermissionsOverride
----------------------------------------

 - *definition*: :code:`withCacheSecurityPasswordsOverride(max: number, maxAge: number)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withCacheSecurityPasswordsOverride(5, 1000)`
 - *build result*:

    .. code-block::

        {
            services: {
                cache: {
                    config: {
                        overrides: {
                            cache_security_passwords: {
                                max: 5,
                                maxAge: 1000
                            }
                        }
                    }
                }
            }
        }

.. _withCacheSecurityUsersOverride:

withCacheSecurityUsersOverride
------------------------------

 - *definition*: :code:`withCacheSecurityUsersOverride(max: number, maxAge: number)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withCacheSecurityUsersOverride(5, 1000)`
 - *build result*:

    .. code-block::

        {
            services: {
                cache: {
                    config: {
                        overrides: {
                            cache_security_users: {
                                max: 5,
                                maxAge: 1000
                            }
                        }
                    }
                }
            }
        }


.. _withConnectSecurityExclusion:

withConnectSecurityExclusion
----------------------------

 - *definition*: :code:`withConnectSecurityExclusion(exclusion: string)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withConnectSecurityExclusion('test/exclusion/path')`
 - *build result*:

    .. code-block::

        {
            services: {
                connect: {
                    config: {
                        middleware: {
                            security: {
                                exclusions: [
                                    /test/exclusion/path
                                ],
                            }
                        }
                      }
                    }
                  },
            }
        }


.. _withConnectSecurityForbiddenResponsePath:

withConnectSecurityForbiddenResponsePath
----------------------------------------

 - *definition*: :code:`withConnectSecurityForbiddenResponsePath(path: string)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withConnectSecurityForbiddenResponsePath('forbidden/response/path')`
 - *build result*:

    .. code-block::

        {
            services: {
                connect: {
                    config: {
                        middleware: {
                            security: {
                                 forbiddenResponsePath: forbidden/response/path,
                            }
                        }
                      }
                    }
                  },
            }
        }

.. _withConnectSecurityUnauthorizedResponsePath:

withConnectSecurityUnauthorizedResponsePath
-------------------------------------------

 - *definition*: :code:`withConnectSecurityUnauthorizedResponsePath(path: string)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withConnectSecurityUnauthorizedResponsePath('unauthorized/response/path')`
 - *build result*:

    .. code-block::

        {
            services: {
                connect: {
                    config: {
                        middleware: {
                            security: {
                                 unauthorizedResponsePath: unauthorized/response/path
                            }
                        }
                      }
                    }
                  },
            }
        }

.. _withDataStore:

withDataStore
-------------

 - *definition*: :code:`withDataStore(name: string, provider: string, isDefault: boolean, isFsync: boolean, dbFile: string, fileName: string)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withDataStore('testDataStore', 'testProvider', true, true, 'dfile.db', 'myDataFile')`
 - *build result*:

    .. code-block::

        {
            services: {
                data: {
                    config: {
                        datastores: [
                            {
                                name: testDataStore,
                                provider: testProvider,
                                isDefault: true,
                                settings: {
                                    fsync: true,
                                    filename: myDataFile
                                },
                                dbfile: dfile.db
                            }
                        ]
                    }
                },
            }
        }

.. _withDataIsSecure:

withDataIsSecure
----------------

 - *definition*: :code:`withDataIsSecure(secure: boolean)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withDataIsSecure(true)`
 - *build result*:

    .. code-block::

        {
            services: {
                data: {
                    config: {
                        secure: true,
                    }
                },
            }
        }

.. _withProtocolAllowNestedPermissions:

withProtocolAllowNestedPermissions
----------------------------------

 - *definition*: :code:`withProtocolAllowNestedPermissions(allow: boolean)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withProtocolAllowNestedPermissions(true)`
 - *build result*:

    .. code-block::

        {
            services: {
                protocol: {
                    config: {
                        allowNestedPermissions: true,
                    }
                }
            }
        }

.. _withProtocolInboundLayer:

withProtocolInboundLayer
------------------------

 - *definition*: :code:`withProtocolInboundLayer(func: function)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withProtocolInboundLayer((msg, cb) => { cb(null, 'inbound-result'); })`
 - *build result*:

    .. code-block::

        {
            services: {
                protocol: {
                    config: {
                        inboundLayers: [
                            (msg, cb) => {
                                cb(null, 'inbound-result');
                            }
                        ]
                    }
                }
            }
        }

.. _withProtocolIsSecure:

withProtocolIsSecure
--------------------

 - *definition*: :code:`withProtocolIsSecure(isSecure: boolean)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withProtocolIsSecure(true)`
 - *build result*:

    .. code-block::

        {
            services: {
                protocol: {
                    config: {
                        secure: true,
                    }
                }
            }
        }

.. _withProtocolOutboundLayer:

withProtocolOutboundLayer
-------------------------

 - *definition*: :code:`withProtocolOutboundLayer(func: function)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withProtocolOutboundLayer((msg, cb) => { cb(null, 'outbound-result'); })`
 - *build result*:

    .. code-block::

        {
            services: {
                protocol: {
                    config: {
                        outboundLayers: [
                            (msg, cb) => {
                                cb(null, 'outbound-result');
                            }
                        ]
                    }
                }
            }
        }

.. _withPublisherAcknowledgeTimeout:

withPublisherAcknowledgeTimeout
-------------------------------

 - *definition*: :code:`withPublisherAcknowledgeTimeout(timeout: number)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withPublisherAcknowledgeTimeout(2000)`
 - *build result*:

    .. code-block::

        {
            services: {
                publisher: {
                    config: {
                        publicationOptions: {
                            acknowledgeTimeout: 2000
                        }
                    }
                }
            }
        }

.. _withPublisherTimeout:

withPublisherTimeout
--------------------

 - *definition*: :code:`withPublisherTimeout(timeout: number)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withPublisherTimeout(2000)`
 - *build result*:

    .. code-block::

        {
            services: {
                publisher: {
                    config: {
                        timeout: 2000
                    }
                }
            }
        }

.. _withSecurityActivateSessionManagement:

withSecurityActivateSessionManagement
-------------------------------------

 - *definition*: :code:`withSecurityActivateSessionManagement(activate: boolean)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withSecurityActivateSessionManagement(true)`
 - *build result*:

    .. code-block::

        {
            services: {
                security: {
                    config: {
                        activateSessionManagement: true
                    }
                }
            }
        }

.. _withSecurityAccountLockoutEnabled:

withSecurityAccountLockoutEnabled
---------------------------------

 - *definition*: :code:`withSecurityAccountLockoutEnabled(enabled: boolean)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withSecurityAccountLockoutEnabled(true)`
 - *build result*:

    .. code-block::

        {
            services: {
                security: {
                    config: {
                        accountLockout: {
                            enabled: true
                        }
                    }
                }
            }
        }

.. _withSecurityAccountLockoutAttempts:

withSecurityAccountLockoutAttempts
----------------------------------

 - *definition*: :code:`withSecurityAccountLockoutAttempts(attempts: number)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withSecurityAccountLockoutAttempts(5)`
 - *build result*:

    .. code-block::

        {
            services: {
                security: {
                    config: {
                        accountLockout: {
                            attempts: 5
                        }
                    }
                }
            }
        }

.. _withSecurityAccountLockoutRetryInterval:

withSecurityAccountLockoutRetryInterval
---------------------------------------

 - *definition*: :code:`withSecurityAccountLockoutRetryInterval(interval: number)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withSecurityAccountLockoutRetryInterval(1000)`
 - *build result*:

    .. code-block::

        {
            services: {
                security: {
                    config: {
                        accountLockout: {
                            retryInterval: 1000
                        }
                    }
                }
            }
        }

.. _withSecurityAdminPassword:

withSecurityAdminPassword
--------------------------

 - *definition*: :code:`withSecurityAdminPassword(password: string)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withSecurityAdminPassword('adminPassword')`
 - *build result*:

    .. code-block::

        {
            services: {
                security: {
                    config: {
                        adminUser: {
                            password: 'adminPassword'
                        }
                    }
                }
            }
        }

.. _withSecurityAdminPublicKey:

withSecurityAdminPublicKey
--------------------------

 - *definition*: :code:`withSecurityAdminPublicKey(key: string)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withSecurityAdminPublicKey('snbouqudb1o23')`
 - *build result*:

    .. code-block::

        {
            services: {
                security: {
                    config: {
                        adminUser: {
                            publicKey: 'snbouqudb1o23'
                        }
                    }
                }
            }
        }

.. _withSecurityAdminGroupCustomData:

withSecurityAdminGroupCustomData
--------------------------------

 - *definition*: :code:`withSecurityAdminGroupCustomData(fieldName: string, fieldValue: string)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withSecurityAdminGroupCustomData('customField', 'customValue')`
 - *build result*:

    .. code-block::

        {
            services: {
                security: {
                    config: {
                        adminGroup: {
                            custom_data: {
                                customField: 'customValue'
                            }
                        }
                    }
                }
            }
        }

.. _withSecurityAdminGroupPermission:

withSecurityAdminGroupPermission
--------------------------------

 - *definition*: :code:`withSecurityAdminGroupPermission(permissionKey: string, actionPath: string)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withSecurityAdminGroupPermission('testKey', 'testAction')`
 - *build result*:

    .. code-block::

        {
            services: {
                security: {
                    config: {
                        adminGroup: {
                            permissions: {
                                testKey: {
                                    actions: [
                                        'testAction'
                                    ]
                                }
                            }
                        }
                    }
                }
            }
        }

.. _withSecurityAllowAnonymousAccess:

withSecurityAllowAnonymousAccess
--------------------------------

 - *definition*: :code:`withSecurityAllowAnonymousAccess(allow: boolean)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withSecurityAllowAnonymousAccess(true)`
 - *build result*:

    .. code-block::

        {
            services: {
                security: {
                    config: {
                        allowAnonymousAccess: true
                    }
                }
            }
        }

.. _withSecurityAuthProvider:

withSecurityAuthProvider
------------------------

 - *definition*: :code:`withSecurityAuthProvider(name: string, instance: any)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withSecurityAuthProvider('testProvider', new (class TestClass {})())`
 - *build result*:

    .. code-block::

        {
            services: {
                security: {
                    config: {
                        authProviders: {
                            testProvider: {}    // TestClass instance
                        }
                    }
                }
            }
        }

.. _withSecurityCookie:

withSecurityCookie
------------------

 - *definition*: :code:`withSecurityCookie(name: string, domain: string)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withSecurityCookie('testCookie', 'test.com')`
 - *build result*:

    .. code-block::

        {
            services: {
                security: {
                    config: {
                        cookieName: 'testCookie',
                        cookieDomain: 'test.com',
                        httpsCookie: true,
                    }
                }
            }
        }

.. _withSecurityLogSessionActivity:

withSecurityLogSessionActivity
------------------------------

 - *definition*: :code:`withSecurityLogSessionActivity(shouldLog: boolean)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withSecurityLogSessionActivity(true)`
 - *build result*:

    .. code-block::

        {
            services: {
                security: {
                    config: {
                        logSessionActivity: true
                    }
                }
            }
        }

.. _withSecurityLockTokenToLoginType:

withSecurityLockTokenToLoginType
--------------------------------

 - *definition*: :code:`withSecurityLockTokenToLoginType(shouldLock: boolean)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withSecurityLockTokenToLoginType(true)`
 - *build result*:

    .. code-block::

        {
            services: {
                security: {
                    config: {
                        lockTokenToLoginType: true
                    }
                }
            }
        }

.. _withSecurityLockTokenToUserId:

withSecurityLockTokenToUserId
-----------------------------

 - *definition*: :code:`withSecurityLockTokenToUserId(shouldLock: boolean)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withSecurityLockTokenToUserId(true)`
 - *build result*:

    .. code-block::

        {
            services: {
                security: {
                    config: {
                        lockTokenToUserId: true
                    }
                }
            }
        }

.. _withSecurityPbkdf2Iterations:

withSecurityPbkdf2Iterations
----------------------------

 - *definition*: :code:`withSecurityPbkdf2Iterations(iterations: number)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withSecurityPbkdf2Iterations(5)`
 - *build result*:

    .. code-block::

        {
            services: {
                security: {
                    config: {
                        pbkdf2Iterations: 5
                    }
                }
            }
        }

.. _withSecurityProfile:

withSecurityProfile
-------------------

 - *definition*: :code:`withSecurityProfile(name: string, sessionKey: string, sessionMatchOn: any, policyTTL: number, policyInactiveThreshold: number)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withSecurityProfile('testProfile', 'testKey', 1, 50000, 10000)`
 - *build result*:

    .. code-block::

        {
            services: {
                security: {
                    config: {
                        profiles: [
                            {
                                name: 'testProfile',
                                policy: {
                                    ttl: 50000,
                                    inactivity_threshold: 10000
                                },
                                session: {
                                    testKey: {
                                        $eq: 1
                                    }
                                }
                            }
                        ]
                    }
                }
            }
        }

.. _withSessionActivityTTL:

withSessionActivityTTL
----------------------

 - *definition*: :code:`withSessionActivityTTL(ttl: number)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withSessionActivityTTL(5000)`
 - *build result*:

    .. code-block::

        {
            services: {
                security: {
                    config: {
                        sessionActivityTTL: 5000
                    }
                }
            }
        }

.. _withSessionTokenSecret:

withSessionTokenSecret
----------------------

 - *definition*: :code:`withSessionTokenSecret(secret: string)`
 - *purpose*: [TODO]
 - *applies to*: **happn**, **happn-cluster**, **happner**, **happner-cluster**
 - *example*: :code:`builder.withSessionTokenSecret('superSecretPassword')`
 - *build result*:

    .. code-block::

        {
            services: {
                security: {
                    config: {
                        sessionTokenSecret: 'superSecretPassword'
                    }
                }
            }
        }

.. _withSubscriptionAllowNestedPermissions:

withSubscriptionAllowNestedPermissions
--------------------------------------

.. _withSubscriptionTreeSearchCacheSize:

withSubscriptionTreeSearchCacheSize
-----------------------------------

.. _withSubscriptionTreePermutationCacheSize:

withSubscriptionTreePermutationCacheSize
----------------------------------------

.. _withSubscriptionTreeTimeout:

withSubscriptionTreeTimeout
---------------------------

.. _withSubscriptionTreeFilterFunction:

withSubscriptionTreeFilterFunction
----------------------------------

.. _withSystemName:

withSystemName
--------------

.. _withTransportCert:

withTransportCert
-----------------

.. _withTransportCertPath:

withTransportCertPath
---------------------

.. _withTransportKeepAliveTimeout:

withTransportKeepAliveTimeout
-----------------------------

.. _withTransportKey:

withTransportKey
----------------

.. _withTransportKeyPath:

withTransportKeyPath
--------------------

.. _withTransportMode:

withTransportMode
-----------------

.. _withDeferListen:

withDeferListen
---------------

.. _withListenFirst:

withListenFirst
---------------

.. _beginComponent:

beginComponent
--------------

.. _withName2:

|rtrif| withName
~~~~~~~~~~~~~~~~

.. _withModuleName:

|rtrif| withModuleName
~~~~~~~~~~~~~~~~~~~~~~

.. _withSchemaExclusive:

|rtrif| withSchemaExclusive
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. _withWebRoute:

|rtrif| withWebRoute
~~~~~~~~~~~~~~~~~~~~

.. _withDataRoute:

|rtrif| withDataRoute
~~~~~~~~~~~~~~~~~~~~~

.. _withEvent:

|rtrif| withEvent
~~~~~~~~~~~~~~~~~

.. _beginFunction:

|rtrif| beginFunction
~~~~~~~~~~~~~~~~~~~~~

.. _withName3:

|rtri| withName

.. _withModelType:

|rtri| withModelType

.. _withAlias:

|rtri| withAlias

.. _withParameter:

|rtri| withParameter

.. _withCallbackParameter:

|rtri| withCallbackParameter

.. _endFunction:

|rtri| endFunction

.. _endComponent:

|rtri| endComponent

