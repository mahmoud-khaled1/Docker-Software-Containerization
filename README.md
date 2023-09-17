# Software Containerization for Beginners
### What is virtualization in Docker?
In Docker, virtualization refers to the process of creating and running virtualized environments called containers. Docker is an open-source platform that provides an additional layer of abstraction and automation for virtualization on top of the operating system.

Traditional virtualization, such as using hypervisors like VMware or VirtualBox, involves running multiple virtual machines (VMs), each with its own operating system, on a physical host machine. This approach can be resource-intensive because each VM requires its own kernel, libraries, and system processes.

Docker takes a different approach called containerization, which is a lightweight form of virtualization. Instead of running full-fledged VMs, Docker allows you to package an application and its dependencies into a container. Containers are isolated environments that share the host machine's operating system kernel, but have their own isolated file systems, processes, and networking.

Virtualization in Docker is achieved using a technology called "containerization engine." Docker uses its containerization engine to build, distribute, and run containers. The containerization engine utilizes operating system-level virtualization features, such as cgroups and namespaces, to provide isolation and resource management for containers.

### What is Containerization?

Containerization is a method of virtualization that allows you to package an application and its dependencies into a standardized unit called a container. Containers provide a lightweight and isolated runtime environment for applications to run consistently across different computing environments.

In containerization, the application and its dependencies are bundled together into a single package, which includes the necessary libraries, runtime, and configuration files. This package is often referred to as an image. The container image is then used to create and run container instances.

Containers are isolated from one another and from the underlying host system, providing a level of security and resource management. Each container has its own file system, processes, and network interfaces, but shares the host machine's operating system kernel. This shared kernel approach results in lightweight and efficient virtualization, as compared to traditional virtual machines that require separate operating system instances.

Containerization offers several benefits:
1. Portability: Containers provide a consistent runtime environment, ensuring that applications run the same way across different platforms, such as development laptops, testing servers, and production systems. This portability simplifies the deployment process and reduces compatibility issues.

2. Scalability: Containers can be easily scaled up or down based on demand. You can replicate container instances to handle increased traffic or scale them down during periods of low usage. This flexibility enables efficient resource utilization and cost savings.

4. Efficiency: Containers have minimal overhead compared to virtual machines since they share the host system's kernel. They start up quickly and require fewer system resources, allowing for higher density and more efficient utilization of hardware.

5. Isolation: Containers offer process-level isolation, ensuring that applications running within containers are isolated from each other and the host system. This isolation improves security and reduces the risk of conflicts between applications.

6. Dependency management: Containerization allows you to package an application along with its dependencies, ensuring that all required libraries and components are included. This simplifies dependency management and avoids conflicts between different versions of software dependencies.

### What is Docker?
Docker is an open-source platform that provides a way to automate the deployment, scaling, and management of applications using containerization. It allows you to package an application and its dependencies into a standardized unit called a container, which can run consistently across different computing environments.

Here are some key aspects and components of Docker:
1. Containerization: Docker uses containerization technology to create lightweight and isolated environments called containers. Containers provide a consistent runtime environment for applications, with their own file systems, processes, and networking, while sharing the host machine's kernel. This enables efficient resource utilization and ensures that applications run consistently across different systems.

2. Docker Engine: Docker Engine is the underlying technology that enables the creation and management of containers. It consists of a client-server architecture, with the Docker client providing the command-line interface (CLI) and API for interacting with Docker, and the Docker daemon running on the host machine, responsible for building, running, and managing containers.

3. Docker Images: Docker images are the building blocks of containers. An image is a read-only template that includes the application code, runtime, libraries, and dependencies needed to run an application. Images are created from a base image and can be customized and layered with additional components and configurations. They are stored in a registry, such as Docker Hub or a private registry, from which they can be pulled and used to create container instances.

4. Dockerfile: A Dockerfile is a text file that contains a set of instructions for building a Docker image. It specifies the base image, application code, dependencies, and configurations required for the image. Dockerfiles allow for the automation and repeatability of the image building process, enabling version control and easy deployment.

5. Docker Compose: Docker Compose is a tool that allows you to define and manage multi-container applications. It uses a YAML file to specify the services, networks, and volumes required for the application. Docker Compose simplifies the orchestration and management of complex applications that consist of multiple interconnected containers.

6. Docker Swarm and Kubernetes: Docker Swarm and Kubernetes are container orchestration platforms that provide advanced features for managing containerized applications at scale. They enable the deployment, scaling, load balancing, and self-healing of containers across a cluster of machines. Docker Swarm is Docker's native orchestration solution, while Kubernetes has gained significant popularity and is widely used for container orchestration.

Docker has revolutionized software development and deployment by providing a standardized and efficient way to package and distribute applications. It simplifies the process of building, shipping, and running applications, making it easier to adopt modern software development practices like continuous integration, continuous deployment, and DevOps.
### Docker Architecture
![image](https://github.com/mahmoud-khaled1/Docker-Software-Containerization/assets/43557035/a880b88e-929f-4852-9a3c-224e9d069eb7)

When it comes to Docker architecture, it uses a client-server architecture. And, its architecture consists of 3 major parts, such as:
1. Docker Host
2. Docker Client
3. Registry

i. Docker Host
Basically, a Docker Host runs the Docker Daemon. As its job role, the daemon listens for Docker API requests such as ‘docker run’, ‘docker builds’, anything and also manages Docker objects like images, containers, networks, etc.
Moreover, one daemon can easily communicate with other daemons in order to manage Docker services.

ii. Docker Client
Here, the Client is nothing but the primary way by which many Docker users interact with Docker.
While we use various commands like (docker build, docker run, etc.) the Docker client sends these commands to the Docker Daemon, which carries them out. One of the best features of Docker client is, it can easily communicate with more than one daemon.

iii. Docker Registries
A stateless, highly scalable server-side application, which stores and lets us distribute Docker images is what we call the Registry. There is a flexibility that either we can create our own image or we can use public registries such as Docker Hub and Docker Cloud.
By default, Docker is configured to look for images on one of its public registries “Docker Hub”. One of the advantages it offers is we can create our own registry as well.
Hence, while we run the docker pull or docker run command, it is possible to pull the required images from our configured registry. Basically, our image is pushed to our configured registry, while we use the docker push command.

### What is the purpose of VOLUME in Dockerfile?
In the context of Docker, a volume is a persistent storage location that exists outside of the container. Volumes are useful for storing data that needs to persist even if the container is stopped or removed.
In a Dockerfile, the VOLUME instruction is used to specify a mount point for a volume within the container. The volume will be created when the container is built, and it can be accessed and modified by processes running inside the container.

Purpose of volume in Dockerfile :- <br />

1. Persisting data: If you have data that needs to persist even if the container is stopped or removed, you can store it in a volume. This is useful for things like database files or application logs.

2. Sharing data between containers: If you have multiple containers that need to share data, you can use a volume to allow them to access the same data. This can be useful for things like storing shared configuration files or data used by multiple containers.

3. Easing data management: By separating data from the container itself, volumes can make it easier to manage the data. For example, you can use a volume to store data that is generated by the container, and then
# Docker Commands, Help & Tips

### Show commands & management commands

```
 docker
```

### Docker version info

```
  docker version
```

### Show info like number of containers, etc

```
  docker info
```

# WORKING WITH CONTAINERS

### Create an run a container in foreground

```
  docker container run -it -p 80:80 nginx
```

### Create an run a container in background

```
  docker container run -d -p 80:80 nginx
```

### Shorthand

```
  docker container run -d -p 80:80 nginx
```

### Naming Containers

```
  docker container run -d -p 80:80 --name nginx-server nginx
```

### TIP: WHAT RUN DID

- Looked for image called nginx in image cache
- If not found in cache, it looks to the default image repo on Dockerhub
- Pulled it down (latest version), stored in the image cache
- Started it in a new container
- We specified to take port 80- on the host and forward to port 80 on the container
- We could do "  docker container run --publish 8000:80 --detach nginx" to use port 8000
- We can specify versions like "nginx:1.09"

### List running containers

```
  docker container ls
```

OR

```
  docker ps
```

### List all containers (Even if not running)

```
  docker container ls -a
```

### Stop container

```
  docker container stop [ID]
```

### Stop all running containers

```
  docker stop  (docker ps -aq)
```

### Remove container (Can not remove running containers, must stop first)

```
  docker container rm [ID]
```

### To remove a running container use force(-f)

```
  docker container rm -f [ID]
```

### Remove multiple containers

```
  docker container rm [ID] [ID] [ID]
```

### Remove all containers

```
  docker rm  (docker ps -aq)
```

### Get logs (Use name or ID)

```
  docker container logs [NAME]
```

### List processes running in container

```
  docker container top [NAME]
```

#### TIP: ABOUT CONTAINERS

Docker containers are often compared to virtual machines but they are actually just processes running on your host os. In Windows/Mac, Docker runs in a mini-VM so to see the processes youll need to connect directly to that. On Linux however you can run "ps aux" and see the processes directly

# IMAGE COMMANDS

### List the images we have pulled

```
  docker image ls
```

### We can also just pull down images

```
  docker pull [IMAGE]
```

### Remove image

```
  docker image rm [IMAGE]
```

### Remove all images

```
  docker rmi  (docker images -a -q)
```

#### TIP: ABOUT IMAGES

- Images are app bianaries and dependencies with meta data about the image data and how to run the image
- Images are no a complete OS. No kernel, kernel modules (drivers)
- Host provides the kernel, big difference between VM

### Some sample container creation

NGINX:

```
  docker container run -d -p 80:80 --name nginx nginx (-p 80:80 is optional as it runs on 80 by default)
```

APACHE:

```
  docker container run -d -p 8080:80 --name apache httpd
```

MONGODB:

```
  docker container run -d -p 27017:27017 --name mongo mongo
```

MYSQL:

```
  docker container run -d -p 3306:3306 --name mysql --env MYSQL_ROOT_PASSWORD=123456 mysql
```

## CONTAINER INFO

### View info on container

```
  docker container inspect [NAME]
```

### Specific property (--format)

```
  docker container inspect --format '{{ .NetworkSettings.IPAddress }}' [NAME]
```

### Performance stats (cpu, mem, network, disk, etc)

```
  docker container stats [NAME]
```

## ACCESSING CONTAINERS

### Create new nginx container and bash into

```
  docker container run -it --name [NAME] nginx bash
```

- i = interactive Keep STDIN open if not attached
- t = tty - Open prompt

**For Git Bash, use "winpty"**

```
  winpty docker container run -it --name [NAME] nginx bash
```

### Run/Create Ubuntu container

```
  docker container run -it --name ubuntu ubuntu
```

**(no bash because ubuntu uses bash by default)**

### You can also make it so when you exit the container does not stay by using the -rm flag

```
  docker container run --rm -it --name [NAME] ubuntu
```

### Access an already created container, start with -ai

```
  docker container start -ai ubuntu
```

### Use exec to edit config, etc

```
  docker container exec -it mysql bash
```

### Alpine is a very small Linux distro good for docker

```
  docker container run -it alpine sh
```

(use sh because it does not include bash)
(alpine uses apk for its package manager - can install bash if you want)

# NETWORKING

### "bridge" or "docker0" is the default network

### Get port

```
  docker container port [NAME]
```

### List networks

```
  docker network ls
```

### Inspect network

```
  docker network inspect [NETWORK_NAME]
("bridge" is default)
```

### Create network

```
  docker network create [NETWORK_NAME]
```

### Create container on network

```
  docker container run -d --name [NAME] --network [NETWORK_NAME] nginx
```

### Connect existing container to network

```
  docker network connect [NETWORK_NAME] [CONTAINER_NAME]
```

### Disconnect container from network

```
  docker network disconnect [NETWORK_NAME] [CONTAINER_NAME]
```

### Detach network from container

```
  docker network disconnect
```

# IMAGE TAGGING & PUSHING TO DOCKERHUB

# tags are labels that point ot an image ID

```
  docker image ls
```

Youll see that each image has a tag

### Retag existing image

```
  docker image tag nginx btraversy/nginx
```

### Upload to dockerhub

```
  docker image push bradtraversy/nginx
```

### If denied, do

```
  docker login
```

### Add tag to new image

```
  docker image tag bradtraversy/nginx bradtraversy/nginx:testing
```

### DOCKERFILE PARTS

- FROM - The os used. Common is alpine, debian, ubuntu
- ENV - Environment variables
- RUN - Run commands/shell scripts, etc
- EXPOSE - Ports to expose
- CMD - Final command run when you launch a new container from image
- WORKDIR - Sets working directory (also could use 'RUN cd /some/path')
- COPY # Copies files from host to container

### Build image from dockerfile (reponame can be whatever)

### From the same directory as Dockerfile

```
  docker image build -t [REPONAME] .
```

#### TIP: CACHE & ORDER

- If you re-run the build, it will be quick because everythging is cached.
- If you change one line and re-run, that line and everything after will not be cached
- Keep things that change the most toward the bottom of the Dockerfile

# EXTENDING DOCKERFILE

### Custom Dockerfile for html paqge with nginx

```
FROM nginx:latest # Extends nginx so everything included in that image is included here
WORKDIR /usr/share/nginx/html
COPY index.html index.html
```

### Build image from Dockerfile

```
  docker image build -t nginx-website
```

### Running it

```
  docker container run -p 80:80 --rm nginx-website
```

### Tag and push to Dockerhub

```
  docker image tag nginx-website:latest btraversy/nginx-website:latest
```

```
  docker image push bradtraversy/nginx-website
```

# VOLUMES

### Volume - Makes special location outside of container UFS. Used for databases

### Bind Mount -Link container path to host path

### Check volumes

```
  docker volume ls
```

### Cleanup unused volumes

```
  docker volume prune
```

### Pull down mysql image to test

```
  docker pull mysql
```

### Inspect and see volume

```
  docker image inspect mysql
```

### Run container

```
  docker container run -d --name mysql -e MYSQL_ALLOW_EMPTY_PASSWORD=True mysql
```

### Inspect and see volume in container

```
  docker container inspect mysql
```

#### TIP: Mounts

- You will also see the volume under mounts
- Container gets its own uniqe location on the host to store that data
- Source: xxx is where it lives on the host

### Check volumes

```
  docker volume ls
```

**There is no way to tell volumes apart for instance with 2 mysql containers, so we used named volumes**

### Named volumes (Add -v command)(the name here is mysql-db which could be anything)

```
  docker container run -d --name mysql -e MYSQL_ALLOW_EMPTY_PASSWORD=True -v mysql-db:/var/lib/mysql mysql
```

### Inspect new named volume

```
docker volume inspect mysql-db
```

# BIND MOUNTS

- Can not use in Dockerfile, specified at run time (uses -v as well)
- ... run -v /Users/brad/stuff:/path/container (mac/linux)
- ... run -v //c/Users/brad/stuff:/path/container (windows)

**TIP: Instead of typing out local path, for working directory use  (pwd):/path/container - On windows may not work unless you are in your users folder**

### Run and be able to edit index.html file (local dir should have the Dockerfile and the index.html)

```
  docker container run  -p 80:80 -v  (pwd):/usr/share/nginx/html nginx
```

### Go into the container and check

```
  docker container exec -it nginx bash
  cd /usr/share/nginx/html
  ls -al
```

### You could create a file in the container and it will exiost on the host as well

```
  touch test.txt
```

# DOCKER COMPOSE

- Configure relationships between containers
- Save our docker container run settings in easy to read file
- 2 Parts: YAML File (docker.compose.yml) + CLI tool (docker-compose)

### 1. docker.compose.yml - Describes solutions for

- containers
- networks
- volumes

### 2. docker-compose CLI - used for local dev/test automation with YAML files

### Sample compose file (From Bret Fishers course)

```
version: '2'

# same as
# docker run -p 80:4000 -v  (pwd):/site bretfisher/jekyll-serve

services:
  jekyll:
    image: bretfisher/jekyll-serve
    volumes:
      - .:/site
    ports:
      - '80:4000'
```

### To run

```
docker-compose up
```

### You can run in background with

```
docker-compose up -d
```

### To cleanup

```
docker-compose down
```



For More Commands visit : 
 <a href="https://www.hostinger.com/tutorials/docker-cheat-sheet?ppc_campaign=google_search_generic_hosting_all&bidkw=defaultkeyword&lo=9112325&gclid=CjwKCAjw3dCnBhBCEiwAVvLcuzmIox6oPrZPQEQpo0MD9FV16uYT5SQYQSANyLWF_lzJDrJGUZoAhhoC1AoQAvD_BwE" target="_blank"> Link </a>
