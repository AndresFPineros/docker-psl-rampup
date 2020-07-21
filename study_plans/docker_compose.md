# Orchestration with Docker-Compose

## Docker Networks: Communicating two containers

Before moving on to Docker Compose, let's play around with the Docker Networks.
When docker is installed in your machine, it creates virtual networks that allow your containers to talk to each other in an isolated manner. Containers that are located in the same network can talk to each other.

Check out this interactive tutorial: [Katacoda Networking Intro](https://www.katacoda.com/courses/docker/networking-intro)

In the tutorial you will:
- Create a Docker Network
- Create a Redis container attached to that network.
- Create a dummy Webserver provided by Catacoda and attach it to redis.

## What is docker-compose?

The purpose of Docker Compose is to facilitate the communiction adn orchestration of applications running inside Docker. It is a declarative way (a YMAL file) of defining how several applications must interact with each other.

Instead of running all those commands we just did with Katacoda, we would have this file describing everything. The file name should be `docker-compose.yml`:
```
version: "3.2"
services:
  redis:
    image: "redis:alpine"
    networks:
      - frontend_net
  webapp:
    image: "katacoda/redis-node-docker-example"
    ports:
      - 3000:3000
    networks:
      - frontend_net

networks:
  frontend_net:
```

And then we just run the command in the folder with the docker-compose.yml file:
```
docker-compose up
```

## Docker-compose concepts: serivcename, replicas, service and stacks.

## Importance of Docker-Compose in development environments.

## Docker-Compose vs Docker Swarm vs ECS vs Kubernetes.
