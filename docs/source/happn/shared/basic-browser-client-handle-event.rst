Handling a data event from a browser client
-------------------------------------------

.. code-block:: html

    <script type="text/javascript" src="http://localhost:55000/browser_client"></script>
    <script>
        // create the client instance
        const client = await HappnClient.create();

        // subscribe to all events on the 'data' path
        client.on('/data/*', (msg, meta) => {
            console.log(`Event detected: ${JSON.stringify(msg)}`);
        });
    </script>