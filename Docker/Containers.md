# Containers

## Run

-   `docker container run <image_name> <command> <arguments>` - runs started container.
-   `docker container start` - start stopped container. Use `-ai` to run command.
-   `docker container stop <container_id>`.
-   `docker container ls`.
-   `docker container logs <container_id>`.
-   `docker container rm <container_id>`.
-   `docker image ls`.
-   `docker container exec <container> <command> <arguments>` - run command in created container. Use `-it` for running command.

### Options of run command

-   `--name`
-   `--publish <host_port>:<container_port>` or `-p`.
-   `--network <name>`.
-   `--detach` - run in background mode.
-   `--env` or `-e`.
-   `--rm` - automatically remove container after exit.

## Networks

-   `docker network ls` - list of networks.
-   `docker network inspect`.
-   `docker network create <network> --driver <driver>`. Default docker virtual network is `docker0` or `bridge`.
-   `docker network connect <network> <container>` - attach network to container.
-   `docker network disconnect <network> <container>`.
