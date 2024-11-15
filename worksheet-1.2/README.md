## 1. Aim/Overview of the practical: 
 #### To understand the Container Lifecycle Management with Docker:
o	Docker images
o	Containers
o	Docker repository
o	Docker commands
o	Docker file
### 2. Task to be done: 
The objective of this practical is to understand and implement the lifecycle management of containers using Docker. You will create a Docker image, run a container, interact with it, manage its state, and push the image to a Docker repository. 
### 3. Apparatus:
	Computer System: A computer with a Linux-based OS (or Windows with Docker Desktop installed).

	Docker Installed: Ensure Docker is installed and running on your system.

	Internet Connection: For downloading Docker images and pushing to Docker Hub.

	Text Editor: For writing the Dockerfile (e.g., VS Code, Sublime Text).

	Docker Hub Account: For pushing and pulling Docker images (optional, for repository-related tasks).

### 4. Theory:
Docker Images:
A Docker image is a lightweight, standalone, and executable software package that includes everything needed to run a piece of software: code, runtime, libraries, environment variables, and configuration files. Docker images are used to create containers, and they can be shared and distributed via Docker repositories.

Containers:
A container is an instance of a Docker image that runs as a lightweight, isolated environment on a host system. Containers are portable and consistent across various environments, allowing developers to run applications and their dependencies in a standardized way. Unlike virtual machines, containers share the host system's OS kernel, making them more efficient in terms of resource usage.

Docker Repository:
A Docker repository, such as Docker Hub, is a storage location where Docker images are stored and managed. It can be public or private, allowing users to share their images with others or keep them for private use. Docker repositories make it easy to distribute, version, and collaborate on images.

Docker Commands:
Docker commands are CLI (Command Line Interface) instructions used to interact with Docker. They allow users to perform various operations like building images, running containers, managing repositories, and inspecting the Docker environment. Common Docker commands include docker build, docker run, docker pull, docker push, and docker ps.

Docker file:
A Docker file is a text file that contains a series of commands and instructions to build a Docker image. It defines what goes into the image, such as the base image, application code, dependencies, and environment settings. By automating the image creation process, Dockerfiles ensure consistency and reproducibility across different environments.

### 5. Procedure:
Docker Architecture and Components:
Docker uses a client-server architecture. The docker client talks to the Docker daemon, which used to building, running, and distributing the Docker containers. The Docker client and daemon communicate using a REST API, over UNIX sockets, or a network interface.

There are five major components in the Docker architecture:
a)     Docker Daemon listens to Docker API requests and manages Docker objects such as images, containers, networks and volumes.

b)    Docker Clients: With the help of Docker Clients, users can interact with Docker. Docker client provides a command-line interface (CLI) that allows users to run, and stop application commands to a Docker daemon.

c)     Docker Host provides a complete environment to execute and run applications. It comprises of the Docker daemon, Images, Containers, Networks, and Storage.

d)    Docker Registry stores Docker images. Docker Hub is a public registry that anyone can use, and Docker is configured to use images on Docker Hub by default. You can run your own registry on it.

e)     Docker Images are read-only templates that you build from a set of instructions written in Docker file. Images define both what you want your packaged application and its dependencies to look like what processes to run when it’s launched.

f)      Docker File is a document file that contains collections of commands that will be executed in the docker environment for building a new docker image. This file is written in YAML Language. These images consist of read-only layers each of which represents a Docker file instruction. It is a more systematic, flexible and efficient way to build a Docker image.

Docker Container Lifecycle Management: There are different stages when we create a Docker container which is known as Docker Container Lifecycle. Some of the states are:
•	Created: A container that has been created but not started

•	Running: A container running with all its processes

•	Paused: A container whose processes have been paused

•	Stopped: A container whose processes have been stopped

•	Deleted: A container in a dead state 
![image](https://github.com/user-attachments/assets/6c658ac2-e7d8-4070-b820-aeb2d4913da7)

### 6. Steps for experiment/practical:
a)	Install Docker:
•	Verify that Docker is installed on your system by running docker --version.
•	If Docker is not installed, download and install Docker from the official Docker website.

b)	Docker Images:
•	List available Docker images on your system using docker images.
•	Pull a basic image from Docker Hub, e.g., docker pull ubuntu.
•	Inspect the pulled image with docker inspect <image_name>.

c)	Create a Container:
•	Run a container from the pulled image using docker run -it --name my_container ubuntu.
•	Inside the container, run basic commands to explore the environment (e.g., ls, pwd, etc.).
•	Exit the container using exit.

d)	Container Management:
•	List all running containers with docker ps.
•	List all containers, including stopped ones, with docker ps -a.
•	Start, stop, and remove containers using docker start, docker stop, and docker rm.

e)	Dockerfile Creation:
•	Create a directory for your Docker project and navigate into it.
•	Build the image using the Dockerfile with docker build -t my_app_image ..

f)	Run and Test the Container:
•	Run a container from the newly created image with docker run -p 4000:80 my_app_image.
•	Access the running application (if it's a web app, open a browser and navigate to http://localhost:4000).

g)	Push Image to Docker Repository (optional):
•	Tag the image for Docker Hub with docker tag my_app_image <your_dockerhub_username>/my_app_image.
•	Push the image to Docker Hub using docker push <your_dockerhub_username>/my_app_image.
•	Verify the image on Docker Hub by logging into your account.

h)	Clean Up:
•	Stop and remove any running containers with docker stop <container_id> and docker rm <container_id>.
•	Remove the custom image with docker rmi my_app_image.

### 7. Result/Output/Writing Summary:
•  Understanding: Through this experiment, you will gain hands-on experience with Docker, including managing the full lifecycle of containers from image creation to running and managing containers, and even sharing images through a repository.
•  Skill Development: You'll develop skills in using Docker commands, writing Dockerfiles, and understanding how Docker images and containers interact. This will prepare you for more complex Docker and containerization tasks in real-world scenarios.
