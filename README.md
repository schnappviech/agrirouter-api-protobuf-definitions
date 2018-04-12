![GitHub Logo](res/img/logo.svg)

# agrirouter-api-protobuf-definitions

## Project description

### The agrirouter

The agrirouter is a universal data exchange platform for farmers and agricultural contractors that makes it possible to connect machinery and agricultural software, regardless of vendor or manufacturer. Agrirouter does not save data; it transfers data.

As a universal data exchange platform, agrirouter fills a gap on the way to Farming 4.0. Its underlying concept unites cross-vendor and discrimination-free data transfer. You retain full control over your data. Even data exchange with service providers (e.g. agricultural contractors) and other partners is uncomplicated: Data are very rapidly transferred via the online connection, and if you wish, is intelligently connected to other datasets.

### The current project you're looking at

This project contains the internal Google Protocol Buffer (protobuf) definitions for the communication with the agrirouter. All the definitions are part of the communcation structure of the agrirouter. For more informations see the technical integration guide which you can download from the developer section on the product website.

## External resources

Here are some external resources for the development:

* [My Agrirouter Website](http://www.my-agrirouter.com) 
* [EFDI Protobuf Definition](http://www.lmgtfy.com)

## Development hints

### Language specific compiling of the `*.proto` definitions

#### Java

`not yet defined`

### C++

#### How to install Protobuf C++ Compiler

The following instructions are optimized for Unix based systems. For Windows I recommend to install Cygwin (https://www.cygwin.com/) and do the same steps as if you were on a Unix based system.

#### Download packages

You can download protoc and protobuf packages from https://github.com/google/protobuf/releases.
Make sure you use downloaded the same versions of protoc and protobuf.

E.g. *protoc-3.5.0-linux-x86_64.zip* and *protobuf-cpp-3.5.0.zip*

#### Prepare Protoc

1. Unzip package <br>
   `unzip protoc-3.* -d protoc3`
2. Move protoc to /usr/bin/ <br>
   `sudo mv protoc3/bin/protoc /usr/bin/`
3. Move included packages to /usr/include/ <br>
   `sudo mv protoc3/include/* /usr/include/`
4. Optional: make protoc executable for everyone <br>
   `sudo chmod +x /usr/bin/protoc`
5. Optional: make includes readable for everyone <br>
   `sudo chmod +r /usr/include/google/*`

#### Install Protobuf

Based on https://github.com/google/protobuf/blob/master/src/README.md:

1. Unzip package <br>
   `unzip protobuf-cpp-3.* -d protobuf3`
2. Go to folder *profobuf3* and make file configure executable <br>
   `chmod +x configure`
3. Execute following commands <br>
   `$ ./configure
   $ make
   $ make check
   $ sudo make install
   $ sudo ldconfig` <br>
   Note: If "make check" fails, you can still install, but it is likely that some features of this library will not work correctly on your system. Proceed at your own risk.

#### Use Protoc

If you want to compile some proto files use e.g. `protoc --cpp_out=. ./*.proto` <br>
`--cpp_out` indicates the destination of compiled files. In this case it is the same folder. <br>
`./*.proto` will compile every proto file in this folder.

#### Cross compiling

If you want to use cross compiling you have to use `--host` option when executing `./configure`. <br>
E.g. `./configure --host=powerpc-linux CC=powerpc-linux-gnu-gcc CXX=powerpc-linux-gnu-g++  --with-protoc=/usr/bin/protoc` <br>


Also see https://github.com/eurotech/edc-examples/wiki/Cross-compiling-protobuf-for-ARM-architecture



