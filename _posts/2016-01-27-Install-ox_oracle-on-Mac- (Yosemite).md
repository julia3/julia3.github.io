---
layout: post
title: "Install ox_oracle on Mac (Yosemite)"
date: 2016-01-27
---

#### Create a directory ```/usr/lib/share/oracle```
Download the necessary zip files from http://www.oracle.com/technetwork/topics/linuxx86-64soft-092277.html
```sh
    - instantclient-basic-macosx
    - instantclient-sdk-macosx
```

#### Unzip both files at the same location, ```/usr/lib/share/oracle ```
All the files is uncompressed in dicrectroy ```instantclient_11_2```, sdk will be unzipped in a subdirectory.
#### For ease of use, set $ORACLE_HOME to this location:
```sh
export ORACLE_HOME=/usr/lib/share/oracle/instantclient_11_2
```

#### Create a symlink to you SO file. (Note: Make sure the version number might be different.)
```sh
cd $ORACLE_HOME
ln -s libclntsh.dylib.11.2 libclntsh.dylib
ln -s libocci.dylib.11.2 libocci.dylib
```

#### Update path:
```sh
export DYLD_LIBRARY_PATH=$ORACLE_HOME
export LD_LIBRARY_PATH=$ORACLE_HOME
```

#### Finally, install cx_oracle with pip:
pip install cx_oracle

