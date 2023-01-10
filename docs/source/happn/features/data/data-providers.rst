..  _data-providers:

Data providers
==============

Happn provides a set of out-of-the-box data providers, which can be activated through configuration:

* Nedb (in-memory or file based)
* Loki
* Mongo
* Sqlite
* Elasticsearch

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
                fsync: true
              },
              dbfile: "temperature-data.db"
            }]
          }
        }
      }
      ...
    }

.. tip::

    The above configuration will cause all data operations on the :code:`temperatures` data store to be persisted to the file :code:`temperature-data.db`.
    If an in-memory data store is required, simply **omit** the :code:`dbfile` field.

    More information about querying data can be found :ref:`here<querying-data>`.

.. note::

    The full set of configuration options are covered in :ref:`happn-configuration`.
