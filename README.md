![License MIT](https://img.shields.io/badge/license-MIT-blue.svg) [![](https://img.shields.io/docker/pulls/andrejkosyak/docker-openstack-tools.svg)](https://hub.docker.com/r/andrejkosyak/docker-openstack-tools 'DockerHub') 

# Openstack tools image

A minimalistic alpine-based docker image with [Openstack](https://www.openstack.org/) client tools.

## What's included

There following CLI apps installed and available in `$PATH`:

* [Openstack client](https://github.com/openstack/python-openstackclient)
* [Swift client](https://github.com/openstack/python-swiftclient)
* [Heat client](https://github.com/openstack/python-heatclient)

## Example using swift-client

Upload a file to swift-storage

```
docker run --rm \
  -e OS_PROJECT_ID=### \
  -e OS_USERNAME=### \
  -e OS_PASSWORD=### \
  -e OS_USER_DOMAIN_NAME=### \
  -e OS_AUTH_URL=### \
  -v "/data:/data" \
  andrejkosyak/docker-openstack-tools \
  sh -c 'cd /data/ && swift upload my-backup-storage backup.zip'
```

## Docs

Managing a server:
https://docs.openstack.org/python-openstackclient/latest/cli/command-objects/server.html
Managing a stack:
https://docs.openstack.org/heat/latest/getting_started/create_a_stack.html

## Want to contribute?

Just create an issue :tada: