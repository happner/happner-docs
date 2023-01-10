..  _querying-data:

Querying data
=============

.. admonition:: A note on paths

    Happn uses a path structure when performing CRUD operations on the data store. Think of paths as *keys* to stored objects.

    The following rules apply:

    * when storing a single object, a unique path must be used, eg: :code:`/data/users/123/orders/876`

    * when retrieving data, a single record or a collection of records can be retrieved depending on the path structure, eg:

        * :code:`/data/users/123/orders/876` will return a single record object
        * :code:`/data/*` will return an array *all* records below the root :code:`data` path
        * :code:`/data/users/*` will return an array of *all* users
        * :code:`/data/users/123/orders/*` will return an array of *all* orders for a specific user

    Note the use of a *wildcard* (:code:`*`) to return a collection.

Setting data
------------
Use the :code:`set` function on the client:

.. code-block:: javascript

    const Happn = require("happn-3");
    const HappnClient = Happn.client;

     HappnClient.create().then(client => {
        const payload = {
          property1: "property1",
          property2: "property2",
          property3: "property3",
        };

        client.set("data/", payload).then(result => {
          console.log("data has been set; result: ", result);
        });
    });

.. admonition:: Set options

    The :code:`set` function on the client accepts a number of options, ie:

    * :code:`noPublish` - sets the data but does not publish to subscribers
    * :code:`noStore` - does not store the data but publishes to subscribers
    * :code:`merge` - merges an existing data object with a new object, newer fields are overwritten

    eg:

    .. code-block:: javascript

        const options = {
            noPublish: false,
            noStore: false,
            merge: true
        };

        client.set("data/", payload, options).then(result => {
          console.log("data has been set; result: ", result);
        });

Retrieving data
---------------

Retrieving objects and collections
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Use the :code:`get` function on the client to retrieve objects on a path, eg:

.. code-block:: javascript

    client.get("data/").then(result => {
      console.log("retrieved data: ", result);
    });

.. admonition:: Get options and criteria

    The :code:`get` function also accepts an optional set of query *options* and filter *criteria*.

    * options:

        * :code:`fields` - object fields to return
        * :code:`sort`  - the field to sort on
        * :code:`limit` - limits the amount of records returned
        * :code:`skip`  - the amount of records to skip before querying

    * criteria:

        * a *mongo-like* set of operations that are performed on the queried data

    eg:

    .. code-block:: javascript

        const options = {
          fields: { name: 1 },
          sort: { name: 1 },
          limit: 10,
          skip: 5,
        };

        const criteria = {
          $or: [
            { region: { $in: ["North", "South", "East", "West"] } },
            { town: { $in: ["North.Cape Town", "South.East London"] } },
          ],
          surname: { $in: ["Bishop", "Emslie"] },
        };

        client
          .get("/users/*", {
            criteria: criteria,
            options: options,
          })
          .then(results => {
            // do something with the results
           });


Retrieving paths only
~~~~~~~~~~~~~~~~~~~~~

Use the :code:`getPaths` function on the client.

.. code-block:: javascript

    client.getPaths("data/*").then(result => {
      console.log("retrieved paths: ", result);
    });

.. admonition:: Paths as keys

    On occasion you may need to retrieve all the paths below a specific parent path rather than the records themselves (ie: keys only). This allows a client to
    parse the paths for a specific record path before retrieving the record itself.


Deleting data
-------------

Deleting data is a simple operation - use the :code:`remove` function:

.. code-block::

    client.remove("data/users/123").then(result => {
        console.log("deleted record: ", result);
    });

.. warning::

    Be careful when executing the :code:`remove` function - if you specify a path that contains a wildcard (:code:`*`), you will remove all records below that path.