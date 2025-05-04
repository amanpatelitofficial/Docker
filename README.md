
# 🔹 When we install docker then by default containerd is installed

# 🔹 Docker 

![image](https://github.com/user-attachments/assets/045e822a-0eab-4db6-87b8-6180ed7954e6)

# 🔹 Docker Architecture | How Docker run our Container

![image](https://github.com/user-attachments/assets/cd082072-0973-4067-9e8f-69ee69084ea5)


# 🔹 CRI - Container RunTime Interface

![image](https://github.com/user-attachments/assets/1d17814e-17f7-4191-8e32-10959b465faa)


# 🔹 OCI - Open Container Initiative

![image](https://github.com/user-attachments/assets/02928399-ab18-48d4-87b7-1cb0359b42db)

# 🔹 Basic Docker Commands

Check Docker version

````bash
docker --version 
````

Get system-wide information about Docker

````bash
docker info  
````
# 🔹 Docker Permission

````
sudo usermod -aG docker $USER
````
````
newgrp docker
````

# 🔹 Command to see the process of Docker & Containerd

````
ps -aux
````

ps — process status command.

a — show processes for all users.

u — show the process's user/owner.

x — show processes not attached to a terminal (like daemons).



# 🔹 When we run a docker then runc create a process, How to verify it ?

`````
docker run -itd nginx
`````

 Now see that runc is responsible for creating container by creating a process by communicating with containerd.

`````
 pa  -aux | grep container_ip
`````
Output

![image](https://github.com/user-attachments/assets/6baea886-ce1d-4f0d-a4c9-7634792add03)


After that go inside the proc dir 

`````
cd /proc
`````

Go inside the pid dir of runc, you will see the linux file system hierarchy

`````
cd 3405
`````
`````
ls
`````
`````
bin  boot  dev	docker-entrypoint.d  docker-entrypoint.sh  etc	home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
`````



 # 🔹 Container Management

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
docker network rm mynetwork
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
# 🔹 Docker Volume

![image](https://github.com/user-attachments/assets/258bee5e-fb2b-436e-b9fe-93effd8fba82)


# 🔹 Docker CMD & EntryPoint

![image](https://github.com/user-attachments/assets/aaf94b57-a480-4ffa-a0fb-8187d16849c5)



