# Introduction

Tinkering with sidecar-proxy concept.  Using [envoy](https://www.envoyproxy.io/).

# Quickstart

## Build/start the 'real' service

Install [sbt](https://www.scala-sbt.org/).  Then:

```sh
cd a-server
sbt run
```

Make sure it's running:

```sh
curl localhost:8080/hello
```

## Build/start the proxy

```sh
cd proxy
docker build -t envoy:v1 .
docker run --rm --network host envoy:v1
```

## Hit the service via the proxy

```sh
curl localhost:10000/svc/1/hello
```

### Admin console

Admin console runs [here](http://localhost:8001).




