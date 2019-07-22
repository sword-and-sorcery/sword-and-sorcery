Getting started
===============

Developing the sources
++++++++++++++++++++++

Use a workspace:

-  Clone all the projects in the Github organization `sword-and-sorcery`_

   .. code-block:: bash

      git clone git@github.com:sword-and-sorcery/sword-and-sorcery.git
      git clone git@github.com:sword-and-sorcery/conanquest-fantastic-adventures.git
      git clone git@github.com:sword-and-sorcery/ui-board-imgui-glfw-opengl3.git
      git clone git@github.com:sword-and-sorcery/ui-board_game.git
      git clone git@github.com:sword-and-sorcery/core-communications.git
      git clone git@github.com:sword-and-sorcery/core-messages.git
      git clone git@github.com:sword-and-sorcery/ui-tileset-glfw.git
      git clone git@github.com:sword-and-sorcery/assets-dungeon.git
      git clone git@github.com:sword-and-sorcery/ui-tileset.git

-  It might be useful to use the `mu-repo` tool to pull all the repos at the same time and so on:

    `pip install mu-repo`
    `mu register --all`
    `mu pull`

-  The project files are at `conanquest-fantastic-adventures`_.
   There is a hardcoded path at the `conanquest-fantastic-adventures/_workspace/layout_cmake` file,
   change it to the basepath of your workspace. Modify the paths to the
   editable projects if needed (I'm cloning all the projects inside the same
   directory).


- Add the needed remotes:

  `conan remote add inexorgame https://api.bintray.com/conan/inexorgame/inexor-conan`

- Go to a clean build folder and install the deps. e.g `conanquest-fantastic-adventures/_workspace/cmake-build-debug`:

  `conan workspace install ..`


Running the project
+++++++++++++++++++

To run the generated executable (from package `ui-board-imgui-glfw-opengl3`) you need a configuration file and
the assets for the game. There is a convenient `conanfile.py` to gather all the needed stuff inside the
main repository: `conanquest-fantastic-adventures/ui-board-imgui-glfw-opengl3`_. Follow these steps:

.. code-block:: bash

   cd conanquest-fantastic-adventures/ui-board-imgui-glfw-opengl3
   mkdir build && cd build
   conan install ..
   conan source .. 
   conan build .. -sf .

This set of commands gathers the required binaries in `bin` folder and the assets for all the episodes in 
the `data` directory. Now you can execute any scenario available:

.. code-block:: bash

   ./bin/board_imgui --config ./data/the-labyrinth.xml


.. _`sword-and-sorcery`: https://github.com/sword-and-sorcery
.. _`conanquest-fantastic-adventures`: https://github.com/sword-and-sorcery/conanquest-fantastic-adventures/tree/master/_workspace
.. _`conanquest-fantastic-adventures/ui-board-imgui-glfw-opengl3`: https://github.com/sword-and-sorcery/conanquest-fantastic-adventures/tree/master/ui-board-imgui-glfw-opengl3
