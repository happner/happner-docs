Starting a basic happn-3 server
-------------------------------
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