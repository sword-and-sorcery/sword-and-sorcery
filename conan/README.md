Tools and utilities to work with Conan and projects in this organization

## Workspace (POC 5314)

Utility files to generate a workspace with _all_ the projects
**according to the [POC of PR #5314](https://github.com/conan-io/conan/pull/5314)**
(these files won't work with regular workspaces):

 * (Before starting) These steps assume that you have already cloned all these repositories
   at the same level
 * Create an empty folder to store the build files for the project
   ```bash
   mkdir <path-to-buildir> && cd <path-to-buildir>
   ```
 * Create the workspace (only CMake supported)
   ```bash
   conan workspace install <path-to-repos>/sword-and-sorcery/sword-and-sorcery/conan/ws5314/conan_ws.yml -s build_type=Debug
   ```
 * Open this folder (previous command created a root `CMakeLists.txt`) using your
   favorite IDE with CMake support.
 * Build!
