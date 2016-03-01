# Description #

eCouch is an [Erlang](http://www.erlang.org/) application that provides access to [CouchDb](http://couchdb.org/) servers.

## Characteristics ##

  * eCouch is an application that provides an API to a [CouchDb](http://couchdb.org/) server
  * It uses the [rfc4627](http://www.lshift.net/blog/2007/02/17/json-and-json-rpc-for-erlang) module from [LShift](http://www.lshift.net/)
  * eCouch design was inspired by the article [Building a Non-blocking TCP server using OTP principles](http://www.trapexit.org/Building_a_Non-blocking_TCP_server_using_OTP_principles)
  * It assumes that [inets](http://www.erlang.org/doc/apps/inets/index.html) application is running

# Features #

  * Follows all the OTP design principles
  * Can run stand-alone with its own supervision tree or be included inside an existing supervision tree
  * Guarantees synchronism between calls and their responses

# Documentation #

  * [APIDocumentation](APIDocumentation.md)

# Copyright #

Copyright © 2008 Vitor Rodrigues <vitor tarpipe (dot) com>