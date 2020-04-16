# Platformio Version Increment
Simple version increment script for Platformio.
DPsoftware (Davide Perini)  

Platformio does not have a tool to automatically increment the version number of an app when building it or when uploading it to a microcontroller so I decided to write a script to do it.

To use it please add this line in your platformio.ini
```
extra_scripts = pre:platformio_version_increment/version_increment.py
```

from the root of your project run
```
git submodule add git@github.com:sblantipodi/platformio_version_increment.git platformio_version_increment
```

upload your software to your microcontroller, in the root of your project you will find two files:
- version
- include/Version.h 

in the version file you will have 0.1.0 version, edit it with your desiderd version.

Every upload will trigger a +1 on the hotfix number.

In the Version.h file you'll have this:
```
// AUTO GENERATED FILE FROM version_increment.py, DO NOT EDIT THIS FILE
#ifndef VERSION
  #define VERSION "0.1.0"
#endif
#ifndef BUILD_TIMESTAMP
  #define BUILD_TIMESTAMP "2020-04-10 17:58:52.937616"
#endif
```    

use variables as you desire.
