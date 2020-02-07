# Docker compose

Dot `.` is used to refer to PWD.

```yaml
version: "3.1" # if no version is specificed then v1 is assumed. Recommend v2 minimum

services: # containers. same as docker run
    servicename: # a friendly name. this is also DNS name inside network
        image: # Optional if you use build:
        command: # Optional, replace the default CMD specified by the image
        environment: # Optional, same as -e in docker run
        volumes: # Optional, same as -v in docker run
        depends_on:
    servicename2:

volumes: # Optional, same as docker volume create

networks: # Optional, same as docker network create
```