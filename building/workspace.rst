
Workspace
---------

Workspace is a really powerful feature of Conan to build a single project for your IDE
from different packages. `Find docs here <https://docs.conan.io/en/latest/developing_packages/workspaces.html>`_.

Workspaces work for packages with a `CMakeLists.txt` file, they are nice for
**developing several packages at the same time**, but you will need to create the
packages in the 'conanquest-fantastic-adventures' repository yourself as they are
not C++ packages. Check the :ref:`building-regular-build` section if you need advice
on how to build it.


Released implementation
+++++++++++++++++++++++

WIP. Need to try and document (use and modify files in folder 'conan/ws').


POC #5314
+++++++++

There is an alternate implementation of workspaces trying to deal with some issues
related to current implementation. In order to use this implementation (just a POC),
you will need to use the `developing version of Conan for this PR <https://github.com/conan-io/conan/pull/5314>`_.

#. Clone all the repositories into the same folder as you would do for a regular
   build (see previous section).

#. Create an empty folder to store the build files for the project

   .. code-block:: bash

      mkdir <path-to-buildir> && cd <path-to-buildir>

#. Create the workspace (use the settings you want). 

   .. code-block:: bash

      conan workspace install <path-to-repos>/sword-and-sorcery/sword-and-sorcery/conan/ws5314/conan_ws.yml [-s build_type=Debug ...]

   In the previous command we are using a file provided within the repository that adds all
   the packages of the project to the workspace, you can use this file as a starting point
   to generate the workspace that fits your needs.

#. Open this folder (previous command created a root `CMakeLists.txt`) using your
   favorite IDE with CMake support

#. Build!
