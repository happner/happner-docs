Starting a basic happn-3 server
-------------------------------
The example below illustrates creating a server using minimal code.

.. code-block:: javascript

    const Happn = require("happn-3");
    let server;

    Happn.service.create().then((result) => {
      server = result;
      server.log.info("server up");
    });
