Setting a data point from a server client
-----------------------------------------

.. code-block:: javascript

    const Happn = require("happn-3");
    const HappnClient = Happn.client;

    HappnClient.create().then((client2) => {
      const payload = {
        property1: "property1",
        property2: "property2",
        property3: "property3",
      };

      // set a data point
      client2.set("data/", payload, (e, result) => {
        console.log("data has been set; result: ", result);
      });
    });