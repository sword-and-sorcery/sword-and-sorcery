Sword and sorcery
=================

This repository gathers common information for the projects inside the 
[sword-and-sorcery](https://github.com/sword-and-sorcery) organization.
The objective of all these repos is to build a game engine (board game)
using Conan C/C++ package manager to gain more knowledge about Conan
itself in a real scenario, so take into account that:
 * the project will be artificially complicated in terms of libraries
   and packages
 * working with Conan is the final aim, so it may not be playable soon.

## Documentation

Full documentation about the project can be generated using sphinx, just
execute `make html` in this folder.

## Repositories

Although each project contains its own `README.md` file, here it is a brief
about each project:
 * [ui-tileset](https://github.com/sword-and-sorcery/ui-tileset): 
   provides classes to handle tiles and tilesets.
 * [ui-tileset-glfw](https://github.com/sword-and-sorcery/ui-tileset-glfw):
   texture storage/loader using GLFW (OpenGL). Adds a tileset and retrieve
   textures one by one.
 * [core-messages](https://github.com/sword-and-sorcery/core-messages):
   definition of common messages across the framework.
 * [core-communications](https://github.com/sword-and-sorcery/core-communications):
   module dedicated to communications.
 * [ui-board_game](https://github.com/sword-and-sorcery/ui-board_game):
   stores the elements and positions of a game, it will connect to a game engine
   and update positions, broadcast changes and handle the communications between
   applications.
 * [assets-dungeon](https://github.com/sword-and-sorcery/assets-dungeon): assets
   for a dungeon.
 * [conanquest-fantastic-adventures](https://github.com/sword-and-sorcery/conanquest-fantastic-adventures):
   this package gathers the executables, libraries, assets and resources needed to run a game

## Conan

Some tools, POC, scripts,... and resources to work with Conan can be found
in the `conan` folder inside this repo, read across the `README.md` in that
folder to know more.
