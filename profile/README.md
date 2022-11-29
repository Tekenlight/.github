# evlua

Designed to be an open source, cross platform lua runtime environment for construction of scalable web applications

#### Goals
1. IO event driven (async) processing
2. lua (4GL) for development
3. Multi threaded, with co-operative multitasking (switch task upon IO event)
4. Usage of co-routines to achieve flowing code, i.e. no need for callbacks or promises

#### Inspired by
Node.js, golang


## Components
### evpoco
Platform for runnning of lua code in asynchronous and event driven manner. 
This module provides 2 modules

1. evlua: A standalone module to execute lua code in event driven manner
2. evluaserver: A HTTP(S) based server that listens to HTTP requests and hands them over to a lua script for processing

The above two modules are equipped with libraries that act as utilities to achieve various functionalities

1. platform: A library tha provides various functions to access platform level functions
2. server request (evluaserver): A library to access various parts of the request that has arrived
3. server response (evluaserver): A library to generate the response to be sent to the clinet


### service_utils


### efio
Library with these facilities 

1. Thread Pool
2. Event driven and asynchronous FILE IO
3. Lock free synchronization artifacts
4. Lock free (Wait free in case of enqueue) data structures, stack and queue
5. base64 encode/decode and hex encode/decode functions


### Customized luaffifb


### lua_schema


## Dependencies

#### Customized libxml2

#### Customized http-parser

#### Customized libev

#### Customized date

#### Customized hiredis

#### Customized lbc-101

#### Customized lua-5.3.5

#### luaposix

#### Penlight

#### cjson-lua


