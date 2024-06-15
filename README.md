# docker-scripts (Docker Cheat Sheet)

## Table of Contents
- [Docker Basics](#docker-basics)
- [Docker Images](#docker-images)
- [Docker Containers](#docker-containers)
- [Docker Volumes](#docker-volumes)
- [Docker Networks](#docker-networks)
- [Docker Compose](#docker-compose)
- [Docker Swarm](#docker-swarm)
- [Dockerfile](#dockerfile)
- [Docker Migrate](#docker-migrate)

## Docker Basics
- `docker --version` - Show the Docker version information.
- `docker info` - Display system-wide information.
- `docker help` - Get help on Docker commands.

## Docker Images
- `docker images` - List all Docker images.
- `docker pull <image>` - Pull an image from a registry.
- `docker build -t <name> .` - Build an image from a Dockerfile in the current directory.
- `docker rmi <image>` - Remove an image.
- `docker tag <image> <new_image>` - Tag an image with a new name.
- `docker history <image>` - Show the history of an image.
- `docker inspect <image>` - Show details of an image.

## Docker Containers
- `docker ps` - List running containers.
- `docker ps -a` - List all containers.
- `docker run -it <image>` - Run a container in interactive mode.
- `docker run -d <image>` - Run a container in detached mode.
- `docker stop <container>` - Stop a running container.
- `docker start <container>` - Start a stopped container.
- `docker restart <container>` - Restart a container.
- `docker rm <container>` - Remove a container.
- `docker logs <container>` - View logs of a container.
- `docker exec -it <container> /bin/bash` - Access a running container.

## Docker Volumes
- `docker volume create <name>` - Create a volume.
- `docker volume ls` - List volumes.
- `docker volume inspect <volume>` - Show details of a volume.
- `docker volume rm <volume>` - Remove a volume.

## Docker Networks
- `docker network ls` - List networks.
- `docker network create <name>` - Create a network.
- `docker network inspect <network>` - Show details of a network.
- `docker network connect <network> <container>` - Connect a container to a network.
- `docker network disconnect <network> <container>` - Disconnect a container from a network.
- `docker network rm <network>` - Remove a network.

## Docker Compose
- `docker-compose --version` - Show the Docker Compose version information.
- `docker-compose up` - Create and start containers.
- `docker-compose down` - Stop and remove containers, networks, images, and volumes.
- `docker-compose build` - Build or rebuild services.
- `docker-compose logs` - View output from containers.
- `docker-compose ps` - List containers.
- `docker-compose start` - Start services.
- `docker-compose stop` - Stop services.
- `docker-compose restart` - Restart services.
- `docker-compose rm` - Remove stopped containers.

## Docker Swarm
- `docker swarm init` - Initialize a swarm.
- `docker swarm join` - Join a swarm as a node.
- `docker node ls` - List nodes in the swarm.
- `docker service create <options>` - Create a service.
- `docker service ls` - List services.
- `docker service ps <service>` - List tasks of a service.
- `docker service scale <service>=<replicas>` - Scale a service.
- `docker service update <options> <service>` - Update a service.

## Dockerfile
- `FROM` - Base image.
- `COPY` - Copy files or directories.
- `ADD` - Copy files or directories with support for URL and tar extraction.
- `RUN` - Execute commands in a new layer.
- `CMD` - Provide defaults for an executing container.
- `ENTRYPOINT` - Configure a container that will run as an executable.
- `ENV` - Set environment variables.
- `EXPOSE` - Define the network ports that the container listens on.
- `VOLUME` - Create a mount point with a specified path.
- `WORKDIR` - Set the working directory.

## Docker Migrate
- **Migration Steps:**
  - **Stop Containers:** `docker stop $(docker ps -a -q)`
  - **Export Containers:** `docker export <container_id> > <container_id>.tar`
  - **Save Images:** `docker save <image> > <image>.tar`
  - **Transfer Files:** Move tar files to the new host.
  - **Import Containers:** `cat <container_id>.tar | docker import - <new_container_name>`
  - **Load Images:** `docker load < <image>.tar`
  - **Start Containers:** `docker run <new_container_name>`

