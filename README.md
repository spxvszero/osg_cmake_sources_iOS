## What is this

This is the [openscenegraph](https://www.openscenegraph.com/) make sources for iOS platform. The OpenSceneGraph git repo is : https://github.com/openscenegraph/OpenSceneGraph



## How to use it

1. Download this repo and unzip it.

2. go into the dir, and git clone the openscenegraph repo in this

3. Edit `run.sh` file, and redirect the `export THIRDPARTY_PATH` 

   (Maybe you also need to edit `-DIPHONE_SDKVER="16.4"` with your local sdk version. You can run `xcrun --sdk iphoneos --show-sdk-path` to get the version number.)

4. copy `run.sh` into `OpenSceneGraph` directory, and run it.

   (While running on iOS devices, maybe you need to remove the link MacOSSDK in XCode build settings. )



## Other Info

#### Some Helpful Links

Cross-Platform-guide

https://github.com/OGStudio/openscenegraph-cross-platform-guide

Cross-Platform-guide-application

https://github.com/OGStudio/openscenegraph-cross-platform-guide-application

OSG Cook book recipes repo

https://github.com/xarray/osgRecipes

Sample Data

https://github.com/openscenegraph/OpenSceneGraph-Data

OSG for iOS + uMundo ：a plugin which can sync camera matrix between devices 

https://github.com/tklab-tud/umundo



#### Local Document Generate

According to this issue https://github.com/openscenegraph/OpenSceneGraph/issues/1063

Turn on CMake option `BUILD_DOCUMENTATION`, and run `make doc_openscenegraph`

It also refer an online document : https://codedocs.xyz/openscenegraph/OpenSceneGraph



## ThirdParty Official Download Site

* Proj	

  https://proj.org

* gdal

  https://gdal.org

  (gdal build guide for iOS : https://gis.stackexchange.com/questions/434514/build-gdal-3-x-for-ios)



## Other Tips

* OSG report `Error, no WindowSystemInterface available, cannot create windows.`

  Use `USE_GRAPICSWINDOW_IMPLEMENTATION(IOS)`  under the `#include <osgDB/Registry>`

* `*.osgb` files could not read correctly

  Need  `USE_OSGPLUGIN(osg2)` and `USE_SERIALIZER_WRAPPER_LIBRARY(osg)` to import the plugin library.

  And the `*.osg` files use these `USE_OSGPLUGIN(osg)` and `USE_DOTOSGWRAPPER_LIBRARY(osg)`

* Add `USE_DOTOSGWRAPPER_LIBRARY(osg)` compile error.

  This statement will search `libosgdb_deprecated_osg.a` library. Make sure import it already. 

* Other Compile failed

  Add `OSG_LIBRARY_STATIC` to Preprocessor Macros may help.
