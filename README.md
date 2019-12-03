# (WIP) postgres-plv8 (WIP)

Docker images for running [plv8](https://github.com/plv8/plv8) 2.x on Postgres 9 (and later).
Based on the [official Postgres image](http://registry.hub.docker.com/_/postgres/).

[![smaktacular/postgres-plv8][docker-pulls-image]][docker-hub-url] [![smaktacular/postgres-plv8][docker-stars-image]][docker-hub-url] 
[![smaktacular/postgres-plv8][docker-size-image]][docker-hub-url] [![smaktacular/postgres-plv8][docker-layers-image]][docker-hub-url]

## Build status

![](https://github.com/smaktacular/docker-postgres-plv8/workflows/BuildDockerImage/badge.svg)

## Tags

- `121-2312`, `latest` ([121-2312/Dockerfile](https://github.com/smaktacular/docker-postgres-plv8/blob/master/121-2312/Dockerfile))

## Usage

### How to use this image

This image behaves exactly like the official Postgres image with the only difference being the inclusion of the plv8 extension.

```sh
$ docker run -d --name postgres smaktacular/postgres-plv8:121-2312
$ docker exec -it postgres bash -c 'psql -U postgres -c "CREATE EXTENSION plv8; SELECT extversion FROM pg_extension WHERE extname = ''plv8'';"'
```

You should see the version of the plv8 extension installed.

You can optionally create a service using `docker-compose`:

```yml
postgres:
  image: smaktacular/postgres-plv8:121-2312
```

## Flavors:

### `smaktacular/postgres-plv8:latest`

Points to the latest release available of Postgres stable with compatible plv8 installed. Occasionally pre-release versions will be included.

### `smaktacular/postgres-plv8:<postgresVersion>-<plv8Version>`

Points to the latest release available of Postgres `<postgresVersion>` with the latest release available of plv8 `<plv8Version>` installed.

## Supported Docker versions

This image is supported on Docker version 19.03, with support for older versions provided on a best-effort basis.

## License

MIT

[docker-hub-url]: https://hub.docker.com/r/smaktacular/postgres-plv8/
[docker-pulls-image]: https://img.shields.io/docker/pulls/smaktacular/postgres-plv8.svg?style=flat-square
[docker-stars-image]: https://img.shields.io/docker/stars/smaktacular/postgres-plv8.svg?style=flat-square
