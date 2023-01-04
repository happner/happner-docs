Basic server client
~~~~~~~~~~~~~~~~~~~
To connect to a running instance of **happn-3** server from a *server application*:

.. code-block:: javascript

    const { HappnClient } = require('happn-3');
    const client;
    const config = {
        host: "127.0.0.1",
        port: 55000,
    };

    client = await HappnClient.create(config);