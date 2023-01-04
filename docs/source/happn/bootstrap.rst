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


Creating a happn-3 server
-------------------------
The example below illustrates creating a server using minimal code.

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


Creating a happn-3 client
-------------------------

.. NOTE::

    The *happn-3* package also contains a client which takes care of the complexities of communicating with the server. See the examples below.

Server-side client
~~~~~~~~~~~~~~~~~~

To connect to a running instance of **happn-3** server from a *server application*:

.. code-block:: javascript

    const { HappnClient } = require('happn-3');
    const client;
    const config = {
        host: "127.0.0.1",
        port: 55000,
    };

    client = await HappnClient.create(config);


Browser client
~~~~~~~~~~~~~~
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

Next steps
----------
Now that you have seen how to set up a basic server and client(s), take a look at this simple working :ref:`example<simple-example-1>`.

.. autosummary::
   :toctree: generated

