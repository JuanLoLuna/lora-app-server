---
title: Source
menu:
    main:
        parent: community
        weight: 3
---

# LoRa App Server source

Source-code can be found at [https://github.com/brocaar/lora-app-server](https://github.com/brocaar/lora-app-server).

### Building

#### With Docker

The easiest way to get started is by using the provided 
[docker-compose](https://docs.docker.com/compose/) environment. To start a bash
shell within the docker-compose environment, execute the following command from
the root of this project:

```bash
docker-compose run --rm appserver bash
```

### Without Docker

It is possible to build LoRa App Server without Docker. However this requires
to install a couple of dependencies (depending your platform, there might be
pre-compiled packages available):

#### Go

Make sure you have [Go](https://golang.org/) installed (1.10+) and that the LoRa
App Server repository has been cloned to 
`$GOPATH/src/github.com/brocaar/lora-app-server`.

#### Node.js

Make sure you have a recent version of Node.js installed, as Node.js is used
to compile the front-end code.

#### Go protocol buffer support

Install the C++ implementation of protocol buffers and Go support by following
the GO support for Protocol Buffers [installation instructions](https://github.com/golang/protobuf).

### Example commands

A few example commands that you can run:

```bash
# install all requirements
make requirements ui-requirements

# cleanup workspace
make clean

# generate the API source-code (run this after changing the .proto files)
make api

# run the tests
make test

# compile (this will also compile the ui and generate the static files)
make build

# compile snapshot builds for supported architectures (this will also compile the ui and generate the static files)
make build-snapshot
```
