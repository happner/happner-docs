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
 - *example*: :code:`happnBuilder.withName('happn-instance')`
 - *build result*:

    .. code-block::

        {
            name: "happn-instance"
        }

.. _withHost:

withHost
--------

 - *definition*: :code:`withHost(host: string)`
 - *purpose*: sets the host for the happn instance
 - *example*: :code:`happnBuilder.withHost('192.168.1.1')`
 - *build result*:

    .. code-block::

        {
            host: "192.168.1.1"
        }

.. _withPort:

withPort
--------

 - *definition*: :code:`withPort(port: number)`
 - *purpose*: sets the port for the happn instance
 - *example*: :code:`happnBuilder.withPort(90)`
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
 - *example*: :code:`happnBuilder.withSecure(true)`
 - *build result*:

    .. code-block::

        {
            secure: true
        }

.. _withAllowNestedPermissions:

withAllowNestedPermissions
--------------------------

.. _withCacheStatisticsCheckPointAuthOverride:

withCacheStatisticsCheckPointAuthOverride
-----------------------------------------

 - *definition*: :code:`withCacheStatisticsCheckPointAuthOverride(max: number, maxAge: number)`
 - *purpose*: [TODO]
 - *example*: :code:`.withCacheStatisticsCheckPointAuthOverride(5, 1000)`
 - *build result*:

    .. code-block::

        {
            "services": {
                "cache": {
                    "config": {
                        "overrides": {
                            "checkpoint_cache_authorization": {
                                "max": 5,
                                "maxAge": 1000
                            }
                        }
                    }
                }
            }
        }


.. _withCacheStatisticsCheckPointAuthTokenOverride:

withCacheStatisticsCheckPointAuthTokenOverride
----------------------------------------------

.. _withCacheStatisticsInterval:

withCacheStatisticsInterval
---------------------------

.. _withCacheStatisticsSecurityGroupPermissionsOverride:

withCacheStatisticsSecurityGroupPermissionsOverride
---------------------------------------------------

.. _withCacheStatisticsSecurityGroupsOverride:

withCacheStatisticsSecurityGroupsOverride
-----------------------------------------

.. _withCacheStatisticsSecurityPasswordsOverride:

withCacheStatisticsSecurityPasswordsOverride
--------------------------------------------

.. _withCacheStatisticsSecurityUserPermissionsOverride:

withCacheStatisticsSecurityUserPermissionsOverride
--------------------------------------------------

.. _withCacheStatisticsSecurityUsersOverride:

withCacheStatisticsSecurityUsersOverride
----------------------------------------

.. _withConnectSecurityExclusion:

withConnectSecurityExclusion
----------------------------

.. _withConnectSecurityForbiddenResponsePath:

withConnectSecurityForbiddenResponsePath
----------------------------------------

.. _withConnectSecurityUnauthorizedResponsePath:

withConnectSecurityUnauthorizedResponsePath
-------------------------------------------

.. _withDataStore:

withDataStore
-------------

.. _withDataIsSecure:

withDataIsSecure
----------------

.. _withProtocolAllowNestedPermissions:

withProtocolAllowNestedPermissions
----------------------------------

.. _withProtocolInboundLayer:

withProtocolInboundLayer
------------------------

.. _withProtocolIsSecure:

withProtocolIsSecure
--------------------

.. _withProtocolOutboundLayer:

withProtocolOutboundLayer
-------------------------

.. _withPublisherAcknowledgeTimeout:

withPublisherAcknowledgeTimeout
-------------------------------

.. _withPublisherTimeout:

withPublisherTimeout
--------------------

.. _withSecurityActivateSessionManagement:

withSecurityActivateSessionManagement
-------------------------------------

.. _withSecurityAccountLockoutEnabled:

withSecurityAccountLockoutEnabled
---------------------------------

.. _withSecurityAccountLockoutAttempts:

withSecurityAccountLockoutAttempts
----------------------------------

.. _withSecurityAccountLockoutRetryInterval:

withSecurityAccountLockoutRetryInterval
---------------------------------------

.. _withSecurityAdminPassword:

withSecurityAdminPassword
--------------------------

.. _withSecurityAdminPublicKey:

withSecurityAdminPublicKey
--------------------------

.. _withSecurityAdminGroupCustomData:

withSecurityAdminGroupCustomData
--------------------------------

.. _withSecurityAdminGroupPermission:

withSecurityAdminGroupPermission
--------------------------------

.. _withSecurityAllowAnonymousAccess:

withSecurityAllowAnonymousAccess
--------------------------------

.. _withSecurityAuthProvider:

withSecurityAuthProvider
------------------------

.. _withSecurityCookie:

withSecurityCookie
------------------

.. _withSecurityLogSessionActivity:

withSecurityLogSessionActivity
------------------------------

.. _withSecurityLockTokenToLoginType:

withSecurityLockTokenToLoginType
--------------------------------

.. _withSecurityLockTokenToUserId:

withSecurityLockTokenToUserId
-----------------------------

.. _withSecurityPbkdf2Iterations:

withSecurityPbkdf2Iterations
----------------------------

.. _withSecurityProfile:

withSecurityProfile
-------------------

.. _withSessionActivityTTL:

withSessionActivityTTL
----------------------

.. _withSessionTokenSecret:

withSessionTokenSecret
----------------------

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

