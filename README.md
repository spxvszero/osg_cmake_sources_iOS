## What is this

This is the [openscenegraph](https://www.openscenegraph.com/) make sources for iOS platform. The OpenSceneGraph git repo is : https://github.com/openscenegraph/OpenSceneGraph



## Other Info

Cross-Platform-guide

https://github.com/OGStudio/openscenegraph-cross-platform-guide

OSG Cook book recipes repo

https://github.com/xarray/osgRecipes

Sample Data

https://github.com/openscenegraph/OpenSceneGraph-Data

## ThirdParty Official Download Site

* Proj	

  https://proj.org

* gdal

  https://gdal.org

  (gdal build guide for iOS : https://gis.stackexchange.com/questions/434514/build-gdal-3-x-for-ios)

## Other Tips

* XCode show `Could not find or use auto-linked framework 'CoreAudioTypes': framework 'CoreAudioTypes' not found`  Error while building.

  This maybe appear while plugin library does not import correctly.

* OSG report `Error, no WindowSystemInterface available, cannot create windows.`

  Use `USE_GRAPICSWINDOW_IMPLEMENTATION(IOS)`  under the `#include <osgDB/Registry>`

* `*.osgb` files could not read correctly

  Need  `USE_OSGPLUGIN(osg2)` and `USE_SERIALIZER_WRAPPER_LIBRARY(osg)` to import the plugin library.

  And the `*.osg` files use these `USE_OSGPLUGIN(osg)` and `USE_DOTOSGWRAPPER_LIBRARY(osg)`
