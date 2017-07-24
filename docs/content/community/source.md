---
title: Source
menu:
  main:
    parent: community
    weight: 3
---

## LoRa Gateway Config source

Source-code can be found at [https://github.com/brocaar/lora-gateway-config](https://github.com/brocaar/lora-gateway-config).

### Building

#### With Docker

The easiest way to get started is by using the provided 
[docker-compose](https://docs.docker.com/compose/) environment. To start a bash
shell within the docker-compose environment, execute the following command from
the root of this project:

```bash
docker-compose run --rm gwconfig bash
```

#### Without Docker

It is possible to build LoRa Gateway Config without Docker. However this requires
to install a couple of dependencies (depending your platform, there might be
pre-compiled packages available):

##### Go

Make sure you have [Go](https://golang.org/) installed (1.7+) and that the LoRa
Gateway Config repository has been cloned to 
`$GOPATH/src/github.com/brocaar/lora-gateway-config`.

##### Development utilities

Finally, install some utilities used for development by executing the
following commands:

```bash
go get github.com/golang/lint/golint
go get github.com/kisielk/errcheck
go get github.com/smartystreets/goconvey
go get golang.org/x/tools/cmd/stringer
```

#### Example commands

A few example commands that you can run:

```bash
# run the tests
make test

# compile
make build

# cross-compile for Linux ARM
GOOS=linux GOARCH=arm make build

# cross-compile for Windows AMD64
GOOS=windows BINEXT=.exe GOARCH=amd64 make build

# build the .tar.gz file for Linux ARM
GOOS=linux GOARCH=arm make package

# build the .tar.gz file for Windows AMD64
GOOS=windows BINEXT=.exe GOARCH=amd64 make package
```
