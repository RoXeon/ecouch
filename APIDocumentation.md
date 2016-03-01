# Module ecouch #

eCouch is an [Erlang](http://www.erlang.org/) application that provides access to [CouchDb](http://couchdb.org/) servers.

Copyright © 2008 Vitor Rodrigues

Version: 0.1

Behaviours: application.

Authors: Vitor Rodrigues (vitor tarpipe (dot) com).

## Characteristics ##

  * eCouch is an application that provides an API to a [CouchDb](http://couchdb.org/) server
  * It uses the [rfc4627](http://www.lshift.net/blog/2007/02/17/json-and-json-rpc-for-erlang) module from [LShift](http://www.lshift.net/)
  * eCouch design was inspired by the article [Building a Non-blocking TCP server using OTP principles](http://www.trapexit.org/Building_a_Non-blocking_TCP_server_using_OTP_principles)
  * It assumes that [inets](http://www.erlang.org/doc/apps/inets/index.html) application is running

## Data Types ##

**array()** = [val()]

**host()** = string()

**json()** = obj() | array() | num() | str() | true | false | null

**key()** = str() | atom()

**num()** = int() | float()

**obj()** = {obj, [{key(), val()}]}

**startargs()** = {host(), tcp\_port()}

**str()** = bin()

**tcp\_port()** = int()

**val()** = obj() | array() | num() | str() | true | false | null

## Function Details ##
### db\_create/1 ###

db\_create(DatabaseName::string()) -> ok | {error, Reason::term()}

Create a database
### db\_delete/1 ###

db\_delete(DatabaseName::string()) -> ok | {error, Reason::term()}

Delete a database
### db\_info/1 ###

db\_info(DatabaseName::string()) -> {ok, Info::json()} | {error, Reason::term()}

Database info
### db\_list/0 ###

db\_list() -> ok | {error, Reason::term()}

List databases
### doc\_create/2 ###

doc\_create(DatabaseName::string(), Doc::json()) -> {ok, Response::json()} | {error, Reason::term()}

Create document
### doc\_create/3 ###

doc\_create(DatabaseName::string(), DocName::string(), Doc::json()) -> {ok, Response::json()} | {error, Reason::term()}

Create a named document
### doc\_delete/3 ###

doc\_delete(DatabaseName::string(), DocName::string(), Rev::string()) -> {ok, Response::json()} | {error, Reason::term()}

Delete document
### doc\_get/2 ###

doc\_get(DatabaseName::string(), DocName::string) -> {ok, Response::json()} | {error, Reason::term()}

Get document
### doc\_get/3 ###

doc\_get(DatabaseName::string(), DocName::string(), Options::options()) -> {ok, Response::json()} | {error, Reason::term()}

Get document
### doc\_get\_all/1 ###

doc\_get\_all(DatabaseName::string()) -> {ok, Response::json()} | {error, Reason::term()}

Get all documents
### doc\_get\_all/2 ###

doc\_get\_all(DatabaseName::string(), Options::options()) -> {ok, Response::json()} | {error, Reason::term()}

Get all documents
### doc\_update/3 ###

doc\_update(DatabaseName::string(), DocName::string(), Doc::json()) -> {ok, Response::json()} | {error, Reason::term()}

Update document
### start/2 ###

start(Type::_Type, StartArgs::startargs()) -> {ok, Pid} | {ok, Pid, State} | {error, Reason}_

This function is called whenever an application is started using application:start/1,2, and should start the processes of the application. If the application is structured according to the OTP design principles as a supervision tree, this means starting the top supervisor of the tree.
### stop/1 ###

stop(State) -> void()

This function is called whenever an application has stopped. It is intended to be the opposite of Module:start/2 and should do any necessary cleaning up. The return value is ignored.
### view\_adhoc/2 ###

view\_adhoc(DatabaseName::string(), Fun::json()) -> {ok, Response::json()} | {error, Reason::term()}

Access an adhoc view
### view\_adhoc/3 ###

view\_adhoc(DatabaseName::string(), Fun::json(), Options::options()) -> {ok, Response::json} | {error, Reason::term()}

Access an adhoc view