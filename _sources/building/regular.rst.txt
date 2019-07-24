
.. _building-regular-build:

Regular build
+++++++++++++

In order to build this project from sources you should create all the
Conan packages in the organization, although you can use your preferred approach,
this is our recommendation for you:


#. Clone all the repositories at the same level (:ref:`tool-mu-repo` is a tool
   that can help you to handle repositories with this layout):

   .. code-block:: bash

      git clone https://github.com/sword-and-sorcery/core-messages.git
      git clone https://github.com/sword-and-sorcery/core-communications.git
      git clone https://github.com/sword-and-sorcery/assets-dungeon.git
      git clone https://github.com/sword-and-sorcery/ui-tileset.git
      git clone https://github.com/sword-and-sorcery/ui-tileset-glfw.git
      git clone https://github.com/sword-and-sorcery/ui-board_game.git
      git clone https://github.com/sword-and-sorcery/ui-board-imgui.git
      git clone https://github.com/sword-and-sorcery/conanquest-fantastic-adventures.git

#. Create packages for all regular projects

   .. code-block:: bash

      conan create core-messages/conanfile.py sword/sorcery
      conan create core-communications/conanfile.py sword/sorcery
      conan create assets-dungeon/conanfile.py sword/sorcery
      conan create ui-tileset/conanfile.py sword/sorcery
      conan create ui-tileset-glfw/conanfile.py sword/sorcery
      conan create ui-board_game/conanfile.py sword/sorcery
      conan create ui-board-imgui/conanfile.py sword/sorcery

#. The actual game is contained in the last repository listed above, `conanquest-fantastic-adventures`.
   It contains two packages:

    * `ui-board-imgui`: the user interface with all the assets, elements and positions of fixed images, and
    * `core`: the game server, which is responsible of managing the rules and broadcasting the game state.

   You can follow two different approaches to build these final applications and run them:
    * Build the packages as usual and use the `deploy` generator:

      .. code-block:: bash

         conan create conanquest-fantastic-adventures/ui-board-imgui/conanfile sword/sorcery
         mkdir <deploy-dir> && cd <deploy-dir>
         conan install conanquest+ui-board-imgui/0.0@sword/sorcery -g deploy
         cd conanquest+ui-board-imgui 
         ./bin/board_imgui --config ./data/episodes/01-the-labyrinth.xml

    * Build the package locally:

      .. code-block:: bash

         cd conanquest-fantastic-adventures/ui-board-imgui
         mkdir build && cd build
         conan install ..
         conan source ..
         conan build .. -sf .

         ./bin/board_imgui --config data/episodes/01-the-labyrinth.xml

   The output of the `board_imgui` command should show a window like the following one:

   .. figure:: ../images/conan-main_window.png
      :width: 800px
      :alt: ImGUI windows with the dungeon

      ImGUI window with the dungeon.
