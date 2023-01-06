..  _pub-sub-basic:

Example: Basic pubsub
=====================
In this example, we will create a **happn server** instance and connect 2 **server clients** to it.

* *client1* will subscribe to an event path on the happn server
* *client2* will publish an object to the happn server

Expectations
~~~~~~~~~~~~
*client1* should receive an event emitted by the server, containing information about the object that was published by *client2*.

Code
~~~~
Create a file (eg: :code:`pub-sub-basic.js`) and paste the following code into it:

.. code-block:: javascript

    const Happn = require("happn-3");
    const HappnClient = Happn.client;

    let server;

    // create server with empty configuration - internal defaults will be used
    Happn.service.create({}).then(happn => {
      server = happn;
      server.log.info("server up");

      // create client1 with empty configuration - internal defaults will be used
      HappnClient.create({}).then(client1 => {
        // subscribe to all events on /data path
        client1.on("/data/*", (msg, meta) => {
          console.log("event detected: ", msg);
        });
      });

    // create client2 with empty configuration - internal defaults will be used
      HappnClient.create({}).then(client2 => {
        const payload = {
          property1: "property1",
          property2: "property2",
          property3: "property3",
        };

        // publish an object on the data/ path
        client2.publish("data/", payload).then(result => {
          console.log("data has been published; result: ", result);
        });
      });
    });

Run the above using :code:`node pub-sub-basic.js`

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
    data has been published; result:  {
      _meta: {
        path: 'data/',
        eventId: 4,
        type: 'response',
        status: 'ok',
        published: true
      }
    }


Under the hood
~~~~~~~~~~~~~~
Using the :code:`publish` function on the client will trigger the server to emit an event to all subscribers on this path.
**No data is persisted** on the server.

.. autosummary::
   :toctree: generated