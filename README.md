# Jtim custom Gitlab CI build image with Docker and Docker-compose

Gitlab CI Docker build image running as non root user.

## Supported tags and respective Dockerfile links

Latest version:
Docker version: 18.09.6 (with git)
Docker compose: 1.24.0

* `18.09.6-git-compose-1.24.0`, `18.09.6-git`, `18.09.6`, `18`, `latest` [(18.09.6/compose-1.24.0)](https://github.com/j-tim/docker-docker-compose/blob/master/18.x/18.09.6/compose-1.24.0/Dockerfile) 

* `18.09.3-git-compose-1.23.2`, `18.09.3-git`, `18.09.3`, [(18.09.3/compose-1.23.2)](https://github.com/j-tim/docker-docker-compose/blob/master/18.x/18.09.3/compose-1.23.2/Dockerfile)  

* `18.09.1-ce-git-compose-1.23.1`, `18.09.1-ce-git`, `18.09.1`, [(18.09.1/ce/compose-1.23.1)](https://github.com/j-tim/docker-docker-compose/blob/master/18.x/18.09.1/ce/compose-1.23.1/Dockerfile)  

## Note

Since version `18.05.0-ce-git-compose-1.21.2` the Docker images run as non root!

## Deprecated versions 

* `18.05.0-ce-git-compose-1.21.2`, `18.05.0-ce-git`, `18.05.0`, [(18.05.0/ce/compose-1.21.2)](https://github.com/j-tim/docker-docker-compose/blob/master/18.x/18.05.0/ce/compose-1.21.2/Dockerfile)
* `18.01.0-compose-1.18.0`, `18.01.0` [(18.01.0/ce/compose-1.18.0)](https://github.com/j-tim/docker-docker-compose/blob/master/18.x/18.01.0/ce/compose-1.18.0/Dockerfile)  
* `17.11-compose-1.17.1`, `17.11`, `17` [(17.11/ce/compose-1.17.1)](https://github.com/j-tim/docker-docker-compose/blob/master/17.x/17.11/ce/compose-1.17.1/Dockerfile)  
* `17.07-compose-1.16.1`, `17.07` [(17.07/ce/compose-1.16.1)](https://github.com/j-tim/docker-docker-compose/blob/master/17.x/17.07/ce/compose-1.16.1/Dockerfile)  
* `17.04-compose-1.12.0`, `17.04` [(17.04/ce/compose-1.12.0)](https://github.com/j-tim/docker-docker-compose/tree/master/17.x/17.04/ce/compose-1.12.0/Dockerfile)

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
  image: jtim/docker-docker-compose:18.09.6-git-compose-1.24.0
  stage: dockerize
  services:
    - docker:dind
  script:
    - whoami
    - docker -v
    - docker-compose -v
    - git version
```

## Related Docker images

In case you need Docker and docker-compose in combination with Java (OpenJdk) 8 or 11 (AdoptOpenJdk) see: 

* Docker images: [https://hub.docker.com/r/jtim/docker-docker-compose-jdk](https://hub.docker.com/r/jtim/docker-docker-compose-jdk)
* Source code: [https://github.com/j-tim/docker-docker-compose-jdk](https://github.com/j-tim/docker-docker-compose-jdk)

Including also Maven into the mix? use:

* Docker images: [https://hub.docker.com/r/jtim/docker-docker-compose-jdk-mvn](https://hub.docker.com/r/jtim/docker-docker-compose-jdk-mvn)
* Source code: [https://github.com/j-tim/docker-docker-compose-jdk-mvn](https://github.com/j-tim/docker-docker-compose-jdk-mvn)

