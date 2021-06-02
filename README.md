# Docker NPM Registry & Cache

A local NPM registry hosted in Docker, using [Verdaccio](https://verdaccio.org).

Establishes a local registry where private packages can be published under whatever [scope](https://docs.npmjs.com/cli/v7/using-npm/scope)
you like. Useful for situations involving private dependencies which are being developed in tandem, but there isn't
a private NPM server set up for your organization.

## Usage
```bash
# start in the background
docker compose up -d
# view logs
docker compose logs
# log in (simultaneously creates user)
npm login --registry http://localhost:4873
# set default registry to local cache
npm config set registry http://localhost:4873
```

### Web Interface
Verdaccio exposes a web interface from which packages can be explored. By default, it's available at http://localhost:4873.

## Storage
A Docker volume is created for package storage. This includes storage of all packages that are retrieved from the main NPM registry.