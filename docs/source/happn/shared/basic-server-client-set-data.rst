Setting a data point from a server client
-----------------------------------------

.. code-block:: javascript

    const { HappnClient } = require('happn-3');

    // create the client instance
    const client = await HappnClient.create();

    // create a payload to set on the data path
    const payload = { property1:'property1', property2:'property2', property3:'property3' };

    // now set the data via the client
    client.set('data/', (e, result) => {
        console.log(`data has been set; result: ${JSON.stringify(result)}`);
    });