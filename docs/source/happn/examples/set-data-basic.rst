..  _basic-pubsub-1:

Example: Basic data operations
==============================
In this example, we will create a **happn server** instance and connect 2 **server clients** to it.

* *client1* will subscribe to an event path on the happn server
* *client2* will set a data object on the happn server

Expectations
~~~~~~~~~~~~
*client1* should receive an event emitted by the server, containing information about the data that was set by *client2*.
*client1* will then explicitly retrieve data from the data store to confirm that it was persisted.

Code
~~~~
Create a file (eg: :code:`set-data-basic.js`) and paste the following code into it:

.. code-block:: javascript

    const Happn = require("happn-3");
    const HappnClient = Happn.client;

    let server;

    // create server with empty configuration - internal defaults will be used
    Happn.service.create({}).then((happn) => {
      server = happn;
      server.log.info("server up");

      // create client1 with empty configuration - internal defaults will be used
      HappnClient.create({}).then((client1) => {
        // subscribe to all events on /data path
        client1.on("/data/*", (msg, meta) => {
          console.log("event detected: ", msg);

            // now retrieve data from the data store
            client1.get("data/").then(result => {
                console.log("retrieved data: ", result);
            })
        });
      });

    // create client2 with empty configuration - internal defaults will be used
      HappnClient.create({}).then((client2) => {
        const payload = {
          property1: "property1",
          property2: "property2",
          property3: "property3",
        };

        // set a data point on the data/ path
        client2.set("data/", payload, (e, result) => {
          console.log("data has been set; result: ", result);
        });
      });
    });

Run the above using :code:`node set-data-basic.js`

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

        client2.set("data/", payload, options, (e, result) => {
          console.log("data has been set; result: ", result);
        });
        ...

Output
~~~~~~
The first block of output will display the default address and port of the happn server, eg:

.. code-block:: bash

    2023-01-05 13:18:20.829 [ INFO] -   232ms butterleader_2zKoK5mATAyv08iRg_iCCQ-0 (HappnServer) happn version 13.7.2 listening at 0.0.0.0:55000
    2023-01-05 13:18:20.834 [ INFO] -     5ms butterleader_2zKoK5mATAyv08iRg_iCCQ-0 (HappnServer) server up

The next block of output will display the console logs:

.. code-block:: bash

    event detected:  {
      property1: 'property1',
      property2: 'property2',
      property3: 'property3'
    }
    data has been set; result:  {
      property1: 'property1',
      property2: 'property2',
      property3: 'property3',
      _meta: {
        path: 'data/',
        created: 1672915267665,
        modified: 1672915267665,
        published: true,
        type: 'response',
        status: 'ok',
        eventId: 4,
        sessionId: '2993d9f4-9d0d-4211-8266-045b17c0f0fe',
        action: 'set'
      }
    }

Under the hood
~~~~~~~~~~~~~~
By default happn uses an in-memory data store to persist data (we are using the :code:`set` function on the client to persist data),
but through :ref:`configuration<happn-configuration>` we are able to persist data to a number of different data stores such as :code:`nedb`,
:code:`mongo` and others.


.. autosummary::
   :toctree: generated