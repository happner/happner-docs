Getting started
===================

Prerequisites
-------------

* Node javascript runtime (preferably v16 or higher)
* npm package manager

Happn
-----

Initial setup
~~~~~~~~~~~~~

* Create a project directory
* :code:`cd` into the directory and initialise a Node application using :code:`npm init`

  * follow the prompts to generate a :code:`package.json` file

* Install the *happn* package using :code:`npm i happn-3`


Running a happn-3 server using minimal code
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

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
~~~~~~~~~~~~~~~~~~~~~~~~~~~~
To connect to a running instance of *happn-3* server from another server:

.. code-block:: javascript

    const { HappnClient } = require('happn-3');
    const client;
    const config = {
        host: "127.0.0.1",
        port: 55000,
    };

    client = await HappnClient.create(config);


The browser-based happn client
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
To connect to a running instance of *happn-3* server from a browser application:

.. code-block:: html

    <script type="text/javascript" src="http://localhost:55000/browser_client"></script>
    <script>
    const config = {
        host: "127.0.0.1",
        port: 55000,
    };
    const client = await HappnClient.create(config);

    </script>

Happner
-------

Initial setup
~~~~~~~~~~~~~

* Create a project directory
* :code:`cd` into the directory and initialise a Node application using :code:`npm init`

  * follow the prompts to generate a :code:`package.json` file

* Install the *happner* package using :code:`npm i happner-2`


.. autosummary::
   :toctree: generated

