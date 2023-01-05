Basic server client
~~~~~~~~~~~~~~~~~~~
To connect to a running instance of **happn-3** server from a *server application*:

.. code-block:: javascript

    const Happn = require("happn-3");
    const HappnClient = Happn.client;

    HappnClient.create().then((client) => {
      // do something with the client....
    });