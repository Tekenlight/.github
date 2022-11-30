# evlua

Designed to be an open source, cross platform lua runtime environment for construction of scalable web applications

#### Goals
1. IO event driven (async) processing
2. lua (4GL) for development
3. Multi threaded, with co-operative multitasking (switch task upon IO event)
4. Usage of co-routines to achieve flowing code, i.e. no need for callbacks or promises

#### Inspired by
Node.js, golang


## Modules
### evpoco
Platform for runnning of lua code in asynchronous and event driven manner. This module provides 2 components

1. evlua: A standalone component to execute lua code in event driven manner
2. evluaserver: A HTTP(S) based server that listens to HTTP requests and hands them over to a lua script for processing

The components are equipped with libraries that provide utilities to achieve various functionalities

1. Platform: A library tha provides various functions to access platform level functions
2. Server (included in the platform)
	1. Request: A library to access various parts of the request that has arrived
	2. Response: A library to generate the response to be sent to the clinet
3. Client (evclient)
	1. TCP/HTTP(s) client connection
	2. Request: Library to construct a HTTP(s) request to be sent to a service
	3. Response: Library to access various parts of the response from a service
4. TLS/SSL support (evlnetssl) 
5. Socket connection pool
6. Websockets
	1. Websocket client
	2. Webscket server


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


