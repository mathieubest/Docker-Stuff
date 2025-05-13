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
