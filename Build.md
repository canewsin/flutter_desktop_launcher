#  Building For Windows :
  You have to Build it yourself for now 
  you can make fork of this repo and make a pull request for windows blobs

  Building:
 - Required Tools:
   - Visual Studio 2017
   - clone this repo https://github.com/google/flutter-desktop-embedding.git and navigate to that folder
   - you will also need GN and ninja click below to download:
     - [ninja](https://github.com/ninja-build/ninja/releases)
     - [gn](https://chrome-infra-packages.appspot.com/dl/gn/gn/windows-amd64/+/latest)

  ## Full instructions are here

  https://github.com/google/flutter-desktop-embedding/blob/master/README.md

  https://github.com/google/flutter-desktop-embedding/blob/master/library/README.md

  ## Dependencies
  Visual Studio Command Line

  The Visual Studio command line build tools, such as vcvars64.bat, must be in your path. They are found under:

  ><Visual Studio Install Path>\2017\<Version>\VC\Auxiliary\Build

  e.g.:

  >C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build

  

  ## jsoncpp

  jsoncpp must be downloaded to 
  `third_party/jsoncpp\src`. 
  
  You can use `tools/dart_tools/bin/fetch_jsoncpp.dart` to simplify this:

  ```
  tools\run_dart_tool.bat fetch_jsoncpp third_party\jsoncpp\src
  ```

  Using the Library

  To build the library, run the following at the root of this repository:

  ```
  $ tools\gn_dart gen out
  $ ninja -C out flutter_embedder
  ```

  Subsequent builds only require the ninja step, as the build will automatically re-run GN generation if necessary.

  The build results will be in the top-level `out\` directory. You will need to link `libflutter_embedder.dll` and `libflutter_engine.dll` into your binary. Public headers will be in `out/include/`; you should point dependent builds at that location rather than the include/ directories in the source tree.

  The DLL provides a minimal C interface, but the recommended approach is to add the code in `out\fde_cpp_library\` to your project, to interact with the library using richer APIs. See `flutter_window_controller.h` and the other headers under that directory for details.
