# Getting Started

## Windows Installation

To install Docker in Windows, you can check the following sources:
- [Pluralsight Guide](https://app.pluralsight.com/course-player?clipId=fc64c687-d09d-41a3-a6e2-f64429ca32ec)
- [Official Docs](https://docs.docker.com/docker-for-windows/install/#install-docker-desktop-on-windows)

If you're following the official docs, please DO NOT switch to Windows containers. We're using Linux Containers in Windows, which is different. The reason why Linux Containers can run in Windows is because the installer creates a small Linux virtual machine inside Windows to run the containers.

Windows users can use Powershell to execute `docker` commands.

## Linux Installation
  - [Pluralsight Guide](https://app.pluralsight.com/course-player?clipId=6ac70df0-eea9-418c-be1a-7a1dfc040b29)
  - [Official Docs - Ubuntu](https://docs.docker.com/engine/install/ubuntu/)
  - [Official Docs - CentOS](https://docs.docker.com/engine/install/centos/)

  Remember that after installing docker in Linux, you should add the current user to the Docker Group with the following command to avoid using `sudo` in all docker commands:
  ```
  sudo usermod -aG docker $USER
  ```


## Validate if the local installation was successful
  ```
  docker run -d -p 8080:80 --name nginx nginx:latest
  ```
  Open your browser and open http://localhost:8080

  If you can see the Nginx webpage it means that Docker is working fine and you just deployed your first application using Docker. Remove the container:

  ```
  docker rm -f nginx
  ```

## Sign up to Docker Hub

[Sign up to Docker Hub here, but first, read the warning below.](https://hub.docker.com/signup)

**WARNING:** Please keep in mind that the free tier of Dockerhub makes your data public. DO NOT upload anything related to internal or customer projects to Dockerhub unless it is a paid private account. It is fine to push test images to Dockerhub as long as they don't contain secrets or any type of sensitive data. It is very common for people to make this type of mistakes.

## Online Environments to Play Around
  Here are some online environments that will allow you to run Docker tests without having to run commands in your local machine. This is great whenever you want to experiment with the unknown.

  - [Katacoda Docker Playground](https://www.katacoda.com/courses/docker/playground)
  - [Docker official Playground](https://labs.play-with-docker.com/)

  ### Interactive Tutorials

  - [Katacoda Docker Interactive Tutorials](https://www.katacoda.com/courses/docker)
  - [Dockerlabs](http://dockerlabs.collabnix.com/) <- This one is amazing. We'll constantly reference it. If you want, you can use this one as a guide for your whole learning process.
  - [Learn2torials](https://learn2torials.com/category/docker) <- This one is also pretty good.

## Official Documentation
  - [Docker Engine Docs](https://docs.docker.com/engine/) (This is the main Docker Engine documentation)
  - [Docker Getting Started Docs](https://docs.docker.com/get-started/overview/) (Some concepts about Docker)

  - [Docker Compose Docs](https://docs.docker.com/compose/) (Documentation for orchestration - Check it out when you reach the orchestration section)

You don't have to read everything, we'll point you to these docs when necessary but you should also stay curious and read.