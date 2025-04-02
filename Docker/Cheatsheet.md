# 🐳 Docker Command CheatSheet

A concise and developer-friendly command reference for using Docker efficiently.

---

## 📦 IMAGES

```bash
# List all local images
docker images

# Delete an image
docker rmi <image_name>

# Remove unused images
docker image prune

# Build image from Dockerfile
docker build -t <image_name>:<tag> .

# Build without cache
docker build --no-cache -t <image_name>:<tag> .

# Save image to .tar file
docker save -o <filename>.tar <image_name>

# Load image from .tar file
docker load -i <filename>.tar
```

---

## 🧱 CONTAINERS

```bash
# List all containers (running + stopped)
docker ps -a

# List only running containers
docker ps

# Create & run a container
docker run <image_name>

# Run container in background
docker run -d <image_name>

# Run container with custom name
docker run --name <container_name> <image_name>

# Port Binding
docker run -p <host_port>:<container_port> <image_name>

# Set environment variables
docker run -e <key>=<value> <image_name>

# Start/Stop container
docker start|stop <container_id/name>

# Inspect a container
docker inspect <container_id/name>

# Delete a container
docker rm <container_id/name>

# Rename a container
docker rename <old_name> <new_name>
```

---

## 🔍 TROUBLESHOOTING

```bash
# View logs of a container
docker logs <container_id/name>

# Open terminal in running container (bash or sh)
docker exec -it <container_id/name> /bin/bash
docker exec -it <container_id/name> sh

# Check real-time resource usage
docker stats

# Check container’s processes
docker top <container_id/name>
```

---

## 🐙 DOCKER HUB

```bash
# Pull image from DockerHub
docker pull <image_name>

# Push image to DockerHub
docker push <username>/<image_name>

# Login/Logout from DockerHub
docker login -u <username>
docker logout

# Search for image on DockerHub
docker search <image_name>
```

---

## 💾 VOLUMES

```bash
# List all volumes
docker volume ls

# Create named volume
docker volume create <volume_name>

# Delete named volume
docker volume rm <volume_name>

# Mount named volume
docker run --volume <volume_name>:<container_path> <image>

# Mount using --mount (recommended)
docker run --mount type=volume,source=<volume_name>,target=<container_path> <image>

# Create anonymous volume
docker run --volume <container_path> <image>

# Bind mount host directory
docker run --volume <host_path>:<container_path> <image>

# Bind mount using --mount
docker run --mount type=bind,source=<host_path>,target=<container_path> <image>

# Remove all unused volumes
docker volume prune
```

---

## 🌐 NETWORKING

```bash
# List networks
docker network ls

# Create custom bridge network
docker network create <network_name>

# Connect container to network
docker network connect <network_name> <container_name>

# Remove a network
docker network rm <network_name>

# Remove all unused networks
docker network prune
```

---

## 🧩 DOCKER COMPOSE

```bash
# Start services defined in docker-compose.yml
docker-compose up

# Start in detached mode
docker-compose up -d

# Stop all services
docker-compose down

# Build or rebuild services
docker-compose build

# View logs of all services
docker-compose logs -f
```

---

## 🧠 MISC

```bash
# Get Docker system info
docker info

# View Docker version
docker version

# Clean up system (images, containers, networks not used)
docker system prune
```

> 💡 **Tip:** Use `--help` with any command to learn more, e.g., `docker run --help`
