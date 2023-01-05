..  _simple-example-1:

Example 1: Basic pubsub
=======================
In this example, we will create a **happn server** instance and connect 2 **server clients** to it.

* *client1* will subscribe to all data events emitted by the happn server
* *client2* will set a data point on the happn server

Expectations
~~~~~~~~~~~~
*client1* should receive an event emitted by the server, containing information about the data that was set by *client2*.

Code
~~~~
Create a file (eg: :code:`example1.js`) and paste the following code into it:

.. code-block:: javascript

    const Happn = require("happn-3");
    const HappnClient = Happn.client;

    let server;

    // create the server instance - by default uses address 0.0.0.0 and port 55000
    Happn.service.create({}, (e, happn) => {
      if (e) {
        console.error(e);
        throw e;
      }

      server = happn;
      server.log.info("server up");

      // create a client - by default connects to address 0.0.0.0:55000
      HappnClient.create().then((client1) => {
        // subscribe to all events on the 'data' path
        client1.on("/data/*", (msg, meta) => {
          console.log("event detected: ", msg);
        });
      });

      // create a client- by default connects to address 0.0.0.0:55000
      HappnClient.create().then((client2) => {
        const payload = {
          property1: "property1",
          property2: "property2",
          property3: "property3",
        };

        // set a data point
        client2.set("data/", payload, (e, result) => {
          console.log("data has been set; result: ", result);
        });
      });
    });



Run the above using :code:`node example1.js`

Output
~~~~~~
The output when running the above code will be:

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

.. autosummary::
   :toctree: generated