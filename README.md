# malice-pe

[![License](http://img.shields.io/:license-mit-blue.svg)](http://doge.mit-license.org)
[![Docker Stars](https://img.shields.io/docker/stars/malice/pe.svg)][hub]
[![Docker Pulls](https://img.shields.io/docker/pulls/malice/pe.svg)][hub]
[![Image Size](https://img.shields.io/imagelayers/image-size/malice/pe/latest.svg)](https://imagelayers.io/?images=malice/pe:latest)
[![Image Layers](https://img.shields.io/imagelayers/layers/malice/pe/latest.svg)](https://imagelayers.io/?images=malice/pe:latest)

Malice PExecutable Plugin

This repository contains a **Dockerfile** of **malice/pe** for [Docker](https://www.docker.io/)'s [trusted build](https://index.docker.io/u/malice/pe/) published to the public [DockerHub](https://index.docker.io/).

### Dependencies

* [gliderlabs/alpine:3.3](https://index.docker.io/_/gliderlabs/alpine/)


### Installation

1. Install [Docker](https://www.docker.io/).
2. Download [trusted build](https://hub.docker.com/r/malice/pe/) from public [DockerHub](https://hub.docker.com): `docker pull malice/pe`

### Usage

    docker run --rm malice/pe FILE

```bash

```

This will output to stdout and POST to malice results API webhook endpoint.

### Sample Output **sandbox** JSON:
```json
{
  "pe": {
  }
}
```
### Sample Output **sandbox** (Markdown Table):
---
#### pe

---
### To Run on OSX
 - Install [Homebrew](http://brew.sh)

```bash
$ brew install caskroom/cask/brew-cask
$ brew cask install virtualbox
$ brew install docker
$ brew install docker-machine
$ docker-machine create --driver virtualbox malice
$ eval $(docker-machine env malice)
```

### Documentation

### Issues

Find a bug? Want more features? Find something missing in the documentation? Let me know! Please don't hesitate to [file an issue](https://github.com/maliceio/malice-av/issues/new) and I'll get right on it.

### Credits

### License
MIT Copyright (c) 2016 **blacktop**

[hub]: https://hub.docker.com/r/malice/pe/
