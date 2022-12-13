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

The components offer different features to an application

1. Platform: A library that provides a set of API to access platform (os, std library) level functions
	1. Asynchronous FILE IO
	2. HTML Form handling (Server side / Request only)
	3. 	Server Side (incoming) request
	4. 	Server Side (ougoing) response
	5. Client side (outgoing) request
	6. Client side (incoming) response
	7. TCP/IP Sockets
	8. Websockets
		1. Websocket client
		2. Webscket server
	9. Generic utilities
2. Socket connection pool
3. TLS/SSL support (evlnetssl)
4. Crypto library (evlcrypto)
5. Postgresql interface for connections and statments (evpostgres)
6. Sqlite interface for connections and statments (evpostgres)
7. Redis interface for connections and data fetch and store (evredis)
 

### service_utils
A Collection of lua components built on top of evpoco. These components provide an interface to evpoco components to lua and provide certain additional features, together necessary for developing a evlua "web application" as well as a "standalone application".

The general assumption in the applications is that IO is event driven and cooperative multi-tasking is achieved, while having a fixed number of underlying OS threads.

The library itself depends on a host of other libraries listed within this document. Most significant ones being luaffifb, lua_schema, efio

##### Components
1. common: A set of utilities
	1. User context: A lua class that contains access to the environment (user session, database connection, etc...) for an application service
	2. pool_repos: Provides a repository of named connection pools, currently used in websockets
	3. password_generator: A set of reusable functions for random number generation and new password generation
		1. utils: Generation of random integer and generation of random number of bytes
	4. msg_literal: A utility to generate a message based on a template (format string)
2. jwt: A minimalist jwt class to generate, sign and veriy jwt tokens
3. WS (Web Sockets):
	1. web_socket: A class to connect fresh and accept incoming websocket connection requests.
	2. ws_util: Class to close, ping, send and receive messages, access websockets from pool, 
4. SMTP client
5. schemarules:
	1. gval: Tool to specify and generate validation checks that should be done on a given input object to a REST API
	2. Library function to execute the checks
6. orm: 
	1. gtbl: Tool to specify and generate mapping between lua objects and RDBMS (Currently only Postgresql) tables
	2. Library class to achieve SELECT/INSERT/UPDATE/DELETE of one record of a table
	3. Libraty class to achieve single table CRUD operations
7. db: A set of connectors to different databases (Currently only Postgresql and REDIS [WIP])
	1. client_params: A class to hold a set of connection parameters to different databases
	2. ev_database: util to make connection to a database
	3. ev_postgres: Interface to postgresql, provides functions to make connection and execute DML statements
	4. ev_redis: Interace to access data (read and write) in REDIS
8. REST: Collection of classes useful in handling of REST requests, making new ones as well as responding to incoming requests
	1. gidl : Tool to specify as well as generate REST API mapping
	2. context_harness: Class to create a new operating context object, which is an input to all methods implementing REST API
	3. service_client: REST client for interfacing serices which are within one LAN
	4. 	external_service_client: REST client for interfacing services across internet
	5. controller: provides single point of entry to all REST requests "handle_request", to which handle to request and response are passed. This in turn locates the lua class and method to be run for the request based on url
 

### efio
Library with these facilities 

1. Thread Pool
2. Event driven and asynchronous FILE IO
3. Lock free synchronization artifacts
4. Lock free (Wait free in case of enqueue) data structures, stack and queue
5. base64 encode/decode and hex encode/decode functions


### Customized luaffifb
This is a library for calling C function and manipulating C types from lua. It is designed to be interface compatible with the FFI library in LuaJIT (see http://luajit.org/ext_ffi.html). It can parse C function declarations and struct definitions that have been directly copied out of C header files and into lua source as a string.

This is a fork of https://github.com/facebookarchive/luaffifb which is inturn a fork of https://github.com/jmckaskill/luaffi

Certain additional functions have been added over and above the capablities that are in the parent repository.


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


