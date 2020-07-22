# Orchestration with Docker-Compose

## Docker Networks: Communicating two containers

Before moving on to Docker Compose, let's play around with the Docker Networks.
When docker is installed in your machine, it creates virtual networks that allow your containers to talk to each other in an isolated manner. Containers that are located in the same network can talk to each other.

Check out this interactive tutorial: [Katacoda Networking Intro](https://www.katacoda.com/courses/docker/networking-intro)

In the tutorial you will:
- Create a Docker Network
- Create a Redis container attached to that network.
- Create a dummy Webserver provided by Catacoda and attach it to redis.

*Questions you should figure out:*
- What is the main purpose of a Docker network?
- What command is used to create a network and attach containers to it?

## What is docker-compose?

Containers can definetely be used by themselves, but because of their scalability and their relation with microservices, it is very common to seek for orchestration solutions to manage multiple applications at once. This is where our first and most simple orchestrator comes in play: Docker Compose.

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
Several commands were reduced to a single file and a single command. Pretty awesome.

*Questions you should figure out:*

- What the difference between `docker-compose up` and `docker-compose up -d`?
- What is the purpose of the `version` field in a docker-compose file.
- What's the difference between the `image` and the `build` field in a docker-compose service?
- How can I pass environment variables to a service to configure it?

## Docker-Compose vs Docker Swarm vs ECS vs Kubernetes.

As we said before, Docker Compose is a very basic orchestrator but how does it compare to other orchestrators?

Check this link to get a general sense: [Orchestrators](https://stackoverflow.com/questions/47536536/whats-the-difference-between-docker-compose-and-kubernetes)

*Questions you should figure out:*

- Would you use Docker Compose in a production application? Why or why not?
- Is Kubernetes better than Docker Compose?
- What's the main difference between Docker Swarm and Docker Compose?
- When would you use Docker Compose over Kubernetes?
- When would you use Kubernetes over Docker Compose.