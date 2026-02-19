# docker-postgis

**🐳 [Docker](https://www.docker.com) container for running a [PostgreSQL](https://www.postgresql.org) server with [PostGIS](https://postgis.net) extensions installed.**

[![Build](https://img.shields.io/github/actions/workflow/status/CargoSense/docker-postgis/publish.yml?logo=github&style=for-the-badge)](https://github.com/CargoSense/docker-postgis/actions/workflows/publish.yml)

The container images published by this repository are built using the [PostGIS project's official Docker images repository](https://github.com/postgis/docker-postgis). The images here are a subset of the official team's Alpine Linux-based Docker images and are built for `linux/amd64` and `linux/arm64` platforms. Refer to the official project's repository if you're looking for a wider selection of operating systems and PostgreSQL/PostGIS version combinations.

## Usage

You may be run this container directly using the [`docker run`](https://docs.docker.com/engine/containers/run/) command from the root of your project:

```sh
docker run --rm -it --env POSTGRES_PASSWORD=postgres ghcr.io/cargosense/postgis:18-3.6-alpine
```

Alternatively, you may configure this container to run as part of a [Docker Compose](https://docs.docker.com/reference/compose-file/)-driven set of services:

```yaml
services:
  app:
    # Your application's configuration here.
  postgis:
    image: ghcr.io/cargosense/postgis:18-3.6-alpine
    environment:
      POSTGRES_PASSWORD: postgres
    volumes:
      - "pg-data:/var/lib/postgresql/data"

volumes:
  pg-data:
```

## License

docker-postgis is freely available under the [MIT License](https://opensource.org/licenses/MIT).
