# nginx-demo
Demonstration of the simplicity of nginx server

nginx is a reverse-proxy; which means any incoming requests are being mapped to relevant internal microservices within the system.

![Overview image](overview.png?raw=true "overview")

## What is happening here:

In a docker environment, we usually do need to have a centralized place to manage incoming traffic. It's typically a nginx instance.
We try to simulate a scenario that demonstrate calling a service going through a nginx reverse-proxy server.
1. Hotel service microservice
2. nginx server which can route the incoming traffic that has the request path `/hotel-service`

Docker compose file is used to bind 2 docker instances into one docker network(`my-real-docker-network`).

## How to run

1. clone this repository
2. move inside the cloned repository(`cd nginx-demo`)
3. build hotel service docker image(`cd hotel-service | docker build -t hotel-service .`)
4. build nginx docker image(`cd nginx | docker build -t nginx-master .`)
5. create the docker network manually(`docker network create my-real-docker-network`)
5. start the docker compose service which will run the 2 containers (`docker-compose up`)
