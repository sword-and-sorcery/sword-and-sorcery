Building the project
--------------------

As the aim of this project is to eat our own food, we highly recommend you
to use whatever you are used to for a Conan project having multiple packages,
and report feedback or errors if you find any issue.

Said that, you can find in the several sections *step by step* documentation
on how to build the project from sources. Before running into any of them
you may need to add the following remote to find `grpc` (Google Protocol Buffers)
package as it is not yet in `conan-center`:

.. code-block:: bash

    conan remote add inexorgame https://api.bintray.com/conan/inexorgame/inexor-conan


.. toctree::
   :maxdepth: 0
   :caption: Build the full project:

   regular
   workspace

.. figure:: ../images/conan-ui-dep-graph.png
    :width: 800px
    :alt: Dependency graph for UI application

    Dependency graph for UI application


