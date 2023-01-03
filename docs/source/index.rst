Welcome to happner
==================

The **happner** project is a feature-rich realtime framework, built specifically to run in resource-constrained environments (IOT).
It consists of suite of Node libraries, with the primary modules being the following:

- happn-3:
    the bottom layer, this manages data-storage, pub/sub and security. happn-3 can be used independently from the other layers - it's technical equivalent would be firebase.
- happner-2:
    the rpc layer, this sits on top of happn-3 and provides a means of exposing javascript module methods to the outside world.
- happn-cluster:
    sits on top of happn-3, allows for the creation of a pub/sub cluster.
- happner-cluster:
    sits on top of happn-3, happner-2 and happn-cluster, allows for the creation of a clustered rpc setup, where work is distributed across multiple cluster nodes in the cloud.



Contents
--------

.. toctree::
    :maxdepth: 1

    happn-home
    happner-home
    happn-cluster-home
    happner-cluster-home

Developer notes
---------------
- ReadTheDocs tutorial: https://docs.readthedocs.io/en/stable/tutorial/
- Using Sphinx to generate documentation: https://www.sphinx-doc.org/en/master/usage/quickstart.html
- Working with Restructured Text: https://thomas-cokelaer.info/tutorials/sphinx/rest_syntax.html
- Generating Restructured Text from JsDoc using Sphinx: https://pypi.org/project/sphinx-js/
