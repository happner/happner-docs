..  _simple-example-1:

Example 1
=========
In this example, we will create a **happn server** instance and connect 2 clients to it - a **server client** and a **browser client**.
The browser client will then subscribe to any data events that might occur on the server. The server client will then set a data point on the happn server.

*What do we expect to see?*
The browser client should receive an event emitted by the server, containing information about the data that was set by the server client.


.. autosummary::
   :toctree: generated