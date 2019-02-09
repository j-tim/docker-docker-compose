# Jtim custom Gitlab CI build image with Docker and Docker-compose

## Supported tags and respective Dockerfile links

Latest version:
Docker version: 18.09.1 ce-git
Docker compose: 1.23.1

Since version `18.05.0-ce-git-compose-1.21.2` the Docker images run as non root!

* `18.09.1-ce-git-compose-1.23.1`, `18.09.1-ce-git`, `18.09.1`, `18`, `latest` [(18.09.1/ce/compose-1.23.1)](https://github.com/j-tim/docker-docker-compose/blob/master/18.09.1/ce/compose-1.23.1/Dockerfile)  

* `18.05.0-ce-git-compose-1.21.2`, `18.05.0-ce-git`, `18.05.0`, [(18.05.0/ce/compose-1.21.2)](https://github.com/j-tim/docker-docker-compose/blob/master/18.05.0/ce/compose-1.21.2/Dockerfile)

## Deprecated versions 

* `18.01.0-compose-1.18.0`, `18.01.0` [(18.01.0/ce/compose-1.18.0)](https://github.com/j-tim/docker-docker-compose/blob/master/18.01.0/ce/compose-1.18.0/Dockerfile)  
* `17.11-compose-1.17.1`, `17.11`, `17` [(17.11/ce/compose-1.17.1)](https://github.com/j-tim/docker-docker-compose/blob/master/17.11/ce/compose-1.17.1/Dockerfile)  
* `17.07-compose-1.16.1`, `17.07` [(17.07/ce/compose-1.16.1)](https://github.com/j-tim/docker-docker-compose/blob/master/17.07/ce/compose-1.16.1/Dockerfile)  
* `17.04-compose-1.12.0`, `17.04` [(17.04/ce/compose-1.12.0)](https://github.com/j-tim/docker-docker-compose/tree/master/17.04/ce/compose-1.12.0/Dockerfile)

## Pull the image 

```shell
docker pull jtim/docker-docker-compose
```

## How to use the Gitlab Build image

.gitlab-ci.yml

```
stages:
  - dockerize

docker-job:
  image: jtim/docker-docker-compose:18.09.1-ce-git-compose-1.23.1
  stage: dockerize
  services:
    - docker:dind
  script:
    - whoami
    - docker -v
    - docker-compose -v
```