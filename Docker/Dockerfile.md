# Dockerfile

## Syntax

-   `FROM` - base image.
-   `EXPOSE` - port that is listened by container.
-   `CMD`.

## Running

1. Build image with `docker image build -t <tag> <dockerfile_location>`. Append `-f` option to set filename other than Dockerfile.
2. Run container.

## Tags

Tags points to specific commit.

Commands

-   `docker tag <image>:<tag> <target_image>:<tag>`
-   `docker push <image>`
