..  _data-providers:

Data providers
==============

Happn provides a set of out-of-the-box data providers, which can be activated through configuration:

* In-memory_
* Loki_
* Nedb_
* Mongo_
* Sqlite
* Elasticsearch

.. admonition:: Unified interface for data operations

    Happn contains a unified interface for data operations (see :ref:`querying-data`), ie: no matter which provider you use, the data querying operations are the same.

In-memory
---------

The in-memory data store uses **Loki** by default. A typical configuration would be:

.. code-block:: javascript

    {
      ...
      services: {
        data: {
          config: {
            secure: true,
            datastores: [{
              name: "temperatures",
              provider: "memory",
              isDefault: true
            }]
          }
        }
      }
      ...
    }

See Loki_ for further information.

Loki
----
Loki is a product produced by Grafana: `<https://grafana.com/oss/loki>`_, and would need to be installed on the host system.

.. admonition:: Loki backing store

    In terms of data storage, Loki itself allows for data persistence in a number of different technologies (Cassandra, GCS, S3, Azure or a filesystem) - see `<https://grafana.com/docs/loki/latest/storage/>`_.

    **Happn uses the filesystem as the backing store for Loki**.

A typical configuration would be:

.. code-block:: javascript

    {
      ...
      services: {
        data: {
          config: {
            secure: true,
            datastores: [{
              name: "temperatures",
              provider: "loki",
              isDefault: true,
              settings: {
                fsync: true,
                filename: "temperature-data.db"
              }
            }]
          }
        }
      }
      ...
    }

.. admonition:: Syncing to the filesystem

    The field :code:`fsync` forces immediate syncing with the filesystem backing store when data is modified.

Nedb
----

A typical Nedb configuration block can be found below:

.. code-block:: javascript

    {
      ...
      services: {
        data: {
          config: {
            secure: true,
            datastores: [{
              name: "temperatures",
              provider: "nedb",
              isDefault: true,
              settings: {
                fsync: true,
                filename: "temperature-data.db"
              }
            }]
          }
        }
      }
      ...
    }

.. tip::

    The above configuration will cause all data operations on the :code:`temperatures` data store to be persisted to the file :code:`temperature-data.db`.

    More information about querying data can be found :ref:`here<querying-data>`.

.. note::

    The full set of configuration options are covered in :ref:`happn-configuration`.

Mongo
-----

A typical Mongo configuration block can be found below:

.. code-block:: javascript

    {
      ...
      services: {
        data: {
          config: {
            secure: true,
            datastores: [{
              name: "temperatures",
              provider: "mongo",
              isDefault: true,
              settings: {
                collection: "temperatures",
                url: "mongodb://127.0.0.1:27017"
              }
            }]
          }
        }
      }
      ...
    }

.. note::

    Mongo requires additional information which is contained within the **settings** field:

    * :code:`url` - the url to the Mongo instance
    * :code:`collection` - the db collection name

        * this can also contain a replicaset, eg: :code:`mongodb://host1:27017,host2:27017,host3:27017/database?replicaSet=myRS`