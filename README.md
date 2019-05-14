# Hello-World-Nginx

Basic Nginx Docker Setup for running a simple website on a Nginx Container on port 8080.

## Building Container

```bash
docker build -t gingco/hello-world-nginx .
```

## Running Container

Running

```bash
docker run --rm -d -p 8080:80 --name nginx gingco/hello-world-nginx
```

## Terminating Container

```bash
docker container rm -f nginx
```

## Deleting all Images

CAUTION: Deleting all currently unused Images from local machine:

```bash
docker rmi $(docker images -q)
```

Just deleting created and pulled images after terminating running container:

```bash
docker rmi nginx:alpine gingco/hello-world-nginx
```

## Combinations

### Setup

```bash
docker build -t gingco/hello-world-nginx . && docker run --rm -d -p 8080:80 --name nginx gingco/hello-world-nginx
```

### Teardown

```bash
docker container rm -f nginx && docker rmi -f nginx:alpine gingco/hello-world-nginx
```
