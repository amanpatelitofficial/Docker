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
