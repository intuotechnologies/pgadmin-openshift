# PgAdmin 4 Docker Container for OpenShift

This repository contains a Docker container for running PgAdmin 4, optimized for deployment on OpenShift without requiring root access. The container runs as an unprivileged user (`pgadmin`) with `uid:gid` `1000:50`, chosen for compatibility with Docker Toolbox and to facilitate bind-mounting a local directory inside the container for persistent storage.

## Background

This project is based on the work by [thaJeztah](https://github.com/thaJeztah/pgadmin4-docker), updated with the latest versions of Python and PgAdmin to ensure compatibility and security.

## Features

- Optimized for OpenShift: Run as a non-root container.
- Persistent storage: Support for bind-mounting local directories.
- Updated dependencies: Uses the latest versions of Python and PgAdmin.

## Getting Started

To use this container, you will need Docker installed on your system. For OpenShift deployment, ensure you have the appropriate permissions to deploy non-root containers.

### Building the Image

```
docker build -t your-tag-name .
```

### Running the Container
```
docker run -d -p 80:80 -v /your/local/directory:/var/lib/pgadmin your-tag-name
```
This command starts PgAdmin accessible on port 80 and uses a local directory for persistent storage.
