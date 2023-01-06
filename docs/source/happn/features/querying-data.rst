Querying data
=============

.. IMPORTANT::

    **A note on paths**

    Happn uses a path structure when performing CRUD operations on the data store. The following rules apply:

    * when storing a single object, a unique path must be used, eg: :code:`/data/users/123/orders/876`

    * when retrieving data, a single record can be retrieved using the same path, or a collection of records can be retrieved by using a wildcard structure, eg:

        * :code:`/data/*` will return *all* records below the root :code:`data` path
        * :code:`/data/users/*` will return *all* users
        * :code:`/data/users/123/orders/*` will return *all* orders for a specific user

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

.. NOTE::

    The :code:`set` function on the client accepts a number of options, ie:

    * noPublish - sets the data but does not publish to subscribers
    * noStore - does not store the data but publishes to subscribers
    * merge - merges an existing data object with a new object, newer fields are overwritten

    eg:

    .. code-block:: javascript

        ...

        const options = {
            noPublish: false,
            noStore: false,
            merge: true
        };

        client.set("data/", payload, options).then(result => {
          console.log("data has been set; result: ", result);
        });

        ...

Retrieving data
---------------

Retrieving objects and collections
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Use the :code:`get` function on the client:

.. code-block:: javascript

    ...

    client.get("data/", payload).then(result => {
      console.log("retrieved data: ", result);
    });

    ...

.. NOTE::

    The :code:`get` function also accepts an optional set of query *options* and filter *criteria*.

    * options:

        * fields - object fields to return
        * sort  - the field to sort on
        * limit - limits the amount of records returned
        * skip  - the amount of records to skip before querying

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

    ...

    client.getPaths("data/*", payload).then(result => {
      console.log("retrieved paths: ", result);
    });

    ...


