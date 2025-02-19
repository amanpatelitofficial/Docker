# Docker 

![image](https://github.com/user-attachments/assets/045e822a-0eab-4db6-87b8-6180ed7954e6)


# 🔹 Basic Docker Commands

Check Docker version

````bash
docker --version 
````

Get system-wide information about Docker

````bash
docker info  
````

🔹 Container Management

````bash

docker run -d -p 8080:80 nginx     # Run an Nginx container in detached mode
docker ps                          # List running containers
docker ps -a                       # List all containers (including stopped ones)
docker stop <container_id>         # Stop a running container
docker start <container_id>        # Start a stopped container
docker restart <container_id>      # Restart a container
docker rm <container_id>           # Remove a stopped container
docker logs -f <container_id>      # View logs of a container
docker inspect <container_id>      # View detailed information about a container
docker exec -it <container_id> sh  # Access a running container (if Alpine-based)
docker exec -it <container_id> bash # Access a running container (if Ubuntu-based)

````

🔹 Image Management

````bash
docker images                      # List available Docker images
docker pull ubuntu                 # Download an image from Docker Hub
docker build -t myapp .            # Build a Docker image from a Dockerfile
docker rmi <image_id>              # Remove an image
docker tag myapp myrepo/myapp:v1   # Tag an image for pushing
docker push myrepo/myapp:v1        # Push an image to Docker Hub

````

🔹 Network & Volume Management

````bash
docker network ls                  # List all networks
docker network create mynetwork    # Create a new network
docker network inspect mynetwork   # Inspect a network
docker network connect mynetwork <container_id>  # Connect a container to a network
docker network disconnect mynetwork <container_id>  # Disconnect a container

docker volume ls                    # List all volumes
docker volume create myvolume        # Create a volume
docker volume inspect myvolume       # Inspect a volume
docker volume rm myvolume            # Remove a volume

````

🔹 Container Cleanup

````bash
docker system prune -f               # Remove unused containers, networks, and images
docker container prune -f            # Remove all stopped containers
docker image prune -f                # Remove unused images
docker volume prune -f               # Remove unused volumes

````
