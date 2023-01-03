Getting started
===================

Happn
-----

Prerequisites
~~~~~~~~~~~~~

* Node javascript runtime (preferably v16 or higher)
* npm package manager

Initial setup
~~~~~~~~~~~~~

* Create a project directory
* :code:`cd` into the directory and initialise a Node application using :code:`npm init`

  * follow the prompts to generate a :code:`package.json` file

* Install the :code:`happn` package using :code:`npm i happn-3`


Minimal code using a callback
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

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



.. autosummary::
   :toctree: generated

