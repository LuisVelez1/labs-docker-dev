# Ejercicio 1
## docker pull ubuntu
### Using default tag: latest
### latest: Pulling from library/ubuntu
### 9c704ecd0c69: Pull complete 
### Digest: sha256:2e863c44b718727c860746568e1d54afd13b2fa71b160f5cd9058fc436217b30
### Status: Downloaded newer image for ubuntu:latest
### docker.io/library/ubuntu:latest 

### docker pull python:3.9

### 3.9: Pulling from library/python
### ca4e5d672725: Pull complete 
### 30b93c12a9c9: Pull complete 
### 10d643a5fa82: Pull complete 
### d6dc1019d793: Pull complete 
### c387064957b7: Pull complete 
### 26766ebde481: Pull complete 
### 8a42d17fd0e2: Pull complete 
### 79eda865cc8a: Pull complete 
### Digest: sha256:fea84f3a3b72c41efe7fc3b07ae209c6856b852b942c05fa88b747b74f70e711
### Status: Downloaded newer image for python:3.9
### docker.io/library/python:3.9 

# Ejercicio 2
## docker run -it ubuntu bash
### root@9d4032dbb03d:/#

## docker run -d -p 8000:80 httpd
### Unable to find image 'httpd:latest' locally
### latest: Pulling from library/httpd
### efc2b5ad9eec: Pull complete 
### fce1785eb819: Pull complete 
### 4f4fb700ef54: Pull complete 
### f214daa0692f: Pull complete 
### 05383fd8b2b3: Pull complete 
### 88ad12232aa1: Pull complete 
### Digest: sha256:932ac36fabe1d2103ed3edbe66224ed2afe0041b317bcdb6f5d9be63594f0030
### Status: Downloaded newer image for httpd:latest
### 3a496442147ca1656c2f0cc12a23dee7a9dcd882f89fb750befb17da6b660558

# Ejercicio 3
## docker ps -a

### CONTAINER ID   IMAGE     COMMAND              CREATED          STATUS                       PORTS                                   NAMES
### 9d4032dbb03d   ubuntu    "bash"               4 minutes ago    Exited (129) 4 minutes ago                                           kind_solomon
### 3a496442147c   httpd     "httpd-foreground"   7 minutes ago    Up 7 minutes                 0.0.0.0:8000->80/tcp, :::8000->80/tcp   awesome_stonebraker
### 4716214ba780   ubuntu    "bash"               11 minutes ago   Exited (129) 8 minutes ago                                           pedantic_einstein

## docker rm 9d4032dbb03d
### }9d4032dbb03d

## docker container prune
### WARNING! This will remove all stopped containers.
### Are you sure you want to continue? [y/N] y
### Deleted Containers:
### 4716214ba7805eb62bf386246998183f6d5ac32a46e2df605de3ecffc64a22d9
### Total reclaimed space: 10B

## docker build -t ubuntu-updated:latest .
### [+] Building 10.0s (6/6) FINISHED                                                                                                                      docker:default
### => [internal] load build definition from dockerfile                                                                                                             0.1s
### => => transferring dockerfile: 96B                                                                                                                              0.0s
### => [internal] load metadata for docker.io/library/ubuntu:latest                                                                                                 0.0s
### => [internal] load .dockerignore                                                                                                                                0.2s
### => => transferring context: 2B                                                                                                                                  0.0s
### => [1/2] FROM docker.io/library/ubuntu:latest                                                                                                                   0.1s
### => [2/2] RUN apt-get update && apt-get upgrade -y                                                                                                               8.6s
### => exporting to image                                                                                                                                           0.7s
### => => exporting layers                                                                                                                                          0.5s
### => => writing image sha256:45634d859b3edba7ca26564b93249bb5db396f6570c6e9e4427204d29c2115bd                                                                     0.0s
### => => naming to docker.io/library/ubuntu-updated:latest 


