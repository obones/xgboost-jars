xgboost4j
=========

[![Build Status](https://travis-ci.org/obones/xgboost-jars.svg?branch=master)](https://travis-ci.org/obones/xgboost-jars)
[![Build status](https://ci.appveyor.com/api/projects/status/7otoobqx43sd0hja?svg=true)](https://ci.appveyor.com/project/obones/xgboost-jars/branch/master)

Repository to build [xgboost4j](https://github.com/obones/xgboost) JARs.

Build
-----

The build would always use the *latest* version of xgboost and its submodules.
Sadly, there is no way around it at the moment, as the submodules are pinned
to specific commits, and `dmlc-core` received quite a few patches to be buildable
on both CIs. In the future, this behaviour could be safely removed.

Otherwise, the following versions of the dependencies are used

```
HADOOP_VERSION=2.6.0-cdh5.5.0
SPARK_VERSION=2.1.1
SCALA_VERSION=2.11.0
```

You could probably change them to more recent/different version, but this has
not been validated yet.

#### Windows

The Windows build is x64 only and uses Visual Studio 2015.

#### Linux

The Linux build is done inside a CentOS6 Docker container to make sure the
resulting JARs can be executed on ancient Linux distributions like CentOS.

Release
-------

To make a release:

- Bump `XGBOOST_VERSION` in `.travis.yml` and `appveyor.yml`.
- Tag `master` with `XGBOOST_VERSION`.
- Wait :)
