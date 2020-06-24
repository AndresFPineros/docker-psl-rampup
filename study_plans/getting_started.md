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


## Deploying a first Docker container
  ### Check we can run a container
  ```
  docker run -d -p 8080:80 -n nginx
  ```
  Open your browser and open http://localhost:8080

  If you can see the Nginx webpage it means that Docker is working fine and you just deployed your first application using Docker.

  ### Having issues with local installation?

  Are you having issues installing Docker but you want to start playing with it? Don't worry, there are plenty Docker Playgrounds Online that are free. They are very easy to use!

  - [Katacoda Docker Playground](https://www.katacoda.com/courses/docker/playground)
  - [Docker official Playground](https://labs.play-with-docker.com/)

  We like Katacoda because the have many interactive tutorials for Docker:
  
  - [Katacoda Docker Interactive Tutorials](https://www.katacoda.com/courses/docker)

## Get to know the sources of information.
We want you to get familiar with the sources of information that'll teach you about Docker. Take some time to check them out:
  - [Docker Engine Docs](https://docs.docker.com/engine/) (This is the main Docker Engine documentation)
  - [Docker Getting Started Docs](https://docs.docker.com/get-started/overview/) (Some concepts about Docker)
  - [Katacoda](https://www.katacoda.com/courses/docker) (Super fun interactive tutorials)
  - [Pluralsight Deep Dive Free Course](https://www.pluralsight.com/courses/docker-deep-dive-update) (Deep Dive into Docker - It is advanced but not too much.)
  - [Docker Curriculum](https://docker-curriculum.com/) (A full rampup in itself to deploy a web application)
  - [Docker Compose Docs](https://docs.docker.com/compose/) (Documentation for orchestration - Check it out when you reach the orchestration section)

You don't have to read everything, wer'll point you to these docs when necessary but you should also stay curious and read.