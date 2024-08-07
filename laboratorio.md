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

# LABORATORIO 2

# Ejercicio 2

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

# Ejercicio 3

## [+] Building 12.8s (6/6) FINISHED                                                                                                                      docker:default
## => [internal] load build definition from dockerfile                                                                                                             0.1s
## => => transferring dockerfile: 137B                                                                                                                             0.0s
## => [internal] load metadata for docker.io/library/ubuntu:latest                                                                                                 0.0s
## => [internal] load .dockerignore                                                                                                                                0.1s
## => => transferring context: 2B                                                                                                                                  0.0s
## => CACHED [1/2] FROM docker.io/library/ubuntu:latest                                                                                                            0.0s
## => [2/2] RUN apt-get update && apt-get install -y nginx                                                                                                        11.4s
## => exporting to image                                                                                                                                           0.8s
## => => exporting layers                                                                                                                                          0.7s
## => => writing image sha256:34d356f620880c617aeb3fd2c3aec377e48dfe1c59779ac01252c63af0b7dea1                                                                     0.0s
## => => naming to docker.io/library/ubuntu-updated:latest 

# Ejercicio 4

### [+] Building 0.5s (6/6) FINISHED                                                                                                                       docker:default
### => [internal] load build definition from dockerfile                                                                                                             0.1s
### => => transferring dockerfile: 137B                                                                                                                             0.0s
### => [internal] load metadata for docker.io/library/ubuntu:latest                                                                                                 0.0s
### => [internal] load .dockerignore                                                                                                                                0.1s
### => => transferring context: 2B                                                                                                                                  0.0s
### => [1/2] FROM docker.io/library/ubuntu:latest                                                                                                                   0.0s
### => CACHED [2/2] RUN apt-get update && apt-get install -y nginx                                                                                                  0.0s
### => exporting to image                                                                                                                                           0.1s
### => => exporting layers                                                                                                                                          0.0s
### => => writing image sha256:34d356f620880c617aeb3fd2c3aec377e48dfe1c59779ac01252c63af0b7dea1                                                                     0.0s
### => => naming to docker.io/library/my-nginx:latest  

## docker run -d -p 80:80 my-nginx:latest
### 66c3fea3b615d21c26870fac7f39e87effab00a5b3c6c3ea10bd6e8f3f46c9a2

# Ejercicio 5
## docker build -t my-nginx:latest .

### [+] Building 0.7s (6/6) FINISHED                                                                                                                       docker:default
### => [internal] load build definition from dockerfile                                                                                                             0.1s
### => => transferring dockerfile: 148B                                                                                                                             0.0s
### => [internal] load metadata for docker.io/library/ubuntu:latest                                                                                                 0.0s
### => [internal] load .dockerignore                                                                                                                                0.1s
### => => transferring context: 2B                                                                                                                                  0.0s
### => [1/2] FROM docker.io/library/ubuntu:latest                                                                                                                   0.0s
### => CACHED [2/2] RUN apt-get update && apt-get install -y nginx                                                                                                  0.0s
### => exporting to image                                                                                                                                           0.1s
### => => exporting layers                                                                                                                                          0.0s
### => => writing image sha256:41e7b796d49b4af65290c8e7caf8e29e78ba7ce9789aab816497d7056e5ce71f                                                                     0.0s
### => => naming to docker.io/library/my-nginx:latest

# Tema 2
## Ejercicio 1
### docker build -t my-nginx-image .
#### [+] Building 6.5s (8/8) FINISHED                                                                                                                       docker:default
#### => [internal] load build definition from dockerfile                                                                                                             0.1s
#### => => transferring dockerfile: 95B                                                                                                                              0.0s
#### => [internal] load metadata for docker.io/library/nginx:latest                                                                                                  0.6s
#### => [auth] library/nginx:pull token for registry-1.docker.io                                                                                                     0.0s
#### => [internal] load .dockerignore                                                                                                                                0.1s
#### => => transferring context: 2B                                                                                                                                  0.0s
#### => [internal] load build context                                                                                                                                0.3s
#### => => transferring context: 31B                                                                                                                                 0.0s
#### => [1/2] FROM docker.io/library/nginx:latest@sha256:6af79ae5de407283dcea8b00d5c37ace95441fd58a8b1d2aa1ed93f5511bb18c                                            4.4s
#### => => resolve docker.io/library/nginx:latest@sha256:6af79ae5de407283dcea8b00d5c37ace95441fd58a8b1d2aa1ed93f5511bb18c                                            0.2s
#### => => sha256:6af79ae5de407283dcea8b00d5c37ace95441fd58a8b1d2aa1ed93f5511bb18c 10.27kB / 10.27kB                                                                 0.0s
#### => => sha256:a72860cb95fd59e9c696c66441c64f18e66915fa26b249911e83c3854477ed9a 7.30kB / 7.30kB                                                                   0.0s
#### => => sha256:baa881b012a49e3c2cd6ab9d80f9fcd2962a98af8ede947d0ef930a427b28afc 2.29kB / 2.29kB                                                                   0.0s
#### => => sha256:8fe9a55eb80f3167f7b3a9c39f90b9eacf833841e5a9f8d60c51f4d2400154a3 41.83MB / 41.83MB                                                                 0.6s
#### => => sha256:045037a63be803c1d446a5239439580a49cd8a8682a5addf4f03b2c1638948a4 627B / 627B                                                                       0.2s
#### => => sha256:7111b42b4bfa1b5273abcc4b138983f48f9cb96bb3f896a6cb36af3dade80383 955B / 955B                                                                       0.3s
#### => => sha256:3dfc528a4df9e1be9b2817271a35cef87f001e699e5b8ef944640b383ca27e1f 394B / 394B                                                                       0.4s
#### => => sha256:9e891cdb453be97c53e1ddbe4b955ee71099f18f16e68e7010c33662aaa944bf 1.21kB / 1.21kB                                                                   0.7s
#### => => sha256:0f11e17345c583a30e9cc89b80b1423b7b52b0e36cda9a6dc5de587ecf6ed54c 1.40kB / 1.40kB                                                                   0.7s
#### => => extracting sha256:8fe9a55eb80f3167f7b3a9c39f90b9eacf833841e5a9f8d60c51f4d2400154a3                                                                        1.2s
#### => => extracting sha256:045037a63be803c1d446a5239439580a49cd8a8682a5addf4f03b2c1638948a4                                                                        0.0s
#### => => extracting sha256:7111b42b4bfa1b5273abcc4b138983f48f9cb96bb3f896a6cb36af3dade80383                                                                        0.0s
#### => => extracting sha256:3dfc528a4df9e1be9b2817271a35cef87f001e699e5b8ef944640b383ca27e1f                                                                        0.0s
#### => => extracting sha256:9e891cdb453be97c53e1ddbe4b955ee71099f18f16e68e7010c33662aaa944bf                                                                        0.0s
#### => => extracting sha256:0f11e17345c583a30e9cc89b80b1423b7b52b0e36cda9a6dc5de587ecf6ed54c                                                                        0.0s
#### => [2/2] COPY index.html /usr/share/nginx/html/                                                                                                                 0.2s
#### => exporting to image                                                                                                                                           0.7s
#### => => exporting layers                                                                                                                                          0.5s
#### => => writing image sha256:ed8556c68da508d34bec207d2a14a7d8bb3b31b1f8c5532e072bbd02fd97e06d                                                                     0.0s
#### => => naming to docker.io/library/my-nginx-image    

### docker run -d -p 8080:80 my-nginx-image
#### de09dba6ee7b9ad9dd6b3b54e5082b17e12bf20d596a6d8c706f7ce0999a3553

## Ejercicio 2
### docker build -t my-ubuntu-image .
#### [+] Building 2.4s (8/8) FINISHED                                                                                                                       docker:default
#### => [internal] load build definition from dockerfile                                                                                                             0.1s
#### => => transferring dockerfile: 89B                                                                                                                              0.0s
#### => [internal] load metadata for docker.io/library/ubuntu:latest                                                                                                 0.0s
#### => [internal] load .dockerignore                                                                                                                                0.1s
#### => => transferring context: 2B                                                                                                                                  0.0s
#### => CACHED [1/3] FROM docker.io/library/ubuntu:latest                                                                                                            0.0s
#### => [internal] load build context                                                                                                                                0.1s
#### => => transferring context: 31B                                                                                                                                 0.0s
#### => [2/3] WORKDIR /app                                                                                                                                           0.2s
#### => [3/3] COPY myfile.txt .                                                                                                                                      0.3s
#### => exporting to image                                                                                                                                           1.4s
#### => => exporting layers                                                                                                                                          1.2s
#### => => writing image sha256:59cc441f9462f7f30b066a8e42b80da74d33a21a87b561d5be1f103d29aa5e24                                                                     0.0s
#### => => naming to docker.io/library/my-ubuntu-image   








