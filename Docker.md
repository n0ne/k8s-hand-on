### Docker commands

- `docker images ls` - List available Docker images
- `docker image pull <image_name>` - Pull a Docker image from a repository
- `docker container run -p 8080:80 -d <image_name>` - Run a Docker container, mapping port 8080 on the host to port 80 on the container in detached mode
- `docker container ls` - List running Docker containers
- `docker container stop <id>` - Stop a running Docker container by specifying its ID
- `docker container rm <id>` - Remove a Docker container by specifying its ID
