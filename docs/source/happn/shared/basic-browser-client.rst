Basic browser client
~~~~~~~~~~~~~~~~~~~~
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