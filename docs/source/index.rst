Welcome to happner
==================

The **happner** project is a feature-rich realtime framework, built specifically to run in resource-constrained environments (IOT).

.. NOTE::
   A **realtime framework** is one where feedback on system events is near-instantaneous. In the happner project, this specifically means that a *pub-sub* model is used to notify interested clients of such events, and an *rpc* model is used to allow immediate invocation of functions between client and server (additional features such as REST are also fully supported).

It consists of suite of Node libraries, with the primary modules being the following:

- :ref:`happn-3<happn-3-home>`:
    the bottom layer, this manages data-storage, pub/sub and security. happn-3 can be used independently from the other layers - it's technical equivalent would be firebase.
- :ref:`happner-2<happner-2-home>`:
    the rpc layer, this sits on top of happn-3 and provides a means of exposing javascript module methods to the outside world.
- :ref:`happn-cluster<happn-cluster-home>`:
    sits on top of happn-3, allows for the creation of a pub/sub cluster.
- :ref:`happner-cluster<happner-cluster-home>`:
    sits on top of happn-3, happner-2 and happn-cluster, allows for the creation of a clustered rpc setup, where work is distributed across multiple cluster nodes in the cloud.

Developer notes
---------------
- ReadTheDocs tutorial: https://docs.readthedocs.io/en/stable/tutorial/
- Using Sphinx to generate documentation: https://www.sphinx-doc.org/en/master/usage/quickstart.html
- Working with Restructured Text: https://thomas-cokelaer.info/tutorials/sphinx/rest_syntax.html
- Generating Restructured Text from JsDoc using Sphinx: https://pypi.org/project/sphinx-js/

.. toctree::
    :hidden:
    :maxdepth: 3

    happn/home
    happner/home
    happn-cluster/home
    happner-cluster/home
    configuration/home