# Inception
A short introduction to Docker

## Display Help
- `docker help` – Displays general Docker help.
- `docker <sub-command> --help` – Displays help for a specific Docker sub-command.

## Display Docker Installation Information
- `docker --version` – Shows the Docker version.
- `docker version` – Provides detailed version information.
- `docker info` – Displays system-wide information about Docker.

## Run a Docker Image
- `docker run hello-world` – Runs the hello-world image.

## List Docker Images
- `docker image ls` or `docker images` – Lists Docker images available locally.

## Remove a Docker Image
- `docker rmi <IMAGE_ID or IMAGE_NAME>` – Removes the specified Docker image.
  - Use `-f` or `--force` to force removal if necessary.

## Remove All Docker Images
- `docker rmi -f $(docker images -q)` – Forces removal of all Docker images.

## Search for an Image on Docker Hub
- `docker search ubuntu` – Searches for Ubuntu-related images.
  - Add `--filter "is-official=true"` to display only official images.

## Download a Docker Image from Docker Hub
- `docker pull <IMAGE_NAME>` – Downloads the specified Docker image (defaults to the latest tag).
- Example: `docker pull ubuntu:16.04` – Downloads the Ubuntu image tagged 16.04.

## Additional Useful Docker Commands

### List Running Containers
- `docker ps` – Lists running containers.
- `docker ps -a` – Lists all containers (both running and stopped).

### Manage Containers
- `docker stop <CONTAINER_ID>` – Stops a running container.
- `docker start <CONTAINER_ID>` – Starts a stopped container.
- `docker rm <CONTAINER_ID>` – Removes a container.

### Run a Container in Detached Mode
- `docker run -d <IMAGE_NAME>` – Runs a container in the background (detached).

### View Container Logs
- `docker logs <CONTAINER_ID>` – Displays logs from a container.

### Execute a Command in a Running Container
- `docker exec -it <CONTAINER_ID> <command>` – Executes a command interactively inside a running container.

<!-- Append the following to your README.md -->

## Run a Docker Container with Options
You can run a container with various options to customize its behavior. For example:

- `docker run <CONTAINER_ID or CONTAINER_NAME>`
  - `-t` or `--tty`: Allocate a pseudo-TTY.
  - `-i` or `--interactive`: Keep STDIN open even if not attached.
  - `-d` or `--detach`: Run the container in the background.
  - `--name <name>`: Assign a specific name to the container.
  - `--expose <port(s)>`: Expose a port or a range of ports (without publishing them to the host).
  - `-p <host_port:container_port>` or `--publish <host_port:container_port>`: Map a host port to a container port.
  - `--rm`: Automatically remove the container when it exits.

## List Running Docker Containers
- `docker container ls`  
  or  
- `docker ps`  
  - Adding the `-a` or `--all` flag shows all containers regardless of their state (running, stopped, etc.).

## Remove a Docker Container
- `docker rm <CONTAINER_ID or CONTAINER_NAME>`
  - Use `-f` or `--force` to forcibly remove a running container.

## Remove All Docker Containers
- `docker rm -f $(docker ps -aq)`  
  This force-removes all containers on your system.

## Execute a Command Inside a Running Container
- `docker exec <CONTAINER_ID or CONTAINER_NAME> <COMMAND>`
  - `-t` or `--tty`: Allocate a pseudo-TTY.
  - `-i` or `--interactive`: Keep STDIN open.
  - `-d` or `--detach`: Run the command in the background.

## View Container Output/Errors
- `docker logs <CONTAINER_ID or CONTAINER_NAME>`
  - `-f`: Follow the log output continuously.
  - `-t`: Include timestamps on each log line.
  - `--tail <number_of_lines>`: Show only the specified number of lines from the end (by default, shows all).

## Commit a Container as an Image
This allows you to convert a running or stopped container into a new Docker image.
- `docker commit <CONTAINER_NAME or CONTAINER_ID> <NEW_IMAGE_NAME>`
  - `-a` or `--author "<name> <email>"`: Specify the author (e.g., "John Hannibal Smith <hannibal@a-team.com>").
  - `-m` or `--message "<commit message>"`: Add a commit message to describe the changes.

> **Tip:** When running commands in interactive mode (using the `-i` and `-t` flags), you can combine them to debug or work interactively inside your container.