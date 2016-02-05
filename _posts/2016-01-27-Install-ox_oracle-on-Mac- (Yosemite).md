---
layout: post
title: "Install ox_oracle on Mac (Yosemite)"
date: 2016-01-27
---


ox_Oracle is a python module that allows developers to connet to Oracle Database. Although The installation process is messy process, we'll try to make it simple for you.

&nbsp;

Create a directory ```/usr/lib/share/oracle```
Download the necessary zip files from [here][1]:

- instantclient-basic-macosx
- instantclient-sdk-macosx


Unzip both files at the same location, ```/usr/lib/share/oracle ```

All the files is uncompressed in dicrectroy ```instantclient_11_2```, sdk will be unzipped in a subdirectory.

For ease of use, set ```$ORACLE_HOME``` to this directory:
```sh
export ORACLE_HOME=/usr/lib/share/oracle/instantclient_11_2
```

Create a symlink to you SO file. 
(Note: Make sure the version number might be different.)
```sh
cd $ORACLE_HOME
ln -s libclntsh.dylib.11.2 libclntsh.dylib
ln -s libocci.dylib.11.2 libocci.dylib
```

Update path:
```sh
export DYLD_LIBRARY_PATH=$ORACLE_HOME
export LD_LIBRARY_PATH=$ORACLE_HOME
```

Finally, install cx_oracle with pip:

```sh
pip install cx_oracle
```

&nbsp;

***References:***

Installing cx_Oracle for Python/ Mac OSX. Retrieved from https://gist.github.com/neara/f9b41fcf19b5f25ccd30#file-cx_oracle_instructions-md

Installing python cx_oracle on Ubuntu. Retrieved from https://gist.github.com/kimus/10012910


[1]: http://www.oracle.com/technetwork/topics/linuxx86-64soft-092277.html
