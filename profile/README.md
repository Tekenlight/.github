# evlua

<img src="../doc/images/logotk.png" width="200"/>

Designed to be an open source, cross platform lua runtime environment for construction of scalable web applications

#### Goals
1. IO event driven (async) processing
2. lua (4GL) for development
3. Multi threaded, with co-operative multitasking (switch task upon IO event)
4. Usage of co-routines to achieve flowing code, i.e. no need for callbacks or promises

#### Inspired by
Node.js, golang


## Modules

![alt text][overview]
### [evpoco](https://github.com/Tekenlight/evpoco)
Platform for runnning of lua code in asynchronous and event driven manner

This is the underlying CORE of the evlua framework. It is a multi-threaded C platform that manages TCP sockets, TLS encryptio/decryption event handling among other things.

### [efio](https://github.com/Tekenlight/efio)
A library written in C/C++, to facilitate access capabilities to evpoco.
* Event driven file io
* sync artifacts
* lockfree datastructures
* Thread pool
* Generic utilities

### [lua\_schema](https://github.com/Tekenlight/lua_schema)
XSD schema processor for lua, the library has the following capabilities
* Command line utility for parsing of XSD files and compilation of XSD grammar to lua
* Lua class for parsing of XML / JSON data and generation of corresponding lua objects.
  Any deviations from grammar (as specified in XSD) are caught at the time of parsing
* Lua class for generation of XML / JSON data from lua tables
  Any deviations from grammar (as specified in XSD) are caught at the time of generation

### [Customised luaffifb](https://github.com/Tekenlight/luaffifb)
Framework for calling C function and manipulating C types from lua

Allows calling external C functions and using C data structures from pure Lua code.

The FFI library largely obviates the need to write tedious manual Lua/C bindings in C. No need to learn a separate binding language — it parses plain C declarations.

### [service\_utils](https://github.com/Tekenlight/service_utils)
Framework which provides a layer of stubs and utilities to facilitate classes implimented in lua be exposed as REST API.
It is a lua library, takes care of marshalling/unmarshalling database connection management, authorization, before the controlled is passed on to the application lua classes.

It also provides utility classes like SMTP, HTTP, JWT, ORM among  others for implementation of those features in lua applications.

## Dependencies
* [Customised date](https://github.com/Tekenlight/date): Lua Date and Time module for Lua 5.x.
* [Customised lbc-101](https://github.com/Tekenlight/lbc-101); This is an arbitrary precision library for Lua
* [Customised libxml2](https://github.com/Tekenlight/libxml2); Libxml2 is the XML C parser and toolkit developed for the Gnome project (but usable outside of the Gnome platform)
* [luaposix](https://github.com/Tekenlight/luaposix); This is a POSIX binding for Lua 5.1, 5.2, 5.3 and 5.4;
* [Penlight](https://github.com/Tekenlight/Penlight): Penlight brings together a set of generally useful pure Lua modules, focusing on input data handling (such as reading configuration files), functional programming (such as map, reduce, placeholder expressions, etc)
* [lua-cjson](https://github.com/Tekenlight/lua-cjson): The Lua CJSON module provides JSON support for Lua.

## Roadmap
* Code refactor
	* Refactor HTTP client (service\_utils)
	* Refactor REST/controller (service\_utils)
	* Refactor evluaserver and evlua
	* Refactor evpoco
* Support for HTTP connections via proxy server
* Mysql client library
* MongoDB client library
* SQLite client library
* Constraints in table specs (ORM)
* Caching of data in TAO
* Support for HTTP2
* Build and deploy of various packages along with their dependencies
	* Merge dependent libraries to a 2 major ones, evpoco and service\_utils
	* evpoco: Meger libev, lua, efio, resdis-client and http-parser within evpoco
	* lua\_schema: Merge necessary parts of efio, libxml2 into the same library
	* service\_utils: Merge lua-uri within the library
	* Installation of service\_utils should install evpoco as well
* Packaging of various modules to facilitate easy distribution and deployment.
* Distribution of evlua for download and usage


[overview]: ../doc/images/evlua_overview.png "Overview"

