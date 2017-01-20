# mongodb-dev-centos7
A vagrant box pre-configured using ansible for doing MongoDB dev on CentOS 7.0.

Currently setup to let you compile the following MongoDB Drivers:

- C Driver
- C++ Driver
- Java Driver

It will also come configured with these tools:

- MongoDB m
- MongoDB mtools

## Building Notes

CentOS cmake is currently still on cmake 2+ but the MongoDB C++ Driver requires cmake 3+. When following the MongoDB C++ Driver instructions to build the driver please use cmake3 like so:

``` bash
cmake3 -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=/usr/local ..
```

Also by default after building the C Driver the driver installs into /usr/local. However you still need to specify the pkgconfig location like so:

``` bash
PKG_CONFIG_PATH="/usr/local/lib/pkgconfig" cmake3 -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=/usr/local ..
```
