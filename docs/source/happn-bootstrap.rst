Getting started with Happn
==========================

Prerequisites
-------------

* Node javascript runtime (preferably v16 or higher)
* npm package manager

Initial setup
-------------

* Create a project directory
* :code:`cd` into the directory and initialise a Node application using :code:`npm init`

  * follow the prompts to generate a :code:`package.json` file

* Install the **happn** package using :code:`npm i happn-3`


Running a happn-3 server using minimal code
-------------------------------------------

.. code-block:: javascript

    const happn = require('happn-3');
    const server;
    const config = {
      utils: {
        logLevel: 'error',
      }
    };

    happn.service.create(config, (e, happn) => {
        if(e) {
            console.error(e);
            throw e;
        }

        server = happn;
        server.log.info('server up');
    });

The server-side happn client
----------------------------
To connect to a running instance of **happn-3** server from a *server application*:

.. code-block:: javascript

    const { HappnClient } = require('happn-3');
    const client;
    const config = {
        host: "127.0.0.1",
        port: 55000,
    };

    client = await HappnClient.create(config);


The browser-based happn client
------------------------------
To connect to a running instance of **happn-3** server from a *browser application*:

.. code-block:: html

    <script type="text/javascript" src="http://localhost:55000/browser_client"></script>
    <script>
    const config = {
        host: "127.0.0.1",
        port: 55000,
    };
    const client = await HappnClient.create(config);

    </script>

A working example
-----------------
In this example, we will create a **happn server** instance and connect 2 clients to it - a **server client** and a **browser client**.
The browser client will then subscribe to any data events that might occur on the server. The server client will then set a data point on the happn server.

*What do we expect to see?*
The browser client should receive an event emitted by the server, containing information about the data that was set by the server client.


.. autosummary::
   :toctree: generated

