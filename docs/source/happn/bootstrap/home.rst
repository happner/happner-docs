Getting started
===============

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


.. include:: ../shared/basic-server.rst


Creating a happn-3 client
-------------------------

.. NOTE::

    The *happn-3* package also contains a client which takes care of the complexities of communicating with the server. See the examples below.

.. include:: ../shared/basic-server-client.rst

.. include:: ../shared/basic-browser-client.rst

Next steps
----------
Now that you have seen how to set up a basic server and client(s), take a look at this simple working :ref:`example<simple-example-1>`.

.. autosummary::
   :toctree: generated

