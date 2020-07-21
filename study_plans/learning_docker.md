# Learning Docker

## Docker containers?
### What is a Container?
Docker is a tool that let's you package and deploy your applications in any machine that has the Docker Daemon.

You can package anything: Mysql databases, Redis Cache, Java applications, Go applications, DotnetCore applications. You name it.

Let's download a Mysql Docker image with Mysql version 8:
```
docker pull mysql:8
```
Why did I say "Docker image" instead of "Docker container"? Docker images are the artifacts or executables, when they are executed they become "Docker containers".

Go ahead and run a Mysql image to create the container:
```
docker run -d -p 3309:3306 --name mysqltest mysql:8
```
That's it, now you have a Mysql application running in your machine. You can connect to `localhost:3309` with MySQL workbench or any other tool to test it.
You can check the current docker containers running in your machine:
```
docker ps -a
```
Go ahead and remove the container:
```
docker rm -f mysqltest
```
It is gone! Why were you able to run MySQL without installing anything related to MySQL like you used to? Because all the system dependencies and the application binaries of Mysql were packed in the docker image. Your only dependency now is Docker!

Do you want to get rid of that Mysql Docker image to free up some disk space?
```
docker rmi mysql:8
```

### Difference between Docker Containers and Virtual Machines
Before containers, Virtual Machines were the main tool to run isolated processes inside a server or host. It is important to understand the main differences between these two technologies because each has pros and cons and specific use cases.

- [Azure Documentation on the topic](https://docs.microsoft.com/en-us/virtualization/windowscontainers/about/containers-vs-vm)
- [Phoenixap](https://phoenixnap.com/kb/containers-vs-vms)
- [Black Blaze](https://www.backblaze.com/blog/vm-vs-containers/)

*Questions you should figure out:*

- What are some advantages of Containers over Virtual Machines?
- What are some advantages of Virtual Machines over Containers?
- Why are containers lighter than Virtual Machines?
- Why are containers faster to start than Virtual Machines?
- Why are Virtual Machines more secure than containers?
- Are containers better than Virtual Machines?

## The Dockerfile

- [Static webpage with Nginx](https://www.katacoda.com/courses/docker/create-nginx-static-web-server)

*Questions you should figure out:*
- What is a Dockerfile? What is it used for?
- How are docker images created? Which command?
- What is the `docker search` command for?
- What is the `docker run` command for?
- What is the `docker ps` command for?


## What is the Docker Engine?

You have been running commands using `docker` but how does it actually work? In a few words: The `docker` command (CLI) is a client that sends HTTP requests to an API called the `docker-daemon`. The `docker-daemon` then calls to a component called `containerd` which operates the containers (create, delete, modify...)

Check these sources:
- [What is the Docker Engine?](https://docs.docker.com/engine/)
- [Docker Architecture](https://www.katacoda.com/courses/docker/create-nginx-static-web-server): In here they show that the daemon receives the commands from the CLI and then creates the containers.

*Questions you should figure out:*
- If the docker daemon is an HTTP API, does it mean that there are other clients besides the command-line tool? Things like SDKs?
- If the docker daemon is an HTTP API, does it mean I can call a remote docker-daemon using the client from my machine?

## Debugging a running container
Docker offers some debugging mechanisms that can be useful for debugging you container(s).
- Research how to read the logs of a container
- Research how to connect to a container and execute commands inside it. (docker exec command)
- Research how to debug code running inside a docker container on execution time (you can follow the attached guide)

## Persisting Data with Containers
all files created inside a container are stored on a writable container layer. This means that the  data doesn’t persist when that container
no longer exists, and it can be difficult to get the data out of the container if another process needs it. In many cases we want to keep this data for
later analyze it or let another process to use it. Docker offers 2 main  mechanisms for allowing data persistance: volumes and bind mounts. If you’re running Docker on Linux you can also use a tmpfs mount. If you’re running Docker on Windows you can also use a named pipe.

Please Check: 
https://docs.docker.com/storage/
for a general overview on docker storage.

go deeper on volumes : https://docs.docker.com/storage/volumes/ 
go deeper on bind mounts: https://docs.docker.com/storage/bind-mounts/
it is recommended to follow the examples on both pages.

*Questions you should figure out:*
- what is a volmue? what is a bind mount?
- what are the differences between a volume and a mount bind?
- what are some advantages and good use cases for docker volumes and bind mounts? 
- how to create a volume and a bind mount? 
